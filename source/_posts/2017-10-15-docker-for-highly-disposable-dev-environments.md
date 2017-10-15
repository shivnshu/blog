---
layout: post
title: "Docker for highly disposable dev environments"
permalink: docker-for-highly-disposable-dev-environments
comments: true
description: "Docker for highly disposable dev environments"
keywords: ""
categories:

tags:

---

Virtual machines are the perfect way of isolating your work environment from your host environment. But when your work is only limited to the user-space programs, this perfect isolation, which comes at the price of performance, is not required.

With the onset of [namespaces in linux kernel](https://en.wikipedia.org/wiki/Linux_namespaces), the concept of containers (sometimes called lightVM) came to light. Unlike [jails](https://en.wikipedia.org/wiki/Chroot), namespaces also isolate and visualize the process's pids, uids, [IPC](https://en.wikipedia.org/wiki/Inter-process_communication) and network access. These isolations suffice to containerize user-space programs without hardware abstraction. Following are some non-trivial use cases of containers.

<ol>
    <li>
	<strong>Docker for Machine learning applications</strong><br/>
        Machine learning applications that require the use of GPU (nvidia) are the perfect example of container's usability. With the release of <a href="https://github.com/NVIDIA/nvidia-docker">nvidia-docker</a>, it is now possible to build the docker containers leveraging the Nvidia GPUs. Replacing <code>docker</code> by <code>nvidia-docker</code> allows the GPUs to be accessible by provisioned container.
    </li>
    <br/>
    <li>
        <strong>Running GUI apps with Docker</strong><br/>
        There are few different options to run GUI applications inside Docker container like <a href="https://stackoverflow.com/questions/16296753/can-you-run-gui-apps-in-a-docker-container/16311264#16311264">ssh with X11 forwarding</a> or <a href="https://blog.docker.com/2013/07/docker-desktop-your-desktop-over-ssh-running-inside-of-a-docker-container/">VNC</a>. But when it comes to run applications using OpenGL like <a href="https://answers.ros.org/question/44840/rosrun-rviz-and-x-window/">Rviz</a>, X11 forwarding with ssh fails miserably. Hence, one simple option to accomplish this task is to share X11 socket with the container and use it directly.
	<br/>
	The idea here is to use the same uid gid of the container user as of the host user exemplified <a href="https://github.com/shivnshu/ros/blob/master/Dockerfile">here</a>. While provisioning the container, the env variable <code>DISPLAY</code> is exported and volume <code>~/.Xauthority</code> of host is mounted to <code>~/.Xauthority</code> on container filesystem. The preceding effects can be achieved by running <br/> <code>docker run -it -e DISPLAY -v $HOME/.Xauthority:/home/developer/.Xauthority --net=host image-name</code>
    </li>
</ol>
