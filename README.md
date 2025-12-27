<h1> 
  Welcome the DTS <i><sub><sub> - A Docker Template Stack Collection</sub></sub></i>
</h1>

Docker Template Stack Components provide pre-configured containerized development environments for developers who want to leverage Docker for consistent, portable, and isolated development. Each Docker Template Stack is tailored for specific development scenarios and includes a complete development environment with all necessary tools, dependencies, and a working template project for specific programming languages and frameworks.

> [Start here](https://nicojane.github.io/Docker-Template-Stacks-Home/index#2-the-available-stack-components)

## Design principles

Docker Template Stack components are containerized development environments that combine:

- **Pre-configured Docker containers** with specific programming language toolchains
- **Complete development toolset** including compilers, package managers, and utilities
- **Ready-to-use template projects** demonstrating best practices and architecture
- **Integrated development environment** with VS Code and Dev Containers extension
- **GUI output, using WSLg or X11**  Containers can be configured to display graphical output on the host
<br>

## Features

### Docker container Types

We distinguish between two container **types** and one container **property** type:

**1. Type: GUI-Forwarding Containers 🖥️**  
These containers forward their (GUI) output to the host using X11 forwarding. They are prefixed with:  ***`App-X11-Forward`***  or ***`X11-GUI`***  prefix and are marked with the above desktop icon in this document.

><details>  
>  <summary class="clickable-summary">
>  <span  class="summary-icon"></span>
>  <b>Host requirement</b>
>  </summary>
>
>  <small> These containers require the **XLaunch** program to be installed on your Windows host.  XLaunch uses the **X11 protocol** to forward the GUI to your host.  Instructions can be found in the **How-to** document of the relevant containers. </small>
> </details>

**2. Type: Non-GUI Containers** <br>
These containers do **not** support GUI forwarding and do **not** use the special prefix.

---

### Pluggable Container Architecture 🧩

The **pluggable architecture** is a core DTS concept that enables multiple containers to work together as a unified system while remaining independently manageable.

**How it works:**

- Any container can be made pluggable by configuring its `docker-compose.yml` file with a **network section**
- Containers with the 🧩 icon come **pre-configured** with this setup
- Containers connect via a shared external Docker network
- Each container maintains its own configuration while communicating seamlessly

**Benefits:**

- **Modular deployment** - Start only the services you need
- **Independent updates** - Update containers without affecting others  
- **Service isolation** - Each container handles a specific responsibility
- **Scalable architecture** - Add new services easily

> **Technical Implementation:** [External Docker Network Setup Guide (Gist)](https://gist.github.com/NicoJanE/709aacd7f2b3f858dce68ec27038a238) - Complete configuration details for implementing pluggable architecture
<br>

## Quick Setup Process

1. **Prerequisites**: Ensure Docker Desktop is installed and running on your system
2. **Download**: Obtain the appropriate template stack for your technology
3. **Execute**: Run the provided setup script to build and start your development container
4. **Develop**: Open the project in VS Code with Dev Containers and start coding
<br>


## Who & Why

<details>
  <summary> Target Audience
  </summary>
<br>

- **Cross-platform developers** wanting consistent environments across Windows, macOS, and Linux
- **Teams** requiring identical development environments regardless of host OS
- **Developers** starting new projects and wanting to skip initial setup
- **Students and educators** needing quick access to configured development environments
- **Anyone** who values rapid setup, portability, and completely isolated development environments

</details>

<details>
  <summary> Key benefits
  </summary>

- **Rapid Development Setup**
  - Execute a single setup script to build and configure your development container
  - Automatically provision the Docker container with all required tools and dependencies
  - Launch directly into VS Code with Dev Containers and start coding immediately
  - **Time to productivity: Minutes, not hours**
- **Combining different container components into one stack**
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
<br>

### License

All repositories are MIT licensed and free to use. For optional commercial support, customization, training, or long-term maintenance, see [`COMMERCIAL.md`](COMMERCIAL.md).

---

<br>

<!--
<div style="text-align: center;">
<font size="5">   <span style="color:#FFD700" >D</span>ocker <span style="color:#FFA500" >T</span>emplate <span style="color:#FF7F50" >S</span>tacks </font>

[**click here**](https://nicojane.github.io/Docker-Template-Stacks-Home/)
</div>
-->

<p align="center">
  <a href="https://nicojane.github.io/Docker-Template-Stacks-Home/">
    <img src="assets/images/DTSfooter.svg" alt="Docker Template Stacks" width="400" />
  </a>
</p>
