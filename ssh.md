# ssh Linux Command

ssh is an OpenSSH remote login client

## The Secure Shell (SSH) Protocol

It is a network protocol that enables two computers to communicate and share data
An inherent feature of ssh is that the communication between the two computers is encrypted - 
suitable for insecure networks

### Operation
It operates as a layered protocol suite comprising three principles hierarchical components:
- the transport layer: provides server authentication, confidentiality, and integrity
- the user authentication protocol: validates the user to the server
- the connection protocol - multiplexes the encrypted tunnel into multiple logical communication
 channels

#### Public-Key Cryptography Authentication Methodologies
It uses public-key cryptography to authenticate the remote host and allow it to authenticate the 
user, if necessary.

Methodology | Description
----------- | -----------
auto-generated public-private key pairs | these pairs are used to encrypt the network connection, and then use of a password to authenticate the user
manually-generated public-private key pairs | authentication is essentially performed when the key pair is created, and a session may then be opened automatically without a password prompt

List of authorized public keys is typically stored in the home directory of the user that is allowed to log in remotely, in the file `~/.ssh/authorized_keys`. The file is respected by SSH only if it is not writable by anything apart from the owner and root.

When the public key is present on the remote end and the matching private key is present in the local end, typing in the password is no longer necessary. However, for additional security the private key itself can be locked with a passphrase.

To produce the public-private key pairs, type the command:
```sh
$ ssh-keygen
```
SSH also supports password based authentication that is encrypted by automatically generated keys. Man-in-the-middle attacks are, however, successfull if the two sides have never authenticated before, as SSH remembers the key that the server side previously used.

The SSH client raises a warning before accepting the key of a new, previously unknown server. Password authentication can be disabled from the server side.

## SSH Applications
They are based on client-server architecture, connecting an SSH client instance with an SSH server.
SSH can be of three types SSH 1, SSH 2, and OpenSSH (from OpenBSD project). Some Linux distributions such a sRed Hat include both client and server packages by default.
Others, such as Ubuntu, supply client package only.
The system allows incoming network connections on TCP port 22.

To try a loopback interface, ensure OpenSSH-Server package is installed and use localhost as name of remote host. The machine will establish connections with itself.
 
## Examples
To connect to a remote host named remote-sys:

```sh
$ ssh remote-sys

```

To connect to bob's account in a remote host named remote-sys:

```sh
$ ssh bob@remote-sys

```

To execute a single command on a remote system:

```sh
$ ssh remote-sys free

```

To perform an `ls` on remote system and redirect output to a file on the local system:

```sh
$ ssh remote-sys 'ls -la' > output.txt

```
We use ls -la in quotes because we want path expansion performed on the remote system.

To redirect output to a file in the remote host, we would place the redirection operator and the filename within the single quotes:

```sh
$ ssh remote-sys 'ls -la > output.txt' 

```

To exit from a remote login session:
```sh
$ exit

```

### Common Error Handling
When a first time connection is attempted, a message is displayed indicating that the authenticity of the remote host cannot be established. This is because the client program has never seen this remote host before.
When prompted, enter yes and the password.

In other cases of authentication errors, the causes might be:
- a man-in-the-middle attack
- the OS or SSH Server has been reinstalled

To troubleshoot, first contact the administrator of the remote host before working on the local machine. If the remote side is okay, remove the obsolete key from the `~/.ssh/known_hosts` file using a text editor of your choice. The erroneous line will probably be highlighted in the error message.
