# ->IT<-


## Table of Contents

- [Linux](#linux)
  - [Commands](#linux.commands)

- [GIT](#git)
  - [Installation](#git.install)
  - [Commands](#git.commands)

- [Docker](#docker)
  - [Installation](#docker.install)
  - [Commands](#docker.commands)

- [PostgreSQL](#postgres)
  - [Installation](#postgres.install)
  - [Commands](#postgres.commands)


</br>

--------------------------------------------------------------------------------

</br>

## Linux <a name="linux"></a>


</br>

### Commands <a name="linux.commands"></a>





</br>

--------------------------------------------------------------------------------

</br>

## GIT <a name="git"></a>


</br>

### Installation <a name="git.install"></a>



</br>

### Commands <a name="git.commands"></a>




</br>

--------------------------------------------------------------------------------

</br>

## Docker <a name="docker"></a>


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


</br>

### Commands <a name="docker.commands"></a>





</br>

--------------------------------------------------------------------------------

</br>

## PostgreSQL <a name="postgres"></a>


</br>

### Installation <a name="postgres.install"></a>





</br>

### Commands <a name="postgres.commands"></a>





</br>

--------------------------------------------------------------------------------



