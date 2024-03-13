# POC-for-writing-publish-C-modules-GNU-Linux-Windows-MAC-OS
POC for writing &amp; publish C++ modules GNU/Linux / Windows / MAC OS

C++ has lots of issues which are not dealt with in the kernel.

Problems in linking.

Exception handling that needs to be turned off.

Memory management functions (like new and delete) which need to be implemented.

The kernel headers are not suitable for inclusion for a C++ compiler since they conflict with many C++ constructs ('class' for instance and more).

The kernel build system does not compile C++ correctly, or even at all.

separate the "top part" - the one that is getting called by Linux, like driver entry and exit points, interrupt functions, tasklets, whatever and handle them in a C layer. expose APIs for all of these facilities and other low level facilities (printk, hardware access and more) via C functions.

write a top part that only accesses these services by well controlled C functions which do not include the kernel headers and are C++ friendly. In the top part write a framework for device driver writing based on OO concepts (inherit from Device and implement the relevant methods).

Add ability to include header files directly in C++ code. Progress: have 'copy_headers' target in makefile which also applies patch but headers are still hard to work with... This is to be developed as a patch to the linux kernel (big project - watch out! may never happen...)

Order at nkinda.com 
Mail: support@nkinda.com

