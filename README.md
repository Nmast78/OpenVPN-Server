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

<ins>\*NOTE\* - Not all files generated and needed to run the VPN are included in this repository. There are simply too many files across too many machines to assemble them all here.  The files included are more of the important proof of concept ones I felt needed to be included. Thank you!</ins>
