#### What is Linux?
* Linux is kernel that powers Linux OS
* Kernels are programs that talk directly to hardware and manage resources and processes
* Kernels need whole OS to be useful
* Kernel bundled with OS software and shipped together is Linux Distribution

#### Linux Distributions:
* Red Hat Family - they created rpm, where all pacakges comes as rpm packages and there is database which keeps track which packages are installed and each rpm can tell what it's dependencies are.
* Debian Family - deb packages instead of rpm, more focus on end user experience whereas red hat has more focus on corporate world
* Source Code Distributions - more customizable than red hat and debian
* System V Init vs SystemD

* System V Init - After kernel loads up, it's the first process that starts, it starts up other processes. It's the old way as it was sequential and used to take up lot of time.

* SystemD - SystemD starts things parallely and is newer and better way

#### Partitions:
* Hard Drive can be partitioned into various volumes and OS can be installed in any of these volumes
* Normally Bootloader is installed on the beginning part of hard drive
* Swap Partitions: It takes a portion of a hard drive and uses it as a virtual memory, so when you run out of space on your RAM it will use this partition
* Other partition types: Like LVM, etc. usually standard linux partition is enough
* [File Systems](https://phoenixnap.com/kb/linux-file-system): ([To read more in-depth](https://www.partitionwizard.com/partitionmagic/linux-file-system.html))
* Mount Point:All partitions are attached to the system via a mount point. The mount point defines the place of a particular data set in the file system. Usually, all partitions are connected through the root partition

#### [Linux Boot Process](https://www.thegeekstuff.com/2011/02/linux-boot-process/):
* BIOS starts bootloader which starts OS
