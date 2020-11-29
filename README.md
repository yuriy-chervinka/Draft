# <p align="center">IT</p>

</br>

## <p align="center">Table of Contents</p>

- __[Markdown](#markdown)__
  - [Links](#markdown.links)

- __[Linux](#linux)__
  - [Commands](#linux.commands)
  - [Links](#linux.links)

- __[GIT](#git)__
  - [Installation](#git.install)
  - [Commands](#git.commands)
  - [Workflow](#docker.workflow)
  - [Links](#git.links)

- __[Docker](#docker)__
  - [Installation](#docker.install)
  - [Commands](#docker.commands)
  - [Workflow](#docker.workflow)
  - [Links](#docker.links)

- __[SQL (PostgreSQL)](#postgres)__
  - [Installation](#postgres.install)
  - [Commands](#postgres.commands)
  - [Workflow](#postgres.workflow)
  - [Links](#postgres.links)


</br>

--------------------------------------------------------------------------------

</br>

## <p align="center">Markdown</p> <a name="markdown"></a>








</br>

--------------------------------------------------------------------------------

</br>

## <p align="center">Linux</p> <a name="linux"></a>


</br>

### Commands <a name="linux.commands"></a>




</br>

### Links <a name="linux.links"></a>





</br>

--------------------------------------------------------------------------------

</br>

## <p align="center">GIT</p> <a name="git"></a>


</br>

### Installation <a name="git.install"></a>



</br>

### Commands <a name="git.commands"></a>



</br>

### Workflow <a name="git.workflow"></a>




</br>

### Links <a name="git.links"></a>






</br>

--------------------------------------------------------------------------------

</br>

## <p align="center">Docker</p> <a name="docker"></a>


</br>

### Installation <a name="docker.install"></a>  
  
__1. Set up the repository__  
  
1.1. Update the apt package index, and install packages to allow apt to use a repository over HTTPS:
  ```
  $ sudo apt update
  $ sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
  ```  
1.2. Add Docker’s official GPG key:  
  ```
  $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
  OK
  ```  
1.3. Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint:  
  ```
  $ sudo apt-key fingerprint 0EBFCD88
  pub   rsa4096 2017-02-22 [SCEA]
        9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
  uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
  sub   rsa4096 2017-02-22 [S]
  ```  
1.4. Set up the stable repository:  
  ```
  $ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
  ```  
  
__2. Install Docker Engine__  
  
2.1. Update the apt package index, and install the latest version of Docker Engine and containerd:
  ```
  $ sudo apt update
  $ sudo apt install docker-ce docker-ce-cli containerd.io
  ```  
2.2. Verify that Docker Engine is installed correctly by running the hello-world image:  
  ```
  $ sudo docker run hello-world  
  Unable to find image 'hello-world:latest' locally
  latest: Pulling from library/hello-world
  0e03bdcc26d7: Pull complete 
  Digest: sha256:e7c70bb24b462baa86c102610182e3efcb12a04854e8c582838d92970a09f323
  Status: Downloaded newer image for hello-world:latest

  Hello from Docker!
  This message shows that your installation appears to be working correctly.
  ...
  ```  
  
__3. Post-installation steps__  
  
3.1. Manage Docker as a non-root user:  
The Docker daemon binds to a Unix socket instead of a TCP port. By default that Unix socket is owned by the user `root` and other users can only access it using `sudo`. The Docker daemon always runs as the `root` user.  
If you don’t want to preface the `docker` command with `sudo`, create a Unix group called `docker` and add users to it. When the Docker daemon starts, it creates a Unix socket accessible by members of the `docker` group.  
  
Create a `docker` group, and add your user to the `docker` group:  
  ```
  $ sudo groupadd docker
  $ sudo usermod -aG docker $USER
  ```  
Log out and log in, so that your group membership is re-evaluated. Or run the following command to activate the changes to groups:  
  ```
  $ newgrp docker
  ```  
Verify that you can run docker commands without sudo:  
  ```
  $ docker run hello-world
  Hello from Docker!
  This message shows that your installation appears to be working correctly.
  ...
  ```  
  
3.2. Configure Docker to start on boot:  
   ```
  $ sudo systemctl enable docker
  ```  




</br>

### Commands <a name="docker.commands" ></a>  <a href="https://docs.docker.com/engine/reference/commandline/docker/" target="_blank"> (documentation)</a>  
  
- check the version:  
`$ docker --version`  
- create and run container from an image:  
`$ docker run [OPTIONS] IMAGE [COMMAND] [ARG...]`  
- manage images:  
`$ docker image COMMAND`  
  - list images:  
  `$ docker image ls`  
  - build an image from docker file:  
  `$ docker image build`  
  - pull an image from registry:  
  `$ docker image pull`  
  - push an image to registry:  
  `$ docker image push`  
  - remove image:  
  `$ docker image rm`  
- manage containers:  
`$ docker container COMMAND`  
  - list containers:  
  `$ docker container ls`  
  - start container:  
  `$ docker container start`  
  - stop container:  
  `$ docker container stop`  
  - remove container:  
  `$ docker container rm`  
- list containers:  
`$ docker ps [OPTIONS]`  
  - list all:  
  `$ docker ps -a`  
- remove container:  
`$ docker rm [OPTIONS] CONTAINER`  
- remove image:  
`$ docker rmi [OPTIONS] IMAGE`  
- stop running container:  
`$ docker stop [OPTIONS] CONTAINER`  
- start stopped container:  
`$ docker start [OPTIONS] CONTAINER`  



</br>

### Workflow <a name="docker.workflow"></a>




  
</br>

### Links <a name="docker.links"></a>
- <a href="https://docs.docker.com/" target="_blank">docs.docker.com</a> - official site






</br>

--------------------------------------------------------------------------------

</br>

## <p align="center">SQL (PostgreSQL)</p> <a name="postgres"></a>


</br>

### Installation <a name="postgres.install"></a>  
<!---  
__1. Set up the repository__  
  
1.1. Update the apt package index, and install packages to allow apt to use a repository over HTTPS:
  ```
  $ sudo apt update
  $ sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
  ```  
1.2. Add Docker’s official GPG key:  
  ```
  $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -  
  OK
  ```  
1.3. Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint:  
  ```
  $ sudo apt-key fingerprint 0EBFCD88
  pub   rsa4096 2017-02-22 [SCEA]
        9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
  uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
  sub   rsa4096 2017-02-22 [S]
  ```  

--->



</br>

### Commands <a name="postgres.commands"></a>




</br>

### Workflow <a name="postgres.workflow"></a>




</br>

### Links <a name="postgres.links"></a>







</br>

--------------------------------------------------------------------------------



