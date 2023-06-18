Picoscope docker image
======================


Basics
======

To setup host system (need to run once):

    sudo ./picocmd setup


To run picoscope (pulling image if needed):

    ./picocmd run


To build locally (not necessary if you just want to run picoscope):

    ./picocmd build


By default, an Ubuntu-based image will be used.
For run & build commands, you can specify to use an OpenSUSE-based image instead:

    ./picocmd run opensuse

Or for Ubuntu:

    ./picocmd run ubuntu


The Ubuntu-based image is the default if no distro is specified.


Save data into your home directory, which is mounted to the same path in the
container as is on the host.

Data saved anywhere else will likely be lost when the container exits.


Details
-------

This requires the host to provide docker, bash v4+, udev, X11.

This will probably not work with Wayland.

This uses docker to provide a portable userspace, NOT security or isolation.

The containers run in privileged mode, with host networking and host IPC.

Some important areas of the host filesystem are mounted into the container,
including your user home directory.

It is tested only on: Kernel 6.1 / Arch Linux / Xorg 21 / Xfce 4 / Docker 24


ARM?
----

If this works for people, and there's demand for ARM-based images, I can
probably provide those too.

This would be great for hardware-in-the-loop continuous-integration and for
remote-developement (even if just on the other side of the cleanroom walls),
via Raspberry Pi / BeagleBone / modded Android.
