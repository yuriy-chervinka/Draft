# IT


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



--------------------------------------------------------------------------------

### Linux <a name="linux"></a>


#### Commands <a name="linux.commands"></a>




</br>

--------------------------------------------------------------------------------

### GIT <a name="git"></a>


#### Installation <a name="git.install"></a>


#### Commands <a name="git.commands"></a>




</br>

--------------------------------------------------------------------------------

### Docker <a name="docker"></a>


#### Installation <a name="docker.install"></a>  

1. Set up the repository  
1.1. Update the apt package index and install packages to allow apt to use a repository over HTTPS:
  ```
  $ sudo apt update
  $ sudo apt install apt-transport-https ca-certificates curl gnupg-agent software-properties-common
  ```  
1.2. Add Docker’s official GPG key:  
  ```
  $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
  ```  
1.3. Verify that you now have the key with the fingerprint 9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88, by searching for the last 8 characters of the fingerprint:  
  ```
  $ sudo apt-key fingerprint 0EBFCD88

  pub   rsa4096 2017-02-22 [SCEA]
        9DC8 5822 9FC7 DD38 854A  E2D8 8D81 803C 0EBF CD88
  uid           [ unknown] Docker Release (CE deb) <docker@docker.com>
  sub   rsa4096 2017-02-22 [S]
  ```  




#### Commands <a name="docker.commands"></a>




</br>

--------------------------------------------------------------------------------

### PostgreSQL <a name="postgres"></a>


#### Installation <a name="postgres.install"></a>


#### Commands <a name="postgres.commands"></a>




</br>

--------------------------------------------------------------------------------



