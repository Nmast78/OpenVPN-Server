<h1 align="center" style="color">OpenVPN-Server </h1>
<p align="center">Personal VPN Server Running on Linux</p>
<p align="center">This is a project I completed over winter break 2024-2025 where I configured and built my own private VPN using the OpenVPN framework.  This project uses the latest Ubuntu 24.04 OS, WSL (Windows Subsystem for
Linux), and Easy-RSA (Public Key Infrastructure Management Solution).</p>

<ins>The link for the tutorial I followed</ins><br/>
https://www.digitalocean.com/community/tutorials/how-to-set-up-and-configure-an-openvpn-server-on-ubuntu-20-04

Some helpful knowledge...

<ins>OpenVPN</ins><br/>
OpenVPN is an open source software that allows you to create your own private VPN. It is used by hundreds of companies and is known for its security and trustworthiness.

<ins>Easy-RSA</ins><br/>
Easy-RSA is a software tool used to create and manage a PKI (Public Key Infrastructure). A PKI is a framework that enables the secure transfer of information over the internet using crypotgraphic techniques.  In this project I used Easy-RSA to generate private and public keys, sign certificates, and manage certificates.

<ins>CA Server</ins><br/>
A Certificate Authority Server is a server that handles issuing, revoking, and managing of digital certificates for our Easy-RSA PKI. In this project I use my CA Server to issue and validate certificates for my server and clients.


1. Installation and Creating PKI
2. Setting Up CA (Certificate Authority) Server
3. Creating and Signing Certificate
4. Configuring OpenVPN
5. Firewall Configuration
6. Creating Client Configurations
7. Testing

<h2>Installation and Creating PKI</h2>

First, your are going to want to install openvpn and easy-rsa on the computer you intend your VPN server to be. For me, this was my ThinkPad running Ubuntu.
    
```bash
$ sudo apt install openvpn easy-rsa
```

Next create a new directory in your home folder as your non-root user called easy-rsa:

```bash
$ mkdir ~/easy-rsa
```

After that, you will need to create a symbolic soft link to the easyrsa script installed when you installed easy-rsa. A symbolic link is essentially a file that points to another file. If you are not comfortable with symbolic links you can also just copy the files in the path specified below. However, any updates to the original files will not be represented in your copies.

```bash
$ ln -s /usr/share/easy-rsa/* ~/easy-rsa
```

Finally, change the owner of the directory to your non-root user and set appropriate permissions to only allow access to that user. Here is a good link to explain linux file permissions:
https://www.redhat.com/en/blog/linux-file-permissions-explained

```bash
$ sudo chown *userHere* ~/easy-rsa
$ chmod 700 ~/easy-rsa
```

The next step is creating the servers Public Key Infrastructure (PKI). This infrastructure will manage the public and private keys, as well as the digital certificates we will create for our clients.
Move into the easy-rsa directory in your user's home directory and create a file called 'vars' with the text editor of your choosing, I prefer Vim.

This file only needs two lines. The first one ensures our keys use Elliptic Curve Cryptography (ECC), a key-based method to encrypt data. The second line specifies we will be using SHA-512, which is a hashing algorithm to create a unique hash of our certificate's contents.

```bash
set_var EASYRSA_ALGO "ec"
set_var EASYRSA_DIGEST "sha512"
```

This file is used by easyrsa to create your PKI.  This PKI is just used here as a place to store certificates as the actual validation and signing will be dont by the CA server we setup in step 2.

```bash
$ ./easyrsa init-pki
```

<h2>Setting Up CA (Certificate Authority) Server</h2>

A Certificate Authority server is a server whos sole purpose is to issue digital certificates to verify clients on the internet. This is a popular and secure way to allow your OpenVPN server to trust the clients that connect to it and vice-versa.  For my CA server, I used WSL on my home desktop.  My WSL is using Ubuntu 24.04, just like my OpenVPN server.

The first steps are very similar to what we did above.

Install Easy-RSA

<h2>Creating and Signing Certificate</h2>


<h2>Configuring OpenVPN</h2>


<h2>Firewall Configuration</h2>


<h2>Creating Client Configurations</h2>


<h2>Testing</h2>

