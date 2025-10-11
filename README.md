
# 1. What

Docker Template Stacks provide pre-configured containerized development environments for developers who want to leverage Docker for consistent, portable, and isolated development. Each Docker Template Stack is tailored for specific development scenarios and includes a complete development environment with all necessary tools, dependencies, and a working template project for specific programming languages and frameworks.

## 1.1 What's Included

Docker Template Stacks are containerized development environments that combine:

- **Pre-configured Docker containers** with specific programming language toolchains
- **Complete development toolset** including compilers, package managers, and utilities
- **Ready-to-use template projects** demonstrating best practices and architecture
- **Integrated development environment** with VS Code and Dev Containers extension
- **GUI output, using WSLg or X11**  Containers can be configured to display graphical output on the host

## 1.2 Docker Stack Types

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

><details>  
>  <summary class="clickable-summary">
>  <span  class="summary-icon"></span>
>  <b>Property: Pluggable Stacks🧩</b>
>  </summary>
>
>  <small> Any container type may have the **pluggable property**. A **pluggable** container includes a `docker-compose.yml` file with a **network section,** designed for easy integration with other independent stacks via a shared external Docker network. </small>  
> <small> A more detailed  **instruction** can be found [**here**](https://nicojane.github.io/Docker-Template-Stacks-Home/pluggable) (**local** [**here**](./pluggable) )</small>
>> <small> **Remark:** In hindsight, I would define **all containers** as pluggable</small>
> </details>


## 1.3 Quick Setup Process

1. **Prerequisites**: Ensure Docker Desktop is installed and running on your system
2. **Download**: Obtain the appropriate template stack for your technology
3. **Execute**: Run the provided setup script to build and start your development container
4. **Develop**: Open the project in VS Code with Dev Containers and start coding

## 1.3 Who & Why

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

# 2. The Docker-Template-Stacks

Please click on the link below for my docker Developer Template Stacks and the related information

<div style="text-align: center;">
<font size="5">   <span style="color:#FFD700" >D</span>ocker <span style="color:#FFA500" >T</span>emplate <span style="color:#FF7F50" >S</span>tacks </font>

[**click here**](https://nicojane.github.io/Docker-Template-Stacks-Home/)
</div>