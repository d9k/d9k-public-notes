# Linux init systems compare

- :tv: [Сравнение скорости всех систем инициализации | Ampersand | YT](https://www.youtube.com/watch?v=XaNTJSpMBoE), 2023
	- dinit - best. sinit - инициализация без многого (напр., без инета)
	- s6, OpenRC, runit - pretty fast

- https://systemdfree.com/
	- https://systemdfree.com/#compare
	- One Process. One Purpose: An init system should start processes, supervise them, and stop them. Not manage DNS, log daemons, network configuration, login sessions, time synchronization, and device events under a single monolithic binary with 1.4 million lines of code.
	- Transparency is Not Optional: Service management should be auditable by any user with a text editor and basic shell skills. Shell scripts are documentation. Binary unit files compiled into journal logs are not. Your init should never require a PhD to debug.


## RunIt

- Smallest: ~7k lines!

### This Linux Init System Is Surprisingly Simple / Hack the Clown / YT, 2026

https://youtube.com/watch?v=c3xNvgkz83E

RunIt

0:35 Services: Just sh-files
1:45 Different process for logging
2:45 /supervise dir  with runtime state of the services created automatically
3:00 sudo sv status /var/service/* - all services status
sudo grc ... to improve the output (generic colorizer)
3:20 services directory compatible with version control

## s6

### s6 - focus on reliability. Почему так пишут? / 🤖 DeepSeek

s6 — это набор маленьких инструментов, каждый делает одно. `s6-svscan`, `s6-supervise`, `s6-svc`, `s6-svstat`, `s6-log`, `s6-rc`, `s6-rc-compile`. Каждый можно понять целиком. Меньше кода — меньше багов. Меньше поверхностей атаки.

В s6 сервис **всегда** перезапускается, если процесс завершился. Это не опция (`Restart=on-failure` в systemd), а **поведение по умолчанию**. Чтобы сервис не перезапускался, надо явно указать это (`down`-файл или `finish`-скрипт).
Это значит: если процесс упал — s6 его поднимет. Если процесс упал 100 раз подряд — s6 поднимет 100 раз. Никакой «политики перезапуска», которая может ошибиться.

Лоран Берко писал, что цель s6 — **«быть настолько надёжным, насколько это возможно»**, и что он готов жертвовать удобством ради надёжности.

В s6 зависимости — **явные**, через `s6-rc` (отдельный слой) или через `sv check` в `run`-скрипте. Ты точно знаешь, что от чего зависит. Нет неявных `Wants=`, `After=`, `Requires=`, которые могут взаимодействовать неочевидно.

**Устойчивость к сбоям.**
- Если `run`-скрипт падает — s6 перезапускает.
- Если `s6-supervise` падает — `s6-svscan` перезапускает.
- Если `s6-svscan` падает — ядро перезапускает (PID 1).
- Если сервис зависает — можно настроить `timeout` через `s6-supervise`-опции.
- Если диск переполнен — `s6-log` может ротировать и сжимать.

#### `s6-rc-compile` и `s6-rc-db`

Это части **s6-rc** — отдельного слоя поверх s6, который добавляет то, чего в голом s6 нет: **зависимости между сервисами** и **упорядоченный запуск**. Сам s6 (s6-svscan/s6-supervise) умеет только «запустить всё параллельно и следить». s6-rc — это надстройка, которая говорит «запусти вот это в таком порядке, с такими зависимостями».

Ключевая идея s6-rc: **сервисная база компилируется из исходников в бинарный формат**, и уже скомпилированная база используется в рантайме. Это нетипично для init-систем и вызывает больше всего вопросов.

#### `/etc/s6-rc/source/`

Это директории с описаниями сервисов. Два типа:
- `oneshot` — сервис, который запускается один раз и завершается (например, `mount-filesystems`, `sysctl`, `hwclock`). Описывается файлом `up` (что делать при запуске) и опционально `down` (что делать при остановке).
- `longrun` — долгоживущий сервис (nginx, sshd, dbus). Описывается директорией с `run`-скриптом (как в голом s6).

Плюс файлы зависимостей:
- `dependencies.d/` — список имён сервисов, от которых зависит этот.
- `requiredby.d/` — обратная зависимость (кто требует этот сервис).
- `contents.d/` — для «бандлов» (групп сервисов).`dependencies.d/` — список имён сервисов, от которых зависит этот.
- `requiredby.d/` — обратная зависимость (кто требует этот сервис).
- `contents.d/` — для «бандлов» (групп сервисов).

#### `s6-rc-compile` **— компилятор**

Берёт исходники из `/etc/s6-rc/source/` и **компилирует их в бинарную сервисную базу**:

```bash
s6-rc-compile /etc/s6-rc/compiled /etc/s6-rc/source
```

Зачем компилировать, а не читать исходники в рантайме:
- **проверка ошибок** — циклические зависимости, отсутствующие сервисы, конфликты ловятся **на этапе компиляции**, а не при загрузке;
**- детерминизм** — скомпилированная база — это фиксированный артефакт, который не меняется;
**- атомарность** — база либо скомпилирована целиком, либо нет; нет частично сломанного состояния.

`s6-rc-db` **— у**тилита для **чтения** скомпилированной базы: `list`, `dependencies`, `up` (порядок запуска)

`s6-rc` **— рантайм-менеджер**.


```bash
s6-rc -u change nginx        # запустить nginx и его зависимости
s6-rc -a list                # что сейчас запущено
```

## System V

> 🗣️️: system v dependencies

🤖 GoogleAI: System V (SysV) init управляет зависимостями сервисов с помощью порядковых номеров (приоритетов) скриптов в каталогах уровней выполнения (runlevels).

• Последовательный запуск: Сервисы запускаются строго по очереди один за другим в соответствии с их номерами.
• Префиксы имен (S и K):
• Скрипты, начинающиеся с буквы S (Start), запускаются при переходе в нужный уровень (например, S20nginx, S99local). Чем меньше число после буквы, тем раньше запустится служба.
• Скрипты, начинающиеся с буквы K (Kill), останавливают службы при выходе из уровня (например, K09postfix).

**Заголовок LSB (Linux Standard Base):** Внутри самих скриптов в `/etc/init.d/` часто указываются специальные комментарии (например, `# Provides:`, `# Required-Start:`, `# Required-Stop:`), которые описывают, какая служба должна запуститься до или после данной.

**Отсутствие динамического графа:** В отличие от systemd, классический SysV не строит сложный граф параллельных зависимостей в реальном времени; он полагается на заранее прописанную нумерацию при помощи инструментов вроде `update-rc.d` (в Debian/Ubuntu) или `chkconfig` (в Red Hat/CentOS).

## Init Systems / dacctal / YT, 2026

https://youtube.com/watch?v=LGCJefnJkG4

- SystemD is bloated. Since 2010.
- 1:13 SystemV / System 5 - classical since 1983. `perp` supervisor.
- 2:06 OpenRC: used by an author: since 2007. Small, functional
- 2:30 runit: since 2004. All services started in parallel. Re-implementation of daemontools
- 2:45 Dinit - properly implemented systemd
- 3:18 s6 - too complicated?

## Linux Init Systems Compared! (SystemD, OpenRC, Runit) / DenshiVideo / YT, 2020

https://youtube.com/watch?v=k1Wh8sWR8v0

2:00 Comparing init systems on Artix and Arch: SystemD, OpenRC, Runit
2:15 Boot speed test: same
3:30 RAM: same
4:40 Actual difference

