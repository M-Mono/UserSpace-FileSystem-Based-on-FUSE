# 使用 FUSE 开发自己的文件系统

---
使用用户空间的文件系统（FUSE），您无需理解文件系统的内幕，也不用学习内核模块编程的知识，就可以开发用户空间的文件系统框架。本文是一篇简单的逐步介绍的指南，内容包括安装、定制和启用 FUSE 和 AFS，这样您就可以在 Linux® 的用户空间中创建自己的功能完备的文件系统了。

使用 FUSE 您可以开发功能完备的文件系统：其具有简单的 API 库，可以被非特权用户访问，并可以安全的实施。更重要的是，FUSE 以往的表现充分证明了其稳定性。
使用 FUSE，您可以像可执行二进制文件一样来开发文件系统，它们需要链接到 FUSE 库上 —— 换言之，这个文件系统框架并不需要您了解文件系统的内幕和内核模块编程的知识。

就文件系统来说，用户空间的文件系统就不再是新奇的设计了。用户空间文件系统的商业实现与学术实现的实例包括：

+ LUFS 是一个混合用户空间的文件系统框架，它对用于任何应用程序无数的文件系统提供透明支持。大部分LUFS 包括一个内核模块和一个用户空间的守护进程。从根本上来说，它将大部分 VFS 调用都委托给一个专用的守护进程来处理。

+ UserFS 让用户进程可以像普通的文件系统一样进行加载。这种概念性的原型提供了 ftpfs，这可以使用文件系统接口提供匿名 FTP 访问。

+ Ufo Project 是为 Solaris 提供的一个全局文件系统，它允许用户将远程文件真正当作本地文件一样对待。

+ OpenAFS 是 Andrew FileSystem 的一个开源版本。

+ CIFS 是 Common Internet FileSystem 的简称。

与这些商业实现和学术实现不同，FUSE 将这种文件系统的设计能力带到了 Linux 中来。由于 FUSE 使用的是可执行程序（而不像 LUFS 一样使用的是共享对象），因此可以简化程序的调试和开发。FUSE 可以在 2.4.x 和 2.6.x 的内核上使用，现在可以支持 Java™ 绑定，因此您可以不必限定于使用 C 和 C++ 来编写文件系统了。

要在 FUSE 中创建一个文件系统，您需要安装一个 FUSE 内核模块，然后使用 FUSE 库和 API 来创建自己的文件系统。

![使用 FUSE 开发自己的文件系统](https://github.com/M-Mono/UserSpace-FileSystem-Based-on-FUSE/Images/FUSE_structure.svg.png)
---
编译环境：
+ Fork
  - [Yixf-Education](https://github.com/Yixf-Education/BP4B)


+ Apple OS X & macOS
  - [MacTeX 2016](https://www.tug.org/mactex/)


+ GNU/Linux & Microsoft Windows
  - [TeX Live 2016](https://www.tug.org/texlive/)


+ Fonts
  - [Inziu Iosevka 1.11.0](https://be5invis.github.io/Iosevka/inziu.html)
  - [Source Code Pro 2.030](https://github.com/adobe-fonts/source-code-pro)


+ Editor
  - [TeXstudio 2.12.2](http://texstudio.sourceforge.net/)
