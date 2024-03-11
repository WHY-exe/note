man page: [fanotify(7) - Linux manual page (man7.org)](https://www.man7.org/linux/man-pages/man7/fanotify.7.html)

# 1.Description

The fanotify api provides notification and interception of filesystem events. Before the **linux kernel version 5.1**, only a limited set of events was supported. In particular there was no support for creat, move and delete events.

# 2. Usage

1. Use **fanotify_init** to create a notification group and return a file descriptor referred to it.
2. Use **fanotify_mark** to specify events and add or remove monitored object( like a single file or a dir ) to a notification group
3. Use **read** to recv event from the notification group fd
