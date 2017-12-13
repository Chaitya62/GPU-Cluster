# Setting Up SSH

## What is SSH? 
Secure Shell (SSH) is a cryptographic network protocol for operating network services securely over an unsecured network.The best known example application is for remote login to computer systems by users.
In simple language it basically let's you control the terminal of any computer in a network remotely and it is very much secure.


## What will we use ? 

We will use [openSSH](https://www.openssh.com/) server.
It provides ssh, scp and sftp.
We will be using ssh and scp most of the times.

## Setup

### 1. Install openSSH

```bash
    sudo apt-get install openSSH.
```

Once the installation is complete for the first time you have to start the service manually.

```bash
    sudo service ssh start
```
This has to be done only the first time after that SSH is started automatically during boot.


For testing install openSSH in two computer and check if you can ssh into one of them using the follwoing command.

```bash
    ssh username@ipaddress
``` 
This will prompt for the password of the username.
**Note:** I recommend to create a separate user for your MPI/GPU cluster and give it the same name and password for all the computers. This will  simplify our setup.

If everything works so far and you are able to SSH into other PCs. You have successfully installed SSH.
**Do this for all the nodes in your network.**

While this will setup SSH successfully there is one things which still needs to be fixed.
Right now if you try to SSH into other PCs it will give a prompt for the password.
We want to setup passwordless login.

## Setting up passwordless SSH

For setting up passwordless SSH we need to understand some files.

We will have a `.ssh`  folder in the `home`(~) of our user.
It will contain the following files.
```bash
.ssh
    authorized_keys
    known_hosts
    id_rsa
    id_ras.pub
```
#### authorized_keys
Holds a list of authorized public keys for servers. When the client connects to a server, the server authenticates the client by checking its signed public key stored within this file

### known_hosts
Contains DSA host keys of SSH servers accessed by the user. This file is very important for ensuring that the SSH client is connecting the correct SSH server.

To understand the difference between the above files readmore [here](https://security.stackexchange.com/questions/20706/what-is-the-difference-between-authorized-keys-and-known-hosts-file-for-ssh)

### id_rsa 
This contains the rsa key 

### id_rsa.pub
This contains the public rsa key

Now for setting up passwordless SSH we want our id_rsa.pub into the authorized_keys of the target PC.






