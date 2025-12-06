---
layout: default_c
RefPages:
TableCont:
--- 
<table class ="no-border"  style="width:100%;">
  <tr>
    <td style="vertical-align:middle; text-align:left; height:30px;">&nbsp;</td>
    <td style="text-align:right; vertical-align:bottom;  padding-right:20px;">
      <a href="https://nicojane.github.io/WSL-Template-Stacks-Home/"
         style="background:#0078d7; color:white; padding:3px 10px; border-radius:8px; font-size:0.8em; text-decoration:none; font-weight:bold; display:inline-block;">
        🚀 To WSL Stacks
      </a>
    </td>
  </tr>
  <tr>
    <td style="vertical-align:middle; text-align:left;">
      <span style="font-size: 3.2em; font-weight: 550;">W</span>
      <span style="font-size: 2.5em; font-weight: 500; margin-left: -0.2em;">elcome to the DTS</span> <br>
      <span style="color: #409EFF; font-style: italic; font-size:1.1em; position:relative; top:-0.6em; display:inline-block;"> — A Docker Template Stack</span>
    </td>
    <td style="text-align:right; vertical-align:middle;">&nbsp;</td>
  </tr>
</table>

Docker Template Stacks offer pre-configured, containerized development environments, enabling developers to leverage Docker for consistent, portable, and isolated workflows.Each stack is tailored to specific development scenarios and includes all necessary tools, dependencies, and a working template project for various programming languages and frameworks

<div class="nje-info-box" style="--box-width: 25%;">
📚 <strong>Direct Link to: </strong><br>
 <span class="nje-indent2"><a href="https://nicojane.github.io/Docker-Template-Stacks-Home/#the-stack-components"> 🔶 The Available DTS Components</a>
</div>
<div class="nje-br1"> </div>

## What's Included

Docker Template Stack components are containerized development environments that combine the following features, which apply to all containers listed in the “Available Stack Components”

- **Pre-configured Docker containers** with specific programming language toolchains
- **Can be combined to create a network Stack**
- **Complete development toolset** including compilers, package managers, and utilities
- **Ready-to-use template projects** demonstrating best practices and architecture
- **Integrated development environment** with VS Code and Dev Containers extension
- **May support GUI output, using WSLg or X11**  Containers can be configured to display graphical output on the host.

---

## Docker Container Types

There are two different container **types**

<span class="nje-colored-block" style="--nje-bgcolor:gray; --nje-textcolor:white; ">**1. GUI-Forwarding Containers** &nbsp; 🖥️</span> <br>
These containers forward their GUI output to the host using X11.
They are prefixed with: ***App-X11-Forward*** or ***X11-GUI*** <sup>[1](#note-1)</sup> prefix and are marked with the above desktop icon in this document.

<details class="nje-note-box">
  <summary>Host requires XLaunch
  </summary>
   These containers require the **XLaunch** program on your Windows host.  XLaunch uses the **X11 protocol** to forward the GUI to your host.  Instructions can be found in the **How-to** document of the relevant containers.
</details>
<br>
<div class="nje-br1"> </div>

<span class="nje-colored-block" style="--nje-bgcolor:gray; --nje-textcolor:white; ">**2. Non-GUI-Forwarding Containers**</span> <br>
These containers do **not** support GUI forwarding and do not use the special prefix.

---

## Pluggable Container Architecture 🧩

**Pluggable architecture** is a core DTS property, allowing multiple containers to work together as a unified system while remaining independently manageable. Stack components with this icon 🧩 have a default pluggable implementation. Additionally, any stack component can be upgraded with a pluggable property.

<details class="nje-back-box">
  <summary>Pluggable Property Details
  </summary>

## How it works

- Any container can be made pluggable by configuring its <span class="nje-cmd-inline-sm">docker-compose.yml</span> file with a **network section**
- Containers with the 🧩 icon come **pre-configured** with this setup
- Containers connect through a shared external Docker network.
- Each container maintains its own configuration and communicates seamlessly

## Benefits

- **Modular deployment** - start only the services you need
- **Independent updates** - update containers without affecting others  
- **Service isolation** - each container handles a specific responsibility
- **Scalable architecture** - add new services easily

<p align="center" style="padding:20px;">─── ✦ ───</p>
</details>
<span class="nje-br2"> </span>

<div class="nje-info-box" style="--box-width: 25%;">
📚 <strong>Usage Instruction </strong> <br>
<span class="nje-indent2"> <a href="https://gist.github.com/NicoJanE/709aacd7f2b3f858dce68ec27038a238"> 🔶 External Docker Network Setup Guide</a>
</div>

---

## General Quick Setup Process

1. **Prerequisites**: Ensure Docker Desktop is installed and running on your system
2. **Clone**: Clone the appropriate template stack for your technology
3. **Execute**: Run the setup script to build and start your development container
4. **Develop**: Open the project in VS Code using Dev Containers and start coding.

---

### Additional setup Information

<div class="nje-br4"> </div>
<details class="nje-note-box" style="margin-top:-18px; margin-left:0px;">
  <summary>General Requirements
  </summary>

- Have **Docker Desktop** installed and running on your **host**
  - **Docker Desktop** images are tested and supported on the following host operating systems:
    - Supported on Windows✅
    - Supported on Linux❓
    - Supported on macOS❓

</details>
<div class="nje-br4"> </div>
<div class="nje-br2"> </div>

<details class="nje-note-box" style="margin-top:-18px; margin-left:0px;">
  <summary>Target Audience
  </summary>

- **Cross-platform developers** wanting consistent environments across Windows, macOS, and Linux
- **Teams** requiring identical development environments regardless of host OS
- **Developers** starting new projects and wanting to skip initial setup
- **Students and educators** needing quick access to configured development environments
- **Anyone** who values rapid setup, portability, and completely isolated development environments

</details>
<div class="nje-br4"> </div>
<div class="nje-br2"> </div>

<details class="nje-note-box" style="margin-top:-18px;margin-left:0px;">
  <summary>Key Features
  </summary>

The stacks feature the following <br><br>

<div class="nje-features-box">
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

</div>
</details>
<div class="nje-br4"> </div>
<hr>
<div class="nje-br2"> </div>

# The Stack Components

The following sections list the available DTS stack components, organized by container type.

<details class="nje-note-box" >
  <summary>Docker Desktop support
  </summary>
   Although these images were developed on Windows using Docker Desktop, they **should** work on other operating systems with minor changes (e.g., file path formats). This is currently **unverified** — optimistic expectation 😄
</details>
<div class="nje-br2"> </div>

## GUI Forward Project Containers

These containers run Debian OS with X11 GUI forwarding and include a specific development environment, along with a template project to help you get started easily. Most are dedicated to a single development language. **However**, `X11-Dev` is a multi-container solution: it consists of a **Base Container** and multiple **Sub Containers**, each with its own development environment and templates. With `X11-Dev`, you can combine several development environments by adding the desired sub-containers.

- [X11-GUI-Dev 🖥️](https://nicojane.github.io/X11-GUI-Dev-Template-Stack/)🧩
  <img src=".\assets\images\docker_m.png" alt="Docker Icon" width="24" height="24" style="background: transparent; vertical-align: -6px;" title='Multiple containers'><br>
  <small>The new **General purpose X11 GUI container** that forwards the GUI to Windows host, replacing ***App X11 Forward GUI***  </small><br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - A generic .NET container with a basic Command Application template</small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - An Avalonia project container, with Avalonia GUI project template. </small> <br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - A .NET project container in combination with GTK#. </small><br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - A PHP/Python/Rust Sub container </small><br>
- [App X11 Forward GUI Cross-Compiling Win32 🖥️](https://nicojane.github.io/APP-X11-Forward-win32-Development-Template-Stack/) 
  <img src=".\assets\images\docker_s.png" alt="Docker Icon" width="24" height="24" style="background: transparent; vertical-align: -6px;" title='Dedicated container'><br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - Specific for win32/C language & frameworks  </small> <br>
  <small> - And for Win32/C++ language & frameworks  </small> <br>
- [App X11 Forward PyCRust 🖥️](https://nicojane.github.io/APP-X11-Forward-PyCRust-Dev-Template-Stack//)
  <img src=".\assets\images\docker_s.png" alt="Docker Icon" width="24" height="24" style="background: transparent; vertical-align: -6px;" title='Dedicated container'><br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - A project container for development in Python (frontend) combined with Rust and C/C++ (backend)  </small> <br>
- [App X11 Forward GUI Cross-Compiling Win32 C++ 🖥️⚠️](https://nicojane.github.io/APP-X11-Forward-win32-CPP-Development-Template-Stack/) 
  <img src=".\assets\images\docker_s.png" alt="Docker Icon" width="24" height="24" style="background: transparent; vertical-align: -6px;" title='Dedicated container' ><br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/>  </small>
  <small> - specific for Win32/C++ language & frameworks  </small> <br>

## None GUI Project Containers

These containers run Debian OS **without** X11 GUI forwarding. They still provide a specific development environment and a template project to help you get started quickly. Most are dedicated to a single development language.

- [STM32](https://nicojane.github.io/STM32F4/)
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small><br>
  <small> - A Docker container for microcontroller bare-bone projects, in C and C++</small>
- [React DTS](https://nicojane.github.io/React-Development-Template-Stack/) 
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small><br>
  <small> - A Docker container for  React</small>
- [Rust DTS](https://nicojane.github.io/Rust-Development-Template-Stack/)
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small><br>
  <small> - A Docker container for  Rust</small>
- [.NET DTS](https://nicojane.github.io/NET-Dev-Template-Stack/)  🧩
  <img src=".\assets\images\docker_s.png" alt="Docker Icon" width="24" height="24" style="background: transparent; vertical-align: -6px;" title='Dedicated container' >
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small><br>
  <small> - A Docker container with .NET containers and template projects</small>
- [PHP DTS 🔍](https://nicojane.github.io/PHP-Development-Template-Stack/)
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small><br>
  <small> - A PHP template project, different PHP versions, PHPUnit tests, Symfony, and Apache2</small>

## Supporting Containers

These containers do not include a development environment. Instead, they provide specific tools designed to integrate into your container stack. These are called  **Pluggable** containers because you can easily add them to your network/stack. By default, they use the **external network** `dev1-net` *(see Legend).*

- [Jenkins](https://nicojane.github.io/Jenkins-Development-Stack/) 🧩<br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - Jenkins CI/CD setup for individual developers working on local projects.</small> <br>
- [Maria DB](https://nicojane.github.io/MariaDB/) 🧩<br>
  <small><span class="nje-ident" style="--nje-number-of-spaces: 4px;"/> </small>
  <small> - Database for individual developers working on local projects.</small> <br>

<div class="nje-br2"> </div>
<details class="nje-note-box">
  <summary>
  **Legend** <br>
  </summary>
- 🖥️  *Container supports X11 forwarded GUI to host.*{: style="color: Darkgray;font-size:12px; "} <br>
- 🧩  *The container is by default part of an external network named: **dev1-net** (may be changed)*{: style="color: Darkgray;font-size:12px; "} <br>
- ⚠️  *The container is deprecated and may be removed.*{: style="color: Darkgray;font-size:12px; "} <br>
- 🔍  *This container or item needs review.*{: style="color: Darkgray;font-size:12px; "} <br>
- <img src=".\assets\images\docker_s.png" alt="Docker Icon" width="24" height="24" style="background: transparent; vertical-align: -6px;" title='Dedicated container'>*Represents a container with a dedicated configuration (e.g., only for C++ development).*
- <img src=".\assets\images\docker_m.png" alt="Docker Icon" width="24" height="24" style="background: transparent; vertical-align: -6px;" title='Multiple containers'>*Represents a container with multiple configurations (e.g., React, PHP, Node). You can choose which to use by configuring the appropriate **sub-container**.*

</details>
<div class="nje-br4"> </div>
<div class="nje-br2"> </div>

**Footnotes**{: style="color: Darkgray;font-size:11px; "} <br>
<small> - <a name="note-1"></a> ***Note** 1: The new preferred, shorter prefix.*{: style="color: Darkgray;font-size:12px; "} </small>


<br>
<div align="center"> ─── ✦ ───
</div>
