# linux-5.0-c-project
Atlas Analyzable C project of Linux 5.0

This respository corresponds to an Eclipse C project for the Linux kernel version 5.0 (https://cdn.kernel.org/pub/linux/kernel/v5.x/linux-5.0.tar.gz).

* The current project contains Atlas specific files including:
(1) .atlas-settings/build-configuration.xml: for the list of files (i.e., translation units) to be mapped.
(2) .atlas-settings/project-build-settings: the global list of settings for code mapping.

* To create specific build configuration, the current project needs to compiled in a Linux OS as it works like a charm using the following commands: (the current project on the repository is built with allmodconfig option. If you want to use allmodconfig, then you don't need to do anything, just import the project as an existing project in eclipse)
(1) make mrproper
(2) The proper configurations (refer to: http://www.makelinux.net/books/lkd2/ch02lev1sec3)
    (a) make defconfig # for the default configurations 
    (b) make allmodconfig # for enabling all possible modules for the build
(3) make V=1 # "V=1" enables echoing the executed command, so that Atlas Error Parser can pick up the build commands for constructing the proper build configurations for code mapping. This option can be set in the "Project Properties" window for proper compilation.

* MacOS filesystem is known to be case-insensitive. This will cause problems with cloning this repository. To overcome this problem, we suggest the following steps:
    (1) Launch Disk Utility
    (2) Choose "New Image"
    (3) Enter a nice Name for your Volume, e.g "Linux-5.0-Project"
    (4) Set the size to something that will most likely fit your needs (1000 MB)
    (5) Select "Mac OS Extended (Case-sensitive, Journaled)" in "Format".
    (6) Select "Single Partition - Apple Partition Map" in "Partitions"
    (7) Ensure "sparse bundle disk image" is set in "Image Format".
    (8) Save it somewhere on your hard drive
