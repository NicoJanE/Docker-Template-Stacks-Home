---
layout: default_c
RefPages:
 
--- 

<br>
 
# Introduction
***W***{: style="font-size:26px; "}elcome to the main site: **Docker Template Stack(DTS)!** <br>
This site documents the different **Docker Template Stacks** I have available.


## General
I distinguish between a two container **types** and one container **property** type:

**1. GUI-Forwarding Containers 🖥️**{: style="color:#dc9c2d;font-size:13px; "} <br>
These containers forward their (GUI) output to the host using X11 forwarding. They are prefixed with:  
***App X11 Forward GUI*** and marked with the above symbol this document.

> **Host requirement**{: style="color:#5491fa;font-size:13px; "} <br>
<small>
These containers require the **XLaunch** program to be installed on your Windows host.  XLaunch uses the **X11 protocol** to forward the GUI to your host.  Instructions can be found in the **How-to** document of the relevant containers. </small>

**2\. Non-GUI Containers**{: style="color:#dc9c2d;font-size:13px; "} <br>
These containers do **not** support GUI forwarding and do **not** use the ***'App X11 Forward GUI'*** prefix.

**3\. Pluggable Stacks🧩**{: style="color:#dc9c2d;font-size:13px; "}  <br>
Any container type may have the **pluggable property**. A **pluggable** container includes a `docker-compose.yml` file with a **network section,** designed for easy integration with other independent stacks via a shared external Docker network.

> **Instruction**{: style="color:#5491fa;font-size:12px; "} <br>
<small>
 A general instruction can be found **[here](https://nicojane.github.io/Docker-Template-Stacks-Home/pluggable)  [incase your local](./pluggable)** <br>
 **Remark:**{: style="color:gray;font-size:10px; "} In hindsight, I would define **all containers** as pluggable<br>
 </small>

<hr>

## The available stacks

### GUI Forward stacks 🖥️
- [App X11 Forward GUI](https://nicojane.github.io/APP-X11-Forward-Development-Template-Stack/) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - A generic .NET container with a basic Command Application template</small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An Avalonia project container, with Avalonia GUI project template, forwards X11 GUI to Windows host </small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An .NET project container in combination with GTK#, forwards X11 GUI to Windows host </small><br>
- [App X11 Forward GUI Cross-Compiling Win32](https://nicojane.github.io/APP-X11-Forward-win32-Development-Template-Stack/) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - Specific for win32/C language & frameworks  </small> <br>
- [App X11 Forward GUI Cross-Compiling Win32 C++](https://nicojane.github.io/APP-X11-Forward-win32-CPP-Development-Template-Stack/) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - specific for Win32/C++ language & frameworks  </small> <br>
- [App X11 Forward PyCRust](https://nicojane.github.io/APP-X11-Forward-PyCRust-Dev-Template-Stack//) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An project container for development in Python (frontend) in combination with Rust and C/C++ (backend)  </small> <br>

### Normal stacks 🖥️

- [Jenkins](https://nicojane.github.io/Jenkins-Development-Stack/) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
   <small> - Jenkins CI/CD setup for individual developers working on local projects (not for production)</small> <br>
- [PHP DTS](https://nicojane.github.io/PHP-Development-Template-Stack/)
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small><br>
  <small> - A PHP template project, Different php versions, PHP Unit test, Symfony and Apache2</small>
- [STM32](https://nicojane.github.io/STM32F4/)
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small><br>
  <small> - A Docker container for microcontroller bare-bone projects, in C and C++</small>
- [React DTS](https://nicojane.github.io/React-Development-Template-Stack/) 
- [Rust DTS](https://nicojane.github.io/Rust-Development-Template-Stack/)
- \[Maria DB\] To be released (🧩)

<hr>

## General Requirements 
To use these DTS Docker containers, you should:
- Have **Docker Desktop** installed and running on your **host**
- **Docker Desktop**  images are tested and supported on the following host operating systems.
  - Supported on Windows✅
  - Supported on Linux❓
  - Supported on macOS❓

> **Instruction**{: style="color:#5491fa;font-size:12px; "} <br>
<small>
 Although these images were developed on Windows using Docker Desktop, they **should** work on other operating systems with minor changes (e.g., file path formats). This is currently **unverified** — optimistic expectation 😄
 </small>
