---
layout: default_c
RefPages:
 
--- 

<br>
# 1. What
***W***{: style="font-size:26px; "}elcome to the **Docker Template Stack (DTS)!**<br>

> [Direct Link to the Available Stack components](#2-the-available-stacks)


Docker Template Stacks provide pre-configured containerized development environments for developers who want to leverage Docker for consistent, portable, and isolated development. Each Docker Template Stack is tailored for specific development scenarios and includes a complete development environment with all necessary tools, dependencies, and a working template project for specific programming languages and frameworks.

## 1.1 What's Included

Docker Template Stack components are containerized development environments that combine:

- **Pre-configured Docker containers** with specific programming language toolchains
- **Can be combined together to create a (network) Stack**
- **Complete development toolset** including compilers, package managers, and utilities
- **Ready-to-use template projects** demonstrating best practices and architecture
- **Integrated development environment** with VS Code and Dev Containers extension
- **GUI output, using WSLg or X11**  Containers can be configured to display graphical output on the host

## 1.2 Docker Stack Types

We distinguish between two container **types** and one container **property** type:

**1. Type: GUI-Forwarding Containers 🖥️**{: style="color:#5f7f90;font-size:13px; "} <br>
These containers forward their (GUI) output to the host using X11 forwarding. They are prefixed with:  ***`App-X11-Forward`***  or ***`X11-GUI`*** <sup>[1](#note-1)</sup> prefix and are marked with the above desktop icon in this document.

><details>  
>  <summary class="clickable-summary">
>  <span  class="summary-icon"></span>
>  **Host requirement**{: style="color:#5491fa;font-size:13px; "}
>  </summary>
>  <small> These containers require the **XLaunch** program to be installed on your Windows host.  XLaunch uses the **X11 protocol** to forward the GUI to your host.  Instructions can be found in the **How-to** document of the relevant containers. </small>
></details>

**1. Type: Non-GUI Containers**{: style="color:#5f7f90;font-size:13px; "} <br>
These containers do **not** support GUI forwarding and do **not** use the special prefix.

><details>  
>  <summary class="clickable-summary">
>  <span  class="summary-icon"></span>
>  **Property: Pluggable Stacks🧩**{: style="color:#5491fa;font-size:13px; "}
>  </summary>
>  <small> Any container type may have the **pluggable property**. A **pluggable** container includes a `docker-compose.yml` file with a **network section,** designed for easy integration with other independent stacks via a shared external Docker network. </small>  
> <small> A more detailed  **instruction** can be found [**here**](https://nicojane.github.io/Docker-Template-Stacks-Home/pluggable) (**local** [**here**](./pluggable) )</small>
>> <small> **Remark:**{: style="color:gray;font-size:10px; "} In hindsight, I would define **all containers** as pluggable</small>
> </details>


## 1.3 Quick Setup Process

1. **Prerequisites**: Ensure Docker Desktop is installed and running on your system
2. **Download**: Obtain the appropriate template stack for your technology
3. **Execute**: Run the provided setup script to build and start your development container
4. **Develop**: Open the project in VS Code with Dev Containers and start coding

## 1.3 Who & Why & Required

<details>
  <summary style="font-size: 1.0em; font-weight: 600; margin-top: 0.1em; margin-bottom: 0.2em;"> &#9654; General Requirements
  </summary>
  
- Have **Docker Desktop** installed and running on your **host**
- **Docker Desktop**  images are tested and supported on the following host operating systems.
  - Supported on Windows✅
  - Supported on Linux❓
  - Supported on macOS❓

</details>

<details>
  <summary style="font-size: 1.0em; font-weight: 600; margin-top: 0.1em; margin-bottom: 0.2em;"> &#9654; Target Audience
  </summary>

- **Cross-platform developers** wanting consistent environments across Windows, macOS, and Linux
- **Teams** requiring identical development environments regardless of host OS
- **Developers** starting new projects and wanting to skip initial setup
- **Students and educators** needing quick access to configured development environments
- **Anyone** who values rapid setup, portability, and completely isolated development environments

</details>

<details>
  <summary style="font-size: 1.0em; font-weight: 600; margin-top: 0.1em; margin-bottom: 0.2em;"> &#9654; Key benefits
  </summary>

- **Rapid Development Setup**
  - Execute a single setup script to build and configure your development container
  - Automatically provision the Docker container with all required tools and dependencies
  - Launch directly into VS Code with Dev Containers and start coding immediately
  - **Time to productivity: Minutes, not hours**

- **Completely Isolated Environment**
  - Each stack runs in its own Docker container with only relevant tools and dependencies
  - Eliminates version conflicts and dependency issues between different projects
  - Provides identical development environment across different operating systems
  - **Zero pollution of your host system**

- **Production-Ready Template Projects**
  - Start with a fully functional template application that demonstrates best practices
  - Includes proper project structure, configuration files, and Docker setup
  - Template can be immediately built, tested, and deployed using containers
  - **Skip the boilerplate and focus on your business logic**

- **True Cross-Platform Development**
  - Develop applications that run identically on Windows, macOS, and Linux
  - Test your applications in production-like containerized environments
  - Use the same development stack regardless of your host operating system
  - **One container, runs everywhere**

</details>


<hr>

# 2 The Available Stack Components

Next follows a list  with references to the available DTS stack components

## 2.1 GUI Forward stacks
- [App X11 Forward GUI 🖥️ <small>🛑</small> ](https://nicojane.github.io/APP-X11-Forward-Development-Template-Stack/) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - <small>🛑</small>  *Deprecated!*{: style="color:red;font-size:12px; "} replaced by [X11-GUI-Dev](https://nicojane.github.io/X11-GUI-Dev-Template-Stack/) </small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - A generic .NET container with a basic Command Application template</small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An Avalonia project container, with Avalonia GUI project template, forwards X11 GUI to Windows host </small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An .NET project container in combination with GTK#, forwards X11 GUI to Windows host </small><br>
- [X11-GUI-Dev 🖥️🧩](https://nicojane.github.io/X11-GUI-Dev-Template-Stack/) <br>
  <small>The new **General purpose X11 GUI container** that forwards the GUI to Windows host, replacing ***App X11 Forward GUI***  </small><br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - A generic .NET container with a basic Command Application template</small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An Avalonia project container, with Avalonia GUI project template. </small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - A .NET project container in combination with GTK#. </small><br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - A PHP/Python/Rust Sub container </small><br>
- [App X11 Forward GUI Cross-Compiling Win32 🖥️](https://nicojane.github.io/APP-X11-Forward-win32-Development-Template-Stack/) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - Specific for win32/C language & frameworks  </small> <br>
- [App X11 Forward GUI Cross-Compiling Win32 C++ 🖥️](https://nicojane.github.io/APP-X11-Forward-win32-CPP-Development-Template-Stack/) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - specific for Win32/C++ language & frameworks  </small> <br>
- [App X11 Forward PyCRust 🖥️](https://nicojane.github.io/APP-X11-Forward-PyCRust-Dev-Template-Stack//) <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An project container for development in Python (frontend) in combination with Rust and C/C++ (backend)  </small> <br>

## 2.2 None GUI stacks

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


> **Note**{: style="color:#5491fa;font-size:12px; "} <br>
<small>
 Although these images were developed on Windows using Docker Desktop, they **should** work on other operating systems with minor changes (e.g., file path formats). This is currently **unverified** — optimistic expectation 😄
 </small>

<hr>

#### Footnotes

<small>**1.** <a name="note-1"></a> the new preferred shorter prefix. </small>





