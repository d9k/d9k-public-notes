# Linux init systems compare

- :tv: [Сравнение скорости всех систем инициализации | Ampersand | YT](https://www.youtube.com/watch?v=XaNTJSpMBoE), 2023
	- dinit - best. sinit - инициализация без многого (напр., без инета)
	- s6, OpenRC, runit - pretty fast

- :tv: [Linux Init Systems Compared! (SystemD, OpenRC, Runit) / DenshiVideo / YT](https://youtube.com/watch?v=k1Wh8sWR8v0), 2020

- https://systemdfree.com/
	- One Process. One Purpose: An init system should start processes, supervise them, and stop them. Not manage DNS, log daemons, network configuration, login sessions, time synchronization, and device events under a single monolithic binary with 1.4 million lines of code.
	- Transparency is Not Optional: Service management should be auditable by any user with a text editor and basic shell skills. Shell scripts are documentation. Binary unit files compiled into journal logs are not. Your init should never require a PhD to debug.

- :tv: [Init Systems / dacctal / YT](https://youtube.com/watch?v=LGCJefnJkG4), 2026

	- SystemD is bloated
	- 1:13 SystemV