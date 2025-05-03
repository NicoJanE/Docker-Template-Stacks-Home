---
layout: default_c
RefPages:
 
--- 

<br>

#  WSL vs Docker for GUI Dev in VS Code

A concise comparison between the differences and advantages of WSL and Docker containers, assuming a more advanced setup using custom development containers.

> **Goal:**{: style="color:#5491fa;font-size:13px; "} <br>
>To provide an easily installable, isolated development environment with tools and project templates to build GUI applications that run on the Windows host. Visual Studio Code is used as the development IDE.


## Similarities & Requirements

Both WSL and Docker containers can display GUI applications on the Windows host.

1. **WSL**{: style="color:#5491fa;font-size:13px; "}
  - Requires **Windows 11**  
  - Requires the **WSL extension** in Visual Studio Code (`ms-vscode-remote.remote-wsl`) — optional but recommended (see 'Usage')
  - Uses **WSLg**, a Wayland-based X server built into Windows 11, to render GUI apps on the host

1. **Docker**{: style="color:#5491fa;font-size:13px; "}
  - Works on **Windows 10 or newer**
  - Requires the **Dev Containers extension** in VS Code (`ms-vscode-remote.remote-containers`)
  - Requires **XLaunch (VcXsrv)** installed on the Windows host to handle X11 display<sup>[1](#footnote-1)</sup> This ensures the received X11 protocol information on the host is handled properly.
  - The **dockerfile** requires a defined variable Display: `ENV DISPLAY=host.docker.internal:0`
  - In your **Docker Compose** file, define the environment variable as follows (to make sure X11 protocol information is send to the host)
  
  ```
  environment:        
            - DISPLAY=host.docker.internal:0    # THIS relays the linux output to vcxsrv(Xlaunch)
  ```
    
  
## Usage

This describes how to use the different approaches in Visual Studio Code
1. **WSL**{: style="color:#5491fa;font-size:13px; "} <br>
You have two ways to develop with WSL in Visual Studio Code: <br> <br>
- **Install and run VS Code inside the WSL environment<sup>[2](#footnote-2)</sup>** <br> 
   This launches the full VS Code IDE from within the WSL environment using WSLg. This is not the recommended way, but may be useful when developing low-level Linux system software.<br><br>
- **Use the VS Code WSL extension (Recommended ✨)** <br>
  Start VS Code on Windows and use the WSL extension to open the project inside the WSL environment. When you run your GUI app, WSLg handles display output to the Windows host seamlessly.

1. **Docker**{: style="color:#5491fa;font-size:13px; "} <br>
The standard and recommended ✨ method is to:
- Start VS Code on the Windows host
- Use the **Dev Containers** extension to open a Docker container as the development environment

Running GUI apps from within the container will forward display output via X11 to the Windows host using XLaunch.
> **Warning**{: style="color: red;font-size:13px; "} <small>While technically possible, running VS Code from inside a Docker container is uncommon and poorly supported</small> <br>


## Advantages & performance
**Docker with X11** is generally the most responsive option:

- Works with **Windows 10 and newer**
- GUI apps launch faster and feel more responsive
- Uses **direct X11 communication** to XLaunch, reducing latency
- Runs in an isolated network environment
- **Security**: Docker offers more isolation and is generally more secure

**WSLg**, while integrated and simpler to set up, has:

- Noticeable **startup delays** (e.g. launching `gedit` may take 5+ seconds)
- Additional overhead due to **Wayland → Weston → FreeRDP → Windows** pipeline
- More components involved, which can introduce lag for certain GUI app
- Runs in a more direct (NAT-like) network environment, with less isolation


<hr>
<br><br>

### Footnotes

<small>1. <a name="footnote-1"></a>or equivalent X11 program</small> <br>
<small>2. <a name="footnote-2"></a> strictly speaking, WSL is not a container system like Docker. WSL is a lightweight VM hosting a Linux distribution, not an OCI-compliant container</small>


<br><br>
<small> <i>version 0.1</i> </small>
