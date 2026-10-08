# Fonts

## :white_check_mark: Better font for terminal?

- (Σ) Terminal: Monofoki bold, Obsidian: Monofoki, VSCode: saxMono bold

- Created: 2024.07

- [ ] Better terminal emulator?
	- smaller step of letter gap

- [-] disable font anti-aliasing
	- (Σ) Некрасиво получается
	- Да, проблема в шрифте Terminess, нет размеров на 13 и 14 пунктов
	- [ ] [Ugly font rendering with anti-aliasing disabled - Linux Mint Forums](https://forums.linuxmint.com/viewtopic.php?t=285451)
	- `/etc/fonts/conf.d/10-antialias.conf`
	- `sudo fc-cache -f -v`

- [x] better font
	- [nerd-fonts](https://github.com/ryanoasis/nerd-fonts?tab=readme-ov-file#font-patcher) by [ryanoasis](https://github.com/ryanoasis)
		- _Font Awesome, Material Design Icons, Octicons, & more_
		- Iconic font aggregator, collection, & patcher. 3,600+ icons
	- [ ] patch font
		- [ ] [Pip install fontforge, says Couldnot find a version - Stack Overflow](https://stackoverflow.com/questions/32688726/pip-install-fontforge-says-couldnot-find-a-version)
	- [ ] :scroll: [Nerd Fonts - Iconic font aggregator, glyphs/icons collection, & fonts patcher](https://www.nerdfonts.com/font-downloads)
	- :balloon: [Programming Fonts - Test Drive](https://www.programmingfonts.org/#hermit)
	- Install font:
		- 1. copy to :open_file_folder: `/usr/share/fonts/truetype`
		- 2. run :zap: `sudo fc-cache -f -v`
		- 3. check :zap: `fc-list ':mono'`
	- [[Solved] xfce4 terminal can not find the font... / Applications & Desktop Environments / Arch Linux Forums](https://bbs.archlinux.org/viewtopic.php?id=281042)

### ❤️

- [x] :sparkles::sparkles: Monofoki
	- :test_tube: Реально классный! Подходит терминалу и Obsidian. Возможно для кода хочется чуть-чуть более строгий. +1 позиция с золота, т. к. лучшая альтернатива пока
		- ~~Monofoki Bold норм показывает в терминале иконки. Bold Italic и regular узкие~~
			- всё равно не те, надо патчить
	- :sparkles: прекрасно масштабируется
	- :sparkles: легко читается
	- :sparkles: норм русский шрифт (+1 позиция)
	- ok в 10, норм в 12, норм в 13, хорош в 14, пойдёт в 16, норм в 17
	- :speech_balloon: [Nerdfont release? | issue #38 | monofoki](https://github.com/datMaffin/monofoki/issues/38), 2024.07.26

### :first_place_medal: Золото

- [-] Overpass Mono
	- Шире Monofoki, а он и так широкий
	- :sparkles: Неплохо масштабируется
	- Норм в 13, хорош в 15, мил в 16, хорош в 17
- [-] :sparkles::sparkles: Hermit
- :test_tube: поставил и он не оч., жирноват, -1 место с топа
	- Хорош в 13,15,16,18
- :microbe: расстояние между буквами по горизонтали маловато
	- Matrix, типа, прикольна
	-  прекрасно масштабируется
	-  легко читается
	- ok в 10, норм в 12, норм в 13, хорош в 14, пойдёт в 16, норм в 17

### :second_place_medal: Серебро

- [ ] :sparkles: Liberation Mono
	- хорош в 11,12,14,16
	- широковат
- [x] :sparkles::sparkles: Monoid
	- :test_tube: Для терминала прям неплох
		- :sparkles: Прекрасно масштабируется
		- Норм в 9, неплох в 12, мил в 14, мил в 15, аляповат в 16
- [ ] :sparkles::sparkles: Noto Mono
		- :sparkles: прекрасно масштабируется
		- :sparkles: супер русский шрифт
		- отл. в 12, норм в 13-14, хорош в 15-16, норм в 17, мил в 18
		- чуть шире и круглее, чем хотелось бы
- [-] :sparkles::sparkles: saxMono
	- -2 места с топа после теста
	- :microbe::microbe: лицензия не позволяет патчить шрифт!
	- :microbe: ненастоящий моноширный, xfcr4-terminal не увидел
	- [saxMono Font Free by s.a.x. Software » Font Squirrel](https://www.fontsquirrel.com/fonts/saxMono)
		- есть поддержка белорусского но не русского?
	- норм в 15, хорош в 16, отл. в 20
	-  :sparkles: оч. быстро читается
	- [saxMono шрифт | скачать бесплатно для WEB](https://rufonts.pro/shrift/saxmono)
	- `xfce4-teminal` doesn't see font!
	- [[Solved] xfce4 terminal can not find the font... / Applications & Desktop Environments / Arch Linux Forums](https://bbs.archlinux.org/viewtopic.php?id=281042)
		- :zap: `sudo apt remove gsfonts`
		- :zap: `fc-list ':mono' | grep sax` - empty!

### :third_place_medal: Бронза

- [ ] :sparkles: Bront DejaVu Sans Mono
	- :sparkles: простой, хороший баланс круглости
	- размеры 8,12,13 хорошо выглядят. 16 хорош
	- :microbe: средне на больших размерах
- [ ] Hack
	- хорош в 12,13,16. 14 норм
- :sparkles: Nanum Gothic Coding
	- :black_heart: норм в 14, пойдёт в 15, отличен в 16, мил в 20
	- :broken_heart: ГДЕ РУССКИЙ?! Абсолютно не поддерживает, буквы растянуты
- [ ] :sparkles: Terminus (TTF)
	- норм 18-21
	- почему-то эта версия нечёткая на малых размерах
- отброшенные в первую очередь
- [-] Average Mono
- :microbe: круглый, широкий
- [-] :thumbsup: Bedstead
	- как f и t вообще рисуются?!
	- лучше всего в размере 10
- [-] Bitsteam Vera Sans Mono
	- можно, но уныленький
- [-] :sparkles: Borg Dans Mono
	- :sparkles: читабельный и с перечёрк. нулём
	- :microbe: круглее, чем хотелось бы
- [-] BPromo
	- :microbe: проигрывает в читабельности соседям: горизонтальные линии визуально сливаются
- [-] Chivo Mono\
	- :microbe: проигрывает соседям, заурядный
- [-] :sparkles: Commit Mono
	- :microbe: чо-ото суть грузит, строг
- [-] D2Coding
	- :sparkles: прикольный, приятно плотный, квадратноватый
	- в 12-м, 15-м размере хорош. 14-й терпим
- [-] :sparkles: Droid Sans
	- :microbe: нет нуля с косой чертой
	- :microbe: чуть шире, чем нужно
- [-] :sparkles: EnvyCode B
	- :microbe: прикольный, но расплывчато увеличивается
- [-] Fixedsys
	- хорош, но расплывчато увеличивается
- [-] Fixedsys with Ligatures
	- хорош, но расплывчато увеличивается
- [-] Geist
	- :sparkles: классный, когда жирное начертание
	- всё-таки не цепляет
- [-] GNU Freefont
	- :microbe: Депрессивно тонкий, почти прозрачный
	- хорошо в 14 и 18
- [-] :sparkles: Gohufont 14
	- :sparkles: милашный
	- :microbe: не скейлится
- [-] Inconsolata OTF
	- :microbe: средне скейлится
- [-] Iosevka
	- :microbe: худой
	- 15, 21 ok
- [-] League Mono
	- :sparkles: мил
	- хорош в 14, норм+ в 16
- [-] :sparkles: Lekton
	- депрессивно-тонкий
- [-] :sparkles: Lucilent
	- терпим в 15, хорош в 14
- [-] :sparkles::sparkles: M PLUS Code
	- :microbe: ноль с точкой, а не чёркнутый
	- хорош в 16, терпим в 17, неплох в 20
- [-] Mensh
	- прекрасен в 12. ok в 14.
- [-] Monaspace Xenon
	- хорош в 11,15,17
- [-] Oxygen Mono
	- хорош в 15, неплох в 16, хорош в 18
	- на малых размерах смазанный
- [-] :sparkles: Profont
	- :test_tube: не особо порадовал
	- хорош в 12, норм в 13, средне-миловато в 14, странновато в 15
- чуть расплывчатый
- [-] :sparkles: Source Code Pro
	- :sparkles: неплохо масштабируется
	- норм в 13, норм+ в 15, чуть мил в 16
- [-] :sparkles: VT323
	- терпим в 15, 17, пойдёт в 18 и 20


## Mono font without anti-aliasing

- :label: and cyrillic, squarish, thin, 43+ rows in 1440p

Числа через запятую - какие размеры понравились.

### :third_place_medal: Good

- [Bront DejaVu Sans Mono](https://www.programmingfonts.org/#bront-dejavu)
	- 9, 10, 11, 12, 13, 14, 15,16
- [Ricty Diminished[Programming Fonts - Test Drive](https://www.programmingfonts.org/#ricty-diminished)](https://www.programmingfonts.org/#ricty-diminished)
	- 13, 17
	- :sparkles: На 17 оч. красивый
- [Terminus (Consoleet)](https://www.programmingfonts.org/#terminus-consoleet)
	- 15, 16, 17, 19, 29
	- [j.eng's site: Consoleet's take on Terminus (better TTF)](https://inai.de/projects/consoleet/terminus)
	- :microbe: нет italic
- [Ubuntu Mono](https://www.programmingfonts.org/#ubuntu)
	- 13, 14, 15, 16, 17, 18, 23

### Rest

- [Atkinson Hyperlegible Mono](https://www.programmingfonts.org/#atkinson-hyperlegible)
	- :microbe: not squarish
	- :sparkles: Разработан для читаемости
	- 12, 14, 15, 16, 17
- [Adwaita Mono](https://www.programmingfonts.org/#adwaita-mono)
	- 14
- [Aporetic Sans Mono](https://www.programmingfonts.org/#aporetic-sans)
	- На 11 нравится, что точка i смещена вправо
	- 13, 14, 15
- [-] [Azeret Mono](https://www.programmingfonts.org/#azeret)
	 - 12
- [CamingoCode](https://www.programmingfonts.org/#camingocode)
	- :thinking_face: not so squarish
	- 11, 12, 13, 14 норм, 15, 16, 17, 18, 19
- [Code New Roman](https://www.programmingfonts.org/#code-new-roman)
	- :microbe: Looks good but not for fast reading
- [Courier Prime](https://www.programmingfonts.org/#courier-prime)
	- 12, 14, 15
	- :thinking_face: С засечками
- [Cousine](https://www.programmingfonts.org/#cousine)
	- 12, 13
	- :thinking_face: Выглядит чуть по-детски
- [Cozette](https://www.programmingfonts.org/#cozette)
	- 12, 21
	- :microbe: Не нравится `X` на многих размерах (тонкая пиксельная)
- [Droid Sans](https://www.programmingfonts.org/#droid-sans)
	- :microbe:  что с `w` внизу?
- [Fairfax HD](https://www.programmingfonts.org/#fairfax-hd)
	- :thinking_face: Хороший, но скучный
- [Go Mono](https://www.programmingfonts.org/#go-mono)
	- 9 (!), 12
	- :microbe: Засечки
- [Google Sans Code](https://www.programmingfonts.org/#google-sans-code)
	- 9, 10, 11, 13, 15
	- :microbe: not squarish
	- :microbe: Стрёмные фигурные скобки
- [Input Mono](https://www.programmingfonts.org/#input)
	- 13, 16 (жирновато)
- [Ioskeley Mono](https://www.programmingfonts.org/#ioskeley)
	- 12, 14
- [JetBrains Mono](https://www.programmingfonts.org/#jetbrainsmono)
- [-] [Liberation Mono](https://www.programmingfonts.org/#liberation)
	- 11, 12, 13, 14
	- :microbe: Слишком широкий
- [Lilex](https://www.programmingfonts.org/#lilex)
	- С засечками, но почти не тормозит чтение
	- :sparkles: Красивый
	- 14, 25
- [Luculent](https://www.programmingfonts.org/#luculent)
	- Якобы простой, чуть детский
	- 12, 13, 15, 18
- [Mensch](https://www.programmingfonts.org/#mensch)
	- 14 норм, 20, 26
- [Miracode](https://www.programmingfonts.org/#miracode)
	- 16
	- :microbe: Вытянутый по горизонтали
	- Напоминает Starcraft
- [Lyth Mono](https://www.programmingfonts.org/#lyth-mono)
	- 13, 14
- [Monaspace Radon](https://www.programmingfonts.org/#monaspace-radon)
	- Прикольно выглядит, типа, рукописный
- [MonoLisa](https://www.programmingfonts.org/#monolisa)
	- 12, 13, 14, 15
	- Тоже жирный?
- [-] [Nanum Gothic Coding](https://www.programmingfonts.org/#nanum-gothic-coding)
	- 15, 17,
	- :microbe: Нет рус. букв
- [Nordwand Mono](https://www.programmingfonts.org/#nordwand-mono)
	- 11, 12, 13, 17 норм
	- Тоже жирный?
- [Noto Sans Mono](https://www.programmingfonts.org/#noto)
	- 12, 13, 14 терпим, 16, 17 жирноват
- [Proggy Clean](https://www.programmingfonts.org/#proggy-clean)
	- 15, 16, 18
	- Маломерящий
- [psudoFont Liga Mono](https://www.programmingfonts.org/#psudo)
	- 14, 16, 23
	- Жирноват?
- [saxMono](https://www.programmingfonts.org/#sax)
	- 13, 14, 16, 17
	- :microbe: Почему-то буквы "прыгают" при изменении размера шрифта
- [Sometype Mono](https://www.programmingfonts.org/#sometype-mono)
	- 15, 16, 23
	- Маломерящий
- [Sono](https://www.programmingfonts.org/#sono)
	- 13, 15 не оч.
- [-] [Spleen](https://www.programmingfonts.org/#spleen)
	- 15, 16, 17, 18
	- :sparkles: Ассоциация с роботом, ретрофутуризмом. Необычное начертание
	- :microbe: No cyrillic
	- Had to use `{ "editor.fontFamily": "Spleen 16x32", "editor.fontSize": 16.0, }` in VSCode
- [-] [UnifontEx](https://www.programmingfonts.org/#unifontex)
	- 13
	- :microbe: Не нравится `X` на многих размерах (тонкая пиксельная)

Прибавлял в конец для теста:

```
'Русские буквы'






__TEST__ '01234567890'
```