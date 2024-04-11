# pyDesktopAccessibility

The goals of this project are:
- To create a python module that allows automation of desktop applications by using the operating systems Accessibility layer
- To be OS agnostic, i.e. when a user calls a function from this module it should perform the same action regardless of OS
- to be able to automate MacOS and Linux desktop applications without using image based automation, this is already possible in Windows, so the Windows support in this module will duplicate existing functionality, however I hope the OS agnostic approach here will make it worthwhile.

My purpose for creating this module is to eventually lead to a robot framework library that will wrap the functions of this module, however I hope this module will also become useful to other people for other purposes as well. I took this approach when creating the perfmon library for robot framework with pyperfmon, and pyperfmon is now the more downloaded package, so it seems to be the right approach.



[This page contains my research on how to access the accessibility layer for each platform](research.md)




_
