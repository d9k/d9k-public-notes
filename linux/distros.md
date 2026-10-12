# #Linux #distribution<span>&hairsp;s</span>

- 2024.07 / 2024.06

- :tv: [Why Your Linux Distro Matters … | Michael Horn | YT](https://www.youtube.com/watch?v=L58loyGQ6HY)
- [Polls | DistroWatch](https://distrowatch.com/polls.php)

- dister
	- [Jackson Novak / Rebos · GitLab](https://gitlab.com/Oglo12/rebos)
	- reproducible system install, any system

- :tv: [Сравнение скорости всех систем инициализации | YT](https://www.youtube.com/watch?v=XaNTJSpMBoE)
	- dinit - best. sinit - инициализация без многого (напр., без инета)

- :tv: [Linux Sucks 2024 | Bryan Lunduke | YT](https://www.youtube.com/watch?v=58mLZyShQjQ)

- :tv: [Native Linux Gaming Has Problems … | YT](https://www.youtube.com/watch?v=DHVHauqRmts)

- :tv: [Sometimes, I get tired of Linux | The Linux Experiment | YT](https://www.youtube.com/watch?v=a2YZ9GwSkxI)
	- Linux desktop environments matured. Updates loosed wow-factor. Sure getting new socks on a birthday is fine but it's not

## :scroll: #list

- https://distrowatch.com/dwres.php?resource=popularity
- [DistroWatch Project Ranking (>100 reviews)](https://distrowatch.com/dwres.php?resource=ranking)
- :tv: [The Linux Tier List | Christ Titus Tech | YT](https://www.youtube.com/watch?v=KyADkmRVe0U&t=1220s)
- [DistroWatch Project Ranking (>10 reviews)](https://distrowatch.com/dwres.php?resource=ranking&sort=average10)
- :tv: [What Your Linux Distro Says About You in 2025 | The Linux Cast | YT](https://www.youtube.com/shorts/ImtoYNt8lFw)

## #theory

- :tv: [5 Common Mistakes New Linux Users Often Make | Learn Linux TV | YT](https://www.youtube.com/watch?v=nY9dVJ2EnSk)
- :tv: [LINUX KERNEL variants explained: Zen, Xanmod, TKG, RealTime, Liquorix... | YT](https://www.youtube.com/watch?v=_idZGJ1NgPE)

- [ ] deb / yum / pacman difference?

- :tv: [100+ Linux Things you Need to Know | Fireship | YT](https://www.youtube.com/watch?v=LKCVKw9CzFo&t=4s)
- immutable distro
	- [ ] :tv: [uBlue Linux: Immutable Fedora With Batteries Included | YT](https://www.youtube.com/watch?v=HsKKh3WS1q0)
	- [What are immutable distros, and are they the future of Linux? - YouTube](https://www.youtube.com/watch?v=9hiPFEUoUyI&t=86s)

- atomic desktops
	- [ ] :tv: [Atomic Desktops | Chris Titus Tech | YT](https://www.youtube.com/watch?v=1vSFR8bi0YQ)
	- [ ] :tv: [Fedora Linux Unveils Fedora Atomic Desktops | YT](https://www.youtube.com/watch?v=Xyitrd8Aal0)

- cloud native
	- [ ] :tv: [The Cloud Native Linux Desktop Model | YT](https://www.youtube.com/watch?v=vZ1LRe_foJY&t=169s)
		- `/usr` - readonly, isolated
			- Silveblue, endless OS, OpenSUSE MicroOS
			- docker/podman for apps
			- GUI apps: flatpak, flatseal
			- state only at /etc, /var, /home
				- no need system cleaners
			- user space: Distrobox, toolbox

- [toolbox](https://github.com/containers/toolbox) by [containers](https://github.com/containers)
	- _Tool for interactive command line environments on Linux_
	- Toolbx is installed by default on Fedora Silverblue and Workstation
	- install at user-space level

- [bubblewrap](https://github.com/containers/bubblewrap) by [containers](https://github.com/containers)
	- _Low-level unprivileged sandboxing tool used by Flatpak and similar projects_

## Install multiple versions of same package

- (Σ) 1. Install as usual. 2. Install appimage/flatpak/snap if old version is necessary

- :mag_right: install old version alongside
- NixOS
- snap

- [apt - Can multiple versions of the same package co-exist on the same system? - Ask Ubuntu](https://askubuntu.com/questions/758502/can-multiple-versions-of-the-same-package-co-exist-on-the-same-system)
- [Is it possible to install multiple version of the same package? : r/linux4noobs](https://www.reddit.com/r/linux4noobs/comments/1bjxiem/is_it_possible_to_install_multiple_version_of_the/)
	- RPM supports multiple installations, as long as there are no file conflicts. (So, either no files in common, or files match exactly.)
- [ubuntu - Can I have two versions of the same package in an apt repository? - Server Fault](https://serverfault.com/questions/279329/can-i-have-two-versions-of-the-same-package-in-an-apt-repository)
	- You can't install two packages with the same name but different versions. Packages need to have different names to be installed together.

- [Nix support in Apx has landed! - Vanilla OS](https://vanillaos.org/blog/article/2023-02-07/nix-support-in-apx-has-landed)
	- Nix has now integrated with apx using a flag, which allows users to install software from Nix repositories.
		- `apx install --nix htop`

## Debian-based

- [CreatePackageFromPPA - Debian Wiki](https://wiki.debian.org/CreatePackageFromPPA)

- :tv: [DEBIAN - САМЫЙ СТАБИЛЬНЫЙ LINUX? Честный обзор Debian на десктопе: GNOME, KDE, Cinnamon. | YT](https://www.youtube.com/watch?v=ad9VkhVncN8)

- [Bodhi Linux](https://www.bodhilinux.com/)
	- :beginner: [Upgrade | Keeping Bodhi Linux Up-to-Date - Bodhi Linux](https://www.bodhilinux.com/w/keeping-bodhi-linux-up-to-date/)
	- :speech_balloon: [Bodhi Forum](https://www.linuxquestions.org/questions/bodhi-92/)
	- [Download - Bodhi Linux](https://www.bodhilinux.com/download/)
	- [Selecting the Correct ISO Image - Bodhi Linux](https://www.bodhilinux.com/w/selecting-the-correct-iso-image/#AppPack)
	- Moksha Desktop
		- :dromedary_camel: [moksha](https://github.com/JeffHoogland/moksha) by [JeffHoogland](https://github.com/JeffHoogland)
			- _Moksha is a fork of Enlightenment DR17 desktop_
		- Cool, green-black theme
			- [Green Theme - Bodhi Linux](https://www.bodhilinux.com/a/green-theme/)
		- [ ] panel can rotate?
		- Thunar file manager
		 - Epiphany web #browser
		 - :speaking_head_in_silhouette: [Is it possible to show first letters of running windows titles in **vertical** shelf?](https://discord.com/channels/274702482473746432/353945066168909846/1257882209122123878)
	- Slow install.
		- `Preparing to completely remove...` ?

- antiX
	- [DistroWatch.com: antiX](https://distrowatch.com/table.php?distribution=antix)
	- System V, no `journalctl`
	- :tv: [antiX 19.4 - Linux с Позитивной аурой. AV Linux - для создания аудио и видео. Легкие и быстрые | YT](https://www.youtube.com/watch?v=QNXlEWvDhXw), 2021
		- 1:55 Отличия среды рабочего стола от оконного менеджера?
		- 2:30 Rox-IceWM
		- 3:15 Кастомизир. ядро Linux со своими патчами
		- 9:15 AVL MXE Assistant
	- :tv: [AntiX Vs Puppy Linux - Which One Is Better? | YT](https://www.youtube.com/watch?v=IXJCt_jhDYs)
		- 3:30 IceWM, JWM, Fluxbox

- [DistroWatch.com: Devuan GNU+Linux](https://distrowatch.com/table.php?distribution=devuan)
	- [Welcome to devuan.org | Devuan GNU+Linux Free Operating System](https://www.devuan.org/)
	- _Runit and openrc are quarter-implemented on this distro, whereas Artix and Void and even antiX have accomplished more_
	- [Peppermint OS - Wikipedia](https://en.wikipedia.org/wiki/Peppermint_OS)
		- based on Devuan

- [DistroWatch.com: Parrot](https://distrowatch.com/table.php?distribution=parrot)
	- security-oriented distribution featuring a collection of utilities designed for penetration testing, computer forensics, reverse engineering, hacking, privacy, anonymity and cryptography
- [DistroWatch.com: SpiralLinux](https://distrowatch.com/table.php?distribution=spiral)
- [DistroWatch.com: Endless OS](https://distrowatch.com/table.php?distribution=endless)
	- simplified and streamlined user experience using a customized desktop environment forked from GNOME 3. Rather than using a traditional Linux package management system, Endless OS uses a read-only root filesystem managed by OSTree with application bundles overlaid on top.
		- [ostreedev/ostree: Operating system and container binary deployment and upgrades](https://github.com/ostreedev/ostree)
	- установщик стирает файлы на диске целиком
- [ExLight Linux | Run a real fast Linux Live system!](https://exlight.exton.net/)
	- very lightweight (400 mb RAM)
- [DistroWatch.com: wattOS](https://distrowatch.com/table.php?distribution=wattos)

## Smol

- [Comparison of lightweight Linux distributions - Wikipedia](https://en.wikipedia.org/wiki/Comparison_of_lightweight_Linux_distributions)

- [Exton Linux | Live Systems](https://www.exton.se/download/)

- [Elive - Wikipedia](https://en.wikipedia.org/wiki/Elive)
	- Enlightenment desktop

- [Porteus (operating system) - Wikipedia](https://en.wikipedia.org/wiki/Porteus_(operating_system))
	- [Porteus-v5.01 is released! - Porteus](https://forum.porteus.org/viewtopic.php?f=35&t=11004)
		- [ftp.cc.uoc.gr - University of Crete / Computer Center](https://ftp.cc.uoc.gr/pub/linux/porteus/x86_64/Porteus-v5.01/)
			- LXDE, Openbox
	- :speech_balloon: [DistroWatch.com: Porteus](https://distrowatch.com/table.php?distribution=porteus)
		- Some configuration annoyances in the openbox version I use. Setting time zone did nothing so had to manually force it at startup.
	- Porteus (formerly Slax Remix) is a portable operating system based on Slackware. It does not require installation and can be run from fixed and removable media, such as a USB flash drive or compact disc.
	- Porteus Kiosk is a specialized edition of the Porteus operating system,[14] a minimalist Linux distribution for web-only terminals with Firefox (or Google Chrome, Chromium or Opera, set upon installation[15]) as the sole application.

- [Tiny Core Linux - Wikipedia](https://en.wikipedia.org/wiki/Tiny_Core_Linux)
	- providing a base system using BusyBox and FLTK.
	- RaspberryPi supported
	- :speech_balloon: [Tiny Core Linux | DistroWatch](https://distrowatch.com/table.php?distribution=tinycore)

- [Austrumi Linux - Wikipedia](https://en.wikipedia.org/wiki/Austrumi_Linux)
	- #Slackware base
	- [DistroWatch.com: AUSTRUMI](https://distrowatch.com/table.php?distribution=austrumi)
	- The entire operating system and all the applications run from RAM, making Austrumi faster than larger distributions that must read from a disk, and allowing the boot medium to be removed after the operating system has booted.

- [Bodhi Linux](https://www.bodhilinux.com/)
	- (See also at [[#Debian-based]])
	- :speech_balloon: [Lowest memory usage | /r/bodhilinux](https://www.reddit.com/r/bodhilinux/comments/1cvi7qa/lowest_memory_usage/)
		- rbtylee: _(This requires a large amount of technical knowledge and has the potential to break your system)._ Go over the list of installed packages, every single one, and uninstall whatever you do not need. Do you need a DM (ie login screen) or are you able to boot to a command line, login, and start M,oskha there? Do you really need network manager or would you be able to connect to the internet without it?
			 - Go over every single systemd service that starts or is installed. Make a decision as to whether you need it or not? If it is unneeded remove it, maybe even uninstall whatever installed it but if not at least make sure it does not start at boot.
			 - If your system still boots and works after doing the above go over all the modules that are loaded in Moksha. Unload the ones not 100% needed by you. The Places module and the Clipboard module are 2 that you could certainly unload.
			 - The Big one: compile your own kernel and make it as minimal as you can and still support your hardware with the features you need.
			- git clone EFL and moksha switch to a tty and uninstall both. Now compile and install EFL after going over all the compile options carefully and make sure it is as minimal of an install as possible. You may even want to consider using an older version of EFL that what is current. Look over EFL branches to find one that works with moksha.

- MX Linux
	- :tv: [Why MX Linux Beats Ubuntu & Fedora | YT](https://www.youtube.com/watch?v=A9Qnd6Obbgg)
		- 3:30 MXLinux LiveUSB: enable advanced option to persist
		- :tv: [MX Linux with Moksha Desktop: MX Moksha Overview | YT](https://www.youtube.com/watch?v=cvoSlNGuIu4)
		- :tv: [I Compared All MX Linux Editions | Here’s The Best One! | YT](https://www.youtube.com/watch?v=_gp8xD-q-hw)
			- 6:20 Fluxbox is the lightest

- Q4OS
	- :tv: [This Is the Best OS for Low End PCs! | Spec Tech | YT](https://www.youtube.com/watch?v=u-4Ki18Jxp0)
		- LTS: 4 years support
		- 2:20 Windows installer
		- [Trinity Desktop Environment](https://www.trinitydesktop.org/) - most Linux distros don't support it at all
		- 6:50 Window becomes transparent when moving
		- 7:00 Konqueror browser doesn't display pages well. Firefox needed.
	- 256 mb, 300 MHz, 3 gb HDD - requirements for TrinityDE?
	- :tv: [Обзор на самый дружелюбный Linux для слабого ПК | Клик Свайп | YT](https://www.youtube.com/watch?v=I4vRP7FuNS0)

- Zenwalk
	- [Zenwalk - Wikipedia](https://en.wikipedia.org/wiki/Zenwalk)
	- https://www.zenwalk.org/

- Loc-OS
	- [DistroWatch.com: Loc-OS](https://distrowatch.com/table.php?distribution=locos)
	- :tv: [Can this Linux distro resurrect my tiny laptop from 2010? | foci | YT](https://www.youtube.com/watch?v=OMl69uCu6jY)
		- 64 Linux vesion bit works faster

- KNOPPIX
	- [DistroWatch.com: KNOPPIX](https://distrowatch.com/table.php?distribution=knoppix)

- Alpine
	- :tv: [Alpine Linux - Simple, Small, and Secure | Titus Tech Talk | YT](https://www.youtube.com/watch?v=UmXNI9PcxDI)
		- _The less crap you have on a system the smaller attack surface you have_
	- OpenRC instead of SystemD
	- `man` doesn't work out of the box
	- `apk` package manager - alpine package keeper
		- very fast
	- :tv: [How to Install and Configure Alpine Linux (2027 Edition) | YT](https://www.youtube.com/watch?v=NKggFBdee94&t=72s)
		- 18:00 RAM usage
	- :tv: [Okay fine, I'll try Alpine Linux.. | YT](https://www.youtube.com/watch?v=CGoFQY1yhFA)
		- 1:40 So much targets! Works on RPi
		- 350 mb
		- 6:50 doas instead of sudo
		- 7:30 setup-desktop
		- 8:15 sound setup
		- 8:55 musl, not glib
		- 12:50 Steam, MineCraft Prism launcher: flatpak were required
	- :tv: [I Used Alpine Linux For 30 Days, Here's How It Went | PenguinByte |  YT](https://www.youtube.com/watch?v=JjctvUcQkjA)
		- Couldn't render video in video editor
		- Network Manager loses connection
	- [bubblewrap](https://github.com/containers/bubblewrap) by [containers](https://github.com/containers)
		- _Low-level unprivileged sandboxing tool used by Flatpak and similar projects_


- OpenWRT
	- [Unable to install xorg-server - Installing and Using OpenWrt - OpenWrt Forum](https://forum.openwrt.org/t/unable-to-install-xorg-server/158114/2)
		- You cannot install a graphics server on OpenWrt. The fundamental dependenceis are not available for OpenWrt and would likely take years to develop (and nobody is interested in doing this).

- Tails
	- incognito-mode OS

### EasyOS

- [DistroWatch.com: EasyOS](https://distrowatch.com/table.php?distribution=easyos)
- :tv: [EasyOS Part8: Easy Containers | YT](https://www.youtube.com/watch?v=VQk8ftYQaeI&list=PLUgReYPhPVl4ZVFLLQXnDdCoPk18FVrmH&index=17)
	- 4:00 OverlayFS
	- 5:05 merging files explanation
	- 10:10 Running container
- [ ] :tv: [EasyOS Part13: Version Control | YT](https://www.youtube.com/watch?v=yAM_7gAJvw8&list=PLUgReYPhPVl4ZVFLLQXnDdCoPk18FVrmH&index=12)
- [ ] :tv: [EasyOS Part17: Crippled root | YT](https://www.youtube.com/watch?v=Yju1w_Mjmbk&list=PLUgReYPhPVl4ZVFLLQXnDdCoPk18FVrmH&index=8)
	- :zap: `ec-chroot excalibur easy`
	- 3:20 removing specific Linux capabilities from container
- :tv: [20 лет МАТЕРИНКЕ! Устанавливаю EasyOS LINUX! Не ожидал такого в 2024 году!!! | YT](https://www.youtube.com/watch?v=O-2sXOjP8Cs)
- The distribution features custom container technology called Easy Containers which can run applications or the entire desktop environment in a container.
- :beginner: [How and why EasyOS is different](https://easyos.org/about/how-and-why-easyos-is-different.html)
	- Easy containers: Easy runs each non-root app as its own user. For example, by default Firefox runs as user 'firefox',
- Работа под Root, но приложения в контейнерах сбрасывают права ради безопасности.
- :speech_balloon: [DistroWatch.com: Put the fun back into computing. Use Linux, BSD.](https://distrowatch.com/dwres.php?resource=ratings&distro=easyos)
	- The desktop is JWM, not quite as flexible as some, but very lightweight. I was unable to pin icons on the stock taskbar, so I added an app dock, deleted some desktop icons, and put some others in the new dock. None of that was difficult.
- [EasyOS: An Experimental Distro With Unique Qualities](https://news.itsfoss.com/easyos/)
- :tv: [Barry Kaulder's 'flagship' system, "EasyOS".... | YT](https://www.youtube.com/watch?v=SZgJy93ivjM)
	- (Σ)  not very useful video, but shows some bugs

### PuppyLinux

- [DistroWatch.com: Puppy Linux](https://distrowatch.com/table.php?distribution=puppy)
- as root напрягает, отбрось это. Система не должна быть умнее пользователя
- :tv: [AntiX Vs Puppy Linux - Which One Is Better? | YT](https://www.youtube.com/watch?v=IXJCt_jhDYs)
	- 3:10 Puppy Linux runs as root by default.
	  On shutdown asks to save session on folder
- :tv: [Bring An Ancient Computer Back To Life Install Puppy Linux in Minutes! | YT](https://www.youtube.com/watch?v=Fdrc-1WD4lw)
- :tv: [BionicPup | Linux for an Old Laptop | YT](https://www.youtube.com/watch?v=aJcWcQ8ew6Q)
- [How to setup Root with password? - Puppy Linux Discussion Forum](https://forum.puppylinux.com/viewtopic.php?t=4054)
	- Unlike mainstream distros, Puppy is a single-user system, and runs as 'root' by default.

## Slackware

- принцип KISS. Если что-то напрягает, отбрось это. Система не должна быть умнее пользователя
- Oldest active distrubution

- :tv: [Installing Slackware 15 | YT](https://www.youtube.com/watch?v=gHfo6U9MhIw)

- :tv: [Самый Unix'овый | Slackware (Обзор и первое впечатление) | YT](https://www.youtube.com/watch?v=yDPPfp4C5aM)
	- дрова работают после установки
	- подходит для старых ПК
- [Slackware - Wikipedia](https://en.wikipedia.org/wiki/Slackware)

- The package management system does not track or manage dependencies
	- `slapt-get` - framework for dependency resolution
	- NetBSD's pkgsrc

- [DistroWatch.com: Slax](https://distrowatch.com/table.php?distribution=slax)
	- small collection of applications, including the Chromium web browser, a text editor and a calculator

- Slackbuild
- [DistroWatch.com: Porteus](https://distrowatch.com/table.php?distribution=porteus)
- :tv: [Gaming on Slackware with Conty, the Arch Linux container application | YT](https://www.youtube.com/watch?v=yugKXXzAdqY)

- Slax

- fu11m00n
	- https://oreivd96v420wee4.umso.co/
	- Based on: Slackware, Porteus

## Ubuntu-based

- [Why are PPAs on Debian/Ubuntu disliked by many? : r/linux](https://www.reddit.com/r/linux/comments/m0xymi/why_are_ppas_on_debianubuntu_disliked_by_many/)
	- _When you add a PPA you are effectively giving root permission to any and all PPA authors. Sandboxed solutions like Flatpak and Snap are much safer and more stable in that they only relate to the specific app you actually want and they won’t make additional changes to the environment outside of themselves_

- [DistroWatch.com: Ubuntu Studio](https://distrowatch.com/table.php?distribution=ubuntustudio)
	- for creative individuals in the areas of audio production, video production, graphics design, photography and desktop publishing. It makes professional audio accessible on Linux; it uses the JACK sound server and a kernel built with a low-latency patch.
- [Ubuntu Christian Edition -- Linux For Christians](https://ubuntuce.com/)
	- :tv: [Ubuntu CE | Christian Edition (Review) | YT](https://www.youtube.com/watch?v=-s7Ro-habnU)
	- [For fellow Linux nerds: command-line Bible app (KJV). Kinda neat. 'sudo apt-get bible-kjv' : r/Christianity](https://www.reddit.com/r/Christianity/comments/2e8j5c/for_fellow_linux_nerds_commandline_bible_app_kjv/)
	- Gnome only?

- [Vanilla OS | DistroWatch](https://distrowatch.com/table.php?distribution=vanilla)
	- gnome only desktop
	- by the main developer of the bottles project
	- :tv: [Immutable Linux, without the hassle? Vanilla OS 2 Orchid | The Linux Experiment | YT](https://www.youtube.com/watch?v=PuGeR075MkE)
	- :tv: [The END of DISTRO HOPPING? All Linux distros in one single system with VanillaOS | The Linux Experiment | YT](https://www.youtube.com/watch?v=tOm_zATjgqU)
		- _best install experience_ [5:00](https://youtu.be/tOm_zATjgqU?t=300)
		- containets support gfx acceleration. native support for NVidia drivers
		- :microbe: was not able to play 3d game on opensuse container
	- :speech_balloon: [reviews of Vanilla OS | DistroWatch](https://distrowatch.com/dwres.php?resource=ratings&distro=vanilla)
		- :microbe: _for starters the installer is fairly bare-bones, not even allowing for custom partitioning or dual booting, erasing the disk is the only option._
			- [Help on manual partitioning : r/vanillaos](https://www.reddit.com/r/vanillaos/comments/18q7902/help_on_manual_partitioning/)
			- :tv: ["partition is done using GParted"](https://youtu.be/tOm_zATjgqU?t=222)
	- :speech_balloon: [Vanilla OS v2 intends to be EASY for ALL users and PCs - Puppy Linux Discussion Forum](https://forum.puppylinux.com/viewtopic.php?t=8801)
		- _having to reboot each time an application is installed_ (?)

<details>
<summary>Apx package manager</summary>
<pre>
Apx introduces a whole new paradigm in package management. The idea is to use your system only as a box for storing your files, leaving it clean of packages and limiting the risk of breaking due to incompatible, poorly constructed or conflicting packages.

It gets done by installing software inside one or more containers fully managed by Apx having restricted access to your system's resources.

One intriguing feature of Apx is it can reportedly pull in software from other distributions, apart from its Ubuntu base. It can also fetch software from Fedora's repositories and install software from Arch Linux User Repository.

Vanilla OS uses ABRoot (https://github.com/Vanilla-OS/ABRoot) to provide its immutable base and provides a tool called VSO (https://documentation.vanillaos.org/docs/vso) to handle system maintenance.
</pre>
</details>


## Mint

- :tv: [Linux Mint 22 is great, but are they trying to do too much? | The Linux Experiment | YT](https://www.youtube.com/watch?v=SO6xx-KF3qs)

## Fedora-based

- :tv: [Why Has Fedora Become So Popular? | YT](https://www.youtube.com/watch?v=SVVe40Qhaug)
	- stability, amount of software
- :tv: [Why Has Fedora Become So Popular? | YT](https://www.youtube.com/watch?v=SVVe40Qhaug), 2023
	- stable but not stale, between rolling and static releases
	- Ubuntu users move to Fedora: no innovations, UI is the same for 10 years
- [ ] [Installing plugins for playing movies and music :: Fedora Docs](https://docs.fedoraproject.org/en-US/quick-docs/installing-plugins-for-playing-movies-and-music/)
	- :zap: `sudo dnf group install Multimedia`
- supports rpm fusion (?) for additional packages
- :tv: [uBlue Linux: Immutable Fedora With Batteries Included | YT](https://www.youtube.com/watch?v=HsKKh3WS1q0)

### Bluefin

- [DistroWatch.com: Bluefin](https://distrowatch.com/table-mobile.php?distribution=bluefin)
	- _If you edit video, you can even install DaVinci Resolve just by typing "ujust install-resolve", and it'll be installed into a preconfigured Distrobox. Installing Resolve on Linux is infamously a bit of a minefield._
	- _Coming from Arch and tired of having to built my own system, this seems to be the "Linux Mint" substitute, as there is absolutely no maintenance with it._

## OpenSuse

- [Shared post - Don't wave the LGBT flag?  SUSE & openSUSE says you are "Rotten Flesh".](https://lunduke.locals.com/post/5815715/dont-wave-the-lgbt-flag-suse-opensuse-says-you-are-rotten-flesh)

- :tv: [Ubuntu, Debian, or openSUSE? Is openSUSE the Best Linux Distribution ... you decide? | YT](https://www.youtube.com/watch?v=XvDXGn6_qIU) (2021)
	- leading contriburor to KDE environment
	- btrfs: snapshots, RAID, self-healing
	- very configurable GUI installer
	- [openSUSE 12.1: Chapter 12. Installing Multiple Kernel Versions](http://open-suse.ru/opensuse-doc/cha.tuning.multikernel.html)
		- multiple kernels, multiversion packages
- :tv: [Why I Love openSUSE | YT](https://www.youtube.com/watch?v=uB4SHNeMv-w&list=PL4d6Lj0GrDECKe0Px1U0GWI3PtZ3fLR_w)
	- BTRFS by default
		- `sudo snapper list`
	- rolling release but with delay for stability
	- OpenBuildService
		- `opi` searches

## NixOS

- :tv: [NixOS: A peak at a MASSIVE rabbit hole! | YT](https://www.youtube.com/watch?v=mA74I2IUfR0)
	- NixOS conf better be stored in CVS, but `system.copySystemConfiguration` exists for simple cases
	- system has to be dynamically generated. During that process library linking and other hacks are used.
	- nix package manager is event slower than dnf
	- to install package unknown in #Nix repos you must fix all it's environment dependencies manually
	- home manager, flakes
	- :sparkles: cool theoretically: declarative builds & deployments
	- :microbe: inconvenient practically: massive configs, weird liniking, slow package manager
- [ ] :tv: [NixOS gaming | best DE and Linux distro | YT](https://www.youtube.com/watch?v=DP-3E1FaBfo)
	- :sparkles: good instruction
- :tv: [NixOS is Mindblowing | Chris Titus Tech | YT](https://www.youtube.com/watch?v=fuWPuJZ9NcU)
- [ ] :tv: [Is NixOS The Best Gaming Distro | Linux Gaming Setup | YT](https://www.youtube.com/watch?v=qlfm3MEbqYA)
- [ ] :tv: [NixOS - Полный Разбор: Nixpkgs, Flakes, home-manager | YT](https://www.youtube.com/watch?v=HOq7XTygAAU)
- :tv: [NixOS Gaming Setup and Comparison | YT](https://www.youtube.com/watch?v=wpS3qIprHL0)
- [NixOS Search - Packages](https://search.nixos.org/packages)
- [7 advantages | Explore | Nix & NixOS](https://nixos.org/explore/)
- try apps temporarily
- :tv: [NixOS Has One BIG Problem | YT](https://www.youtube.com/watch?v=i6wSn8OlBNc)
	- not for new users
	- do things in different, unexpected way
	- bad doc, assume prior knowledge of certain things, need to know technical terms to google the solution
- :newspaper: [NixOS Story By Jesse Smith | DistroWatch](https://distrowatch.com/weekly.php?issue=20240401#nixos)
- :tv: [HOW to REALLY learn NixOS | YT](https://www.youtube.com/watch?v=1ED9b7ERTzI)
- installing packages
	- [Example package: ardour | Nixhub](https://www.nixhub.io/packages/ardour)
	- :beginner: [KDE - NixOS Wiki](https://nixos.wiki/wiki/KDE)
	- [Searching and installing old versions of Nix packages – Marcelo Lazaroni – Developing for the Interwebs](https://lazamar.github.io/download-specific-package-version-with-nix/)
		- https://www.nixhub.io/
- :scroll::beginner: IogaMaster course
	- [ ] :tv: [HOW to REALLY learn NixOS | YT](https://www.youtube.com/watch?v=1ED9b7ERTzI)
	- [ ] :tv: [Direnv in 2 minutes | YT](https://www.youtube.com/watch?v=lz2qbtWZu90)
	- [ ] :tv: [The ULTIMATE guide to Nixpkgs | YT](https://www.youtube.com/watch?v=3hMIqxbQBRM)
	- [ ] :tv: [Intro to Nix | YT](https://www.youtube.com/watch?v=ua3bjgrcOg8)

## Arch

- :tv: [Why Do I Shill Arch Linux So Much? | YT](https://www.youtube.com/watch?v=lunnbdFdPJE)
- [BlendOS | DistroWatch](https://distrowatch.com/table.php?distribution=blendos
	- automates installing software from supported distributions (Arch, Fedora, and Ubuntu) into containers
	- immutable distro
	- :door: [Home - blendOS](https://blendos.co/)
	- :tv: [Blend OS - The Perfect Blend Of Linux Distros, Android Apps & Web Apps | YT](https://www.youtube.com/watch?v=i4Zj86uDmN4)
	- :tv: [Обзор BlendOS 2 Avial/ Самый лучший дистрибутив ?/ Поддержка Android | YT](https://www.youtube.com/watch?v=xUOTjpHCl9o)
	- :tv: [BlendOS - Arch, Debian, Android in ONE DISTRO! | YT](https://www.youtube.com/watch?v=Sjd_aqLnxYo&t=1134s)

- [ ] Alternative: EndeavourOS ("Manjaro done right")
	- :speech_balloon: [Is there any stable/LTS distro based on Arch? | /r/DistroHopping](https://www.reddit.com/r/DistroHopping/comments/1kwvzjf/is_there_any_stablelts_distro_based_on_arch/)
		- Man-in-Oslo: Try Endeavour OS with LTS kernels.

- [Exodia OS](https://github.com/Exodia-OS)
	- A highly customized arch-based distro For All Cybersecurity fields
	- bspwm windows manager
- [DistroWatch.com: CachyOS](https://distrowatch.com/table.php?distribution=cachyos)
	- focuses on speed and security optimisations - the default Linux kernel is heavily optimised using the BORE (Burst-Oriented Response Enhancer). Compiled with security flags.
	- [Let's Install Linux | cachy os - YouTube](https://www.youtube.com/watch?v=4ks1j5wSQVY)
- [DistroWatch.com: ArcoLinux](https://distrowatch.com/table.php?distribution=arco)
	- [arcolinuxb/arco-budgie](https://github.com/arcolinuxb/arco-budgie)
- [DistroWatch.com: ArcoLinux](https://distrowatch.com/table.php?distribution=arco)
	- [ArcoLinux | News and information about ArcoLinux](https://www.arcolinux.info/)
- [DistroWatch.com: Archman GNU/Linux](https://distrowatch.com/table.php?distribution=archman)

## Gaming distros

- :tv: [Linux Gaming 2023 | Linux на простом языке #0 | YT](https://www.youtube.com/watch?v=cSs192tYUf0)
- :tv: [Native Linux Gaming Has Problems … | Low Budget Linux Gaming | YT](https://www.youtube.com/watch?v=DHVHauqRmts)

- Fedora-based
	- [ ] :scroll: :tv: [Linux Gaming 4 Noobs - Choosing a Distro in 2024 | YT](https://www.youtube.com/watch?v=byz8YPzczxg)
	- [ ] [Bazzite Vs Nobara - Bazzite - Universal Blue](https://universal-blue.discourse.group/t/bazzite-vs-nobara/830)
	- The biggest difference is that Bazzite uses Fedora Atomic 25 as opposed to the “Workstation” Fedora base. Nobara’s filesystem does not have read-only root files while Bazzite does.
	- Nobara is maintained by only 1 dude
	- [Why "Nobara" as a name? : r/NobaraProject](https://www.reddit.com/r/NobaraProject/comments/1aty9t2/why_nobara_as_a_name/)
		- _the creator(s) really liked Nobara Kugisaki_
- [ ] [ChimeraOS](https://chimeraos.org/)

- [ ] SteamOS
	- Arch, BTW
	- [Why did they choose KDE Plasma as a Desktop Environment for SteamOS? :: Steam Deck General Discussions](https://steamcommunity.com/app/1675200/discussions/0/3319736698850085211/)

## LTS distros

- [LTS distrors | DistroWatch](https://distrowatch.com/search.php?ostype=All&category=All&origin=All&basedon=All¬basedon=None&desktop=All&architecture=All&package=All&rolling=Fixed+%28LTS%29&isosize=All&netinstall=All&language=All&defaultinit=All&status=Active#simpleresults)

## Alt. distros

- [Kaisen Linux | The distribution for professional IT](https://kaisenlinux.org/)
	 - _provides a set of tools dedicated to system administration and covering all the needs for diagnosing and dealing with faults or failures of an installed system and its components._
- [stali linux](https://sta.li/index.html)

- Qubes OS
	- "If you're serious about security, @QubesOS is the best OS available today. It's what I use, and free." /Edward Snowden,
	- :tv: [the most secure OS in the world.....I hate it | YT](https://www.youtube.com/watch?v=i3sRSS6fN0g&t=60s)

## Gentoo

- [Slotting – Gentoo Development Guide](https://devmanual.gentoo.org/general-concepts/slotting/)
	- Через slots и eselect можно держать несколько версий одного пакета одновременно: например, python:3.11, python:3.12, gcc:12, gcc:13, llvm:16, llvm:17. Переключение — командой eselect.
	- Packages can support having multiple versions installed simultaneously.
	- Portage permits at most one instance of a package installation _per `SLOT` value_.
	- Sometimes a package installs a library that changes interfaces between versions. This situation can be handled by using sub-slots, which are delimited from the regular slot by a `/` character

- Exherbo
	- https://exherbo.org/
	- :tv: [How to Install Exherbo Linux | YT](https://www.youtube.com/watch?v=gKJu_di_Zsw), 2026
		- Fork of Gentoo

## Independent / Unique / Experimental

- [Bedrock Linux | DistroWatch](https://distrowatch.com/table.php?distribution=bedrock)
	- BedrockLinux cured me of my distroholism.

- [CRUX | DistroWatch](https://distrowatch.com/table.php?distribution=crux)

- [Home | Carbs Linux](https://carbslinux.org/)

- [Redox - Your Next(Gen) OS - Redox - Your Next(Gen) OS](https://www.redox-os.org/)
	- Rust

- Void linux
	- :tv: [Void Linux and why it is home | Jake@Linux | YT](https://www.youtube.com/watch?v=rpiThzdDLXQ)
		- runit - fast boot
		- better then Arch community
	- :tv: [🗿 Честный Обзор на Void Linux | YT](https://www.youtube.com/watch?v=GtcF7Mj0GC0)
		- xbps package manager
		- runIt init
		- musl libc - alt. glibc
		- создано разрабом из NetBSD
		- musl несовместим с Wine/Steam/проприетарными бинарника

- Gobolinux
	- https://gobolinux.org/
	- :fallen_leaf: outdated
	- distro by `htop` creator friend
	- [NixOS vs GoboLinux](https://gobolinux-users.gobolinux.narkive.com/GpgnY2Bc/nixos-vs-gobolinux)

- [-] [Clear Linux | DistroWatch](https://distrowatch.com/table.php?distribution=clear)
	- :fallen_leaf:
	- Gnome only?
	- :tv: [The History of Clear Linux | YT](https://www.youtube.com/watch?v=13CxUbumzPA)
	- :tv: [Why Clear Linux OS? | YT](https://www.youtube.com/watch?v=VxA-vim715w)
	- от Intel
	- немного быстрее
	- free security scanner
	- lightweight delta updates
	- :tv: [Clear Linux 35000 (GNOME 40.4) | YT](https://www.youtube.com/watch?v=Jv_p7MF4bP0)


## RedHat

- [Rocky Linux — Википедия](https://ru.wikipedia.org/wiki/Rocky_Linux)[Rocky Linux — Википедия](https://ru.wikipedia.org/wiki/Rocky_Linux)
	- 8 декабря 2020 г. Red Hat объявила о прекращении разработки CentOS, которая была готовой к производству нисходящей версией Red Hat Enterprise Linux , в пользу более нового варианта разработки этой операционной системы, известного как «CentOS Stream».  В ответ первоначальный основатель CentOS Грегори Курцер объявил, что он снова начнет проект для достижения первоначальных целей CentOS.  Его название было выбрано в честь одного из первых соучредителей CentOS Рокки Макгоу. К 12 декабря репозиторий кода Rocky Linux стал самым популярным репозиторием на GitHub.

## Российские ОС

- :tv: [Недостатки РОСА ОС Linux и других российских операционных систем | YT](https://www.youtube.com/watch?v=674_0hzDLSM)
- :tv: [РОССИЙСКИЕ LINUX: Топ 3 и кому нужны? | YT](https://www.youtube.com/watch?v=RhNx57U5How)

- Alt Linux
	- работает на российских процессорах Эльбрус
	- :beginner: [В самом начале ... | ALT Zero](https://plafon.gitbook.io/alt-zero)
	- :tv: [ALT linux - что нового в 11 платформе и что мы имеем в текущей p10 | YT](https://www.youtube.com/watch?v=1JCj7mH9uwY)
	- `epm` пакетный менеджер
	- :tv: [100 лет на Линуксе (2025) | PLAFON | YT](https://www.youtube.com/watch?v=2eA_eqkX-bM)
	- :heavy_dollar_sign:[Base\_prices.pdf](https://www.basealt.ru/fileadmin/user_upload/pdf/Base_prices.pdf)
		- :microbe: Цены жесть
- РОСА Linux
	- :tv: [Недостатки РОСА ОС Linux и других российских операционных систем | YT](https://www.youtube.com/watch?v=674_0hzDLSM)
	- Нет скриншотов программ в центре приложений как в Ubuntu

- РедОС
	- RedWine?
		- [Работа с Wine - База знаний РЕД ОС](https://redos.red-soft.ru/base/arm/arm-other/work-in-wine/)
	- `dnf`

## Truely #OSS distros

- [Guix System | DistroWatch](https://distrowatch.com/table.php?distribution=guixsd)
	- Stateless, uses some NixOS libs
	- :tv: [Why I Choose Guix Over NixOS | YT](https://www.youtube.com/watch?v=PiAMRXYIri0)
		- 0:35 Entire system is built using Scheme language

- :scroll: [List of Free GNU/Linux Distributions - GNU Project - Free Software Foundation](https://www.gnu.org/distros/free-distros.html)

- :tv: [your Linux distro isn't FREE! (these are) | YT](https://www.youtube.com/watch?v=IGV7A6X6uCg)

- https://www.hyperbola.info/
	- #Arch - based
	- OpenRC вместо SystemD
	- :speech_balloon: [Hyperbola GNU/Linux-libre | DistroWatch](https://distrowatch.com/table.php?distribution=hyperbola)
		- For desktop users, it provides a package called lumina-desktop. It uses xenocara as the default window system. It uses sndio instead of pulseaudio or pipewire.
	- :tv: [Hyperbola GNU/Linux-libre/BSD | фанатичная преданность идеалам свободы | YT](https://www.youtube.com/watch?v=FOO4JsoZlxk), 2021
		- 3:50 Философия защиты от глобальной слежки
		- 6:30 Даже Libre-ядро Linux включает DRM. Хотят перейти на OpenBSD
		- 7:20 Распространение Rust и cargo требуют изменения версии. Mozilla уже убивала свободные проекты на этой почве
			- Upd: 2021 права были переданы Rust Fondation

- Trisquel Mini
	- :door: https://trisquel.info/en/wiki/trisquel-mini
	- 128 mb RAM!
	- образ 1.2 GB, есть NetInstall
	- LXDE + Openbox
	- :tv: [Trisquel linux лёгкий , свободный , безопасный | YT](https://www.youtube.com/watch?v=ReXd9KRjMic)
	- Полностью свободный. Trisquel не содержит в себе закрытых участков исходного кода
	- Abrowser - дебрендир. Firefox
	- нет и не будет телеметрии
	- NVidia видеокарта может не заработать
	- :tv: [Дыра в Linux, Дистрибутивы Deepin 20.4, Nitrux 2, Свободный Trisquel | YT](https://www.youtube.com/watch?v=soKYVaTckYk), 2022
		- 11:00 Появление поддержки ARM, но прекратили поддержку 32-bit


## Install package from different Linux distro

- :tv: [Gaming on Slackware with Conty, the Arch Linux container application | YT](https://www.youtube.com/watch?v=yugKXXzAdqY)

- homebrew

- Nix

- [Is there a way to use AUR on ubuntu? : r/Ubuntu](https://www.reddit.com/r/Ubuntu/comments/9sogqg/is_there_a_way_to_use_aur_on_ubuntu/)

- distrobox
	- :tv: [Stop Distro Hopping! Use this AWESOME tool on Linux | YT](https://www.youtube.com/watch?v=Sj064D9ZUl8)
	- [ ] :tv: [Distrobox Is Basically A Linux Subsystem For Linux | YT](https://www.youtube.com/watch?v=FhW-3PPldAg)
	- :tv: [New to DistroBox? Start Here: Full Beginner's Tutorial! | Learn Linux TV | YT](https://www.youtube.com/watch?v=eiDt4O6UPRw)
		- install distrobox
		- [distrobox](https://github.com/89luca89/distrobox) by [89luca89](https://github.com/89luca89)
			- Use any linux distribution inside your terminal. Enable both backward and forward compatibility with software and freedom to use whatever distribution you’re more comfortable with.
			- :zap: `wget https://github.com/89luca89/distrobox/raw/refs/tags/1.8.1.2/install; sudo sh install`
		- install podman
			- for better security
		- 6:00 `distrobox create`
		- 7:30 `distrobox --nvidia create` - expose NVidia videocard to the container
		- 8:00 `distrobox enter my-distrobox` `cat /etc/os-release`
		- 9:30 podman allows to run rootless containers.
	- :tv: [Installing Mojo🔥 on Arch/Fedora/Distrobox | Mii beta | YT](https://www.youtube.com/watch?v=MHSGphClhZw)
		- :zap: `distrobox create --image archlinux:multilib-devel --name d9k-arch-32-dev-container`
			- [x] :rotating_light: `short-name "archlinux:multilib-devel" did not resolve to an alias and no unqualified-search registries are defined in "/etc/containers/registries.conf"`
				- :zap: `sudo nvim /etc/containers/registries.conf`
					- add `sudo nvim /etc/containers/registries.conf`
				- :zap: `distrobox enter d9k-arch-32-dev-container`
					- :rotating_light: `lua: error while loading shared libraries: libreadline.so.6: cannot open shared object file: No such file or directory`
	- Check space occupied
		- :zap: `sudo du -h ~/.local/share/containers`

	- [Distrobox - ArchWiki](https://wiki.archlinux.org/title/Distrobox)
	- :newspaper:  [How to integrate any Linux distribution inside a terminal with Distrobox - Linux Tutorials - Learn Linux Configuration](https://linuxconfig.org/how-to-integrate-any-linux-distribution-inside-a-terminal-with-distrobox)
	- [Distrobox vs Toolbox? : r/Fedora](https://www.reddit.com/r/Fedora/comments/u69vr9/distrobox_vs_toolbox/)
		- _The biggest issue with Toolbox (in my opinion), is it just hands your home directory over as the container's home directory, with no way to configure this. That issue is a deal-breaker for me and makes the software completely pointless and unusable. I've also had Toolbox just randomly break on me oftn. Distrobox supports configuring the container's home directory, which immediately makes it the much better option to me. Tlbx is another superior option._
	- apx
		- There is a distro called VanillaOS, and its package manager, apx, is a wrapper around distrobox. The killer feature is that it allows to have APT, DNF and AUR on a single system.

## #christian

- [Run Live / Install | Computers4Christians](https://computers4christians.org/download/install-c4c-ubuntu/)
- [Mauna Christian Edition - Mauna Linux](https://maunalinux.top/download/mauna-christian-edition/)

## #gaming

- [Batocera.linux | DistroWatch](https://distrowatch.com/table.php?distribution=batocera)
	- :beginner: [pacman\_package\_manager \[Batocera.linux - Wiki\]](https://wiki.batocera.org/pacman_package_manager)
		- It is important to note that although this is pacman, and Arch Linux uses pacman to install its packages, it does not mean that you can install packages designed for Arch Linux inside of Batocera.
	- :speech_balloon: [adding packages to Batocera | /r/batocera](https://www.reddit.com/r/batocera/comments/17wwumb/adding_packages_to_batocera/)
		- pacman in batocera is only used for it's custom freeware downloads in the es menu. It is not connected to Arch mirrors, and batocera is made on buildroot..it's "Just Enough Linux" for its own services and not designed for addons. IOW, it's more like firmware.
		- Alternatively, you might want to try https://github.com/fsquillace/junest I haven't played with it, much but it does have pacman connected to Arch's mirrors.

- :tv: [How To Add Desktop Mode To Batocera! | YT](https://www.youtube.com/watch?v=OGQNzdf1XUk)

## #create #multiMedia

- :scroll: [DistroFinder - Find your perfect Linux distribution](https://distro-finder.com/?category=Multimedia&sort=popularity.asc)

- [KXStudio : Applications](https://kx.studio/Applications)
	- [KXStudio : Applications : Catia](https://kx.studio/Applications:Catia)
		- Catia is a JACK Patchbay, with some neat features like A2J bridge support and JACK Transport.

- :tv: [EasyEffects An equalizer and Effects App for Linux | YT](https://www.youtube.com/watch?v=h1Z3WBUD1Aw)

### Ubuntu Studio

- :tv: [Ubuntu Studio 26.04 Review | Best Free Linux OS for Creators in 2026? | YT](https://www.youtube.com/watch?v=uaxS7pAg43Y)

### AV Linux

- https://www.bandshed.net/avlinux/
- 🤖 GoogleAI: AV Linux transitioned its base from antiX/Debian to MX Linux (which itself shares underlying build tools and roots with antiX and Debian). The Change: AV Linux moved to being built upon MX Linux (starting majorly around the MX-21 / AVL-MXe releases), utilizing MX tools and Debian foundations
	- :speech_balloon: [AV Linux moving to MX Linux - LinuxMusicians](https://linuxmusicians.com/viewtopic.php?t=21782), 2020
		- The last AVL release (2020.5.10) was well received for the most part but there were still a few issues and users having difficulty with the 'Systemback' Installer and UEFI as well as problems installing to NVMe media. Over the years I've seen a few MX Linux Users who do Audio work using the AVL kernels and some folks have suggested that I use MX as a base.
		- GMaq: MX is extremely well thought out and their own additional tools, supplemental packaging and large helpful community already confirm to me this is a good step forward.
- [ ] Install nvidia drivers
	- :tv: [MX Linux 25.2 "Infinity" How to Install NVIDIA Drivers on MX Linux based on Debian 13.5 Trixie | YT](https://www.youtube.com/watch?v=aAudVTLnD8c)
- :beginner: [MX Moksha](https://www.bandshed.net/mx-moksha/)
	- +video
		- 2:00 Wi-Fi connection
- :tv: [Hello AV Linux MX Moksha ! | YT](https://www.youtube.com/watch?v=TEeLLvAPRDY)
	- AV Linux — дистрибутив Linux, рассчитанный на создателей мультимедийного контента. Доступен для архитектур i386 и x86-64, оптимизирован под максимальную производительность и производство аудио с малым временем отклика / [AV Linux — Википедия](https://ru.wikipedia.org/wiki/AV_Linux)
- :tv: [AV Linux 23.2 - Pipewire Controls Audio Information and Wine Staging | YT](https://www.youtube.com/watch?v=iGaIlY2SZIw)
- :tv: [WTF is AV Linux? | YT](https://www.youtube.com/watch?v=CIeKw_j3Jxk)

### Modica

- https://www.modiciaos.cloud/#school
- :speech_balloon: [DistroWatch.com: MODICIA O.S.](https://distrowatch.com/table.php?distribution=modicia)
	- No bluetooth or wifi for my pc. I suppose the lack of support for newer hardware cannot be fixed by any driver updates.
- :tv: [28 Killer Graphic Tools to Max Out Linux Performance! | YT](https://www.youtube.com/watch?v=jLtVfyaeZYM)