---
type: article
fc-calendar: Gregorian Calendar
fc-date: 
year: 2024
month: January
day: 31
creation date: 2024-01-31 23:22
modification date: Wednesday 31st January 2024 23:22:56
---

#internetContent  #linux 
## Article link:
[Daemon (computing) - Wikipedia](https://en.wikipedia.org/wiki/Daemon_(computing))
related notes: 
- [[Linux - Advanced Bash Commands]]
_____
## Content

In [multitasking](https://en.wikipedia.org/wiki/Computer_multitasking "Computer multitasking") computer [operating systems](https://en.wikipedia.org/wiki/Operating_system "Operating system"), a **daemon** ([/ˈdiːmən/](https://en.wikipedia.org/wiki/Help:IPA/English "Help:IPA/English") or [/ˈdeɪmən/](https://en.wikipedia.org/wiki/Help:IPA/English "Help:IPA/English"))[[1]](https://en.wikipedia.org/wiki/Daemon_(computing)#cite_note-jargon-1) is a [computer program](https://en.wikipedia.org/wiki/Computer_program "Computer program") that runs as a [background process](https://en.wikipedia.org/wiki/Background_process "Background process"), rather than being under the direct control of an interactive user. Traditionally, the process names of a daemon end with the letter _d_, for clarification that the process is in fact a daemon, and for differentiation between a daemon and a normal computer program. For example, [syslogd](https://en.wikipedia.org/wiki/Syslogd "Syslogd") is a daemon that implements system logging facility, and sshd is a daemon that serves incoming [SSH](https://en.wikipedia.org/wiki/Secure_Shell "Secure Shell") connections.

In a [Unix](https://en.wikipedia.org/wiki/Unix "Unix") environment, the [parent process](https://en.wikipedia.org/wiki/Parent_process "Parent process") of a daemon is often, but not always, the [init](https://en.wikipedia.org/wiki/Init "Init") process. A daemon is usually created either by a process [forking](https://en.wikipedia.org/wiki/Fork_(operating_system) "Fork (operating system)") a child process and then immediately exiting, thus causing init to adopt the child process, or by the init process directly launching the daemon. In addition, a daemon launched by forking and exiting typically must perform other operations, such as dissociating the process from any controlling [terminal](https://en.wikipedia.org/wiki/Tty_(Unix) "Tty (Unix)") (tty). Such procedures are often implemented in various convenience routines such as _daemon(3)_ in Unix.

Systems often start daemons at [boot](https://en.wikipedia.org/wiki/Booting "Booting") time that will respond to network requests, hardware activity, or other programs by performing some task. Daemons such as [cron](https://en.wikipedia.org/wiki/Cron "Cron") may also perform defined tasks at scheduled times.