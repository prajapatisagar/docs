---
author:
  name: Joe D.
  email: docs@linode.com
description: 'Deploy a Node.js Server in a Docker Container.'
keywords: 'docker,node.js,node,debian,ubuntu,web server,javascript,container'
license: '[CC BY-ND 4.0](https://creativecommons.org/licenses/by-nd/4.0)'
modified: Thursday, November 16, 2017
modified_by:
  name: Linode
published: 'Monday, March 23rd, 2015'
title: 'Node.js Web Server deployed within Docker'
alias: ['applications/containers/nodejs-node-js-web-server-docker-container/']
---

Node.js is a server-side, JavaScript package, often used for various cloud applications. Docker is a container platform. With Docker, users can download applications without the hassle of the installation and configuration process.

## Install Docker
Use the Docker-maintained install script for Debian or Ubuntu. For other operating systems, see the [Docker Installation](https://docs.docker.com/en/latest/installation/) guides.

1.  Install Docker:

        curl -sSL https://get.docker.com/ | sh

2.  If necessary, add the non-root user to the "docker" group:

        sudo usermod -aG docker example_user

## Download the Docker Node.js Server Image
The Docker Hub user page for Linode can be accessed [here](https://hub.docker.com/u/linode/). Select the **server-node-js** image for configuration information.

{{ <note> }}
>
>Docker images made for one operating system can be used on servers running a different OS. The **server-node-js** Ubuntu 14.04 image was tested on Debian 7, Ubuntu 14.04, Centos 7 and Fedora 21. After Docker installation on Centos and Fedora, run the `sudo service docker start` command.
{{ </note>}}
1.  Search for **linode** images:

        sudo docker search linode

2.  Download the **linode/server-node-js** image:

        sudo docker pull linode/server-node-js

## Run the Docker Container, Node.js, and the Web Server
Note that when an image downloads, no image containers run.

1.  Run, create or activate a new container. Forward the Linode's port 80 to port 3000 of the container:

        docker run -d -p 80:3000 linode/server-node-js

     {{< note >}}
 > This command runs the docker image as a daemon. 
{{< /note>}}

2. Test the server at `example.com/test.htm`, replacing `example.com` with your Linode's IP address. A page with "Test File" should appear.

The [Docker Hub image page](https://registry.hub.docker.com/u/linode/server-node-js/) has information explaining what the Docker image contains.

## For More Information
 - [Linode Docker Hub Page](https://hub.docker.com/u/linode/)
 - [Docker Docs](http://docs.docker.com/)
 - [Docker Try it Tutorial](https://www.docker.com/tryit/)
 - [Docker Hub](https://hub.docker.com/)


