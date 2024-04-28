Webserver vulnerability scanner

    sudo apt update && sudo apt install nikto

## Usage:

    nikto -h TARGET_IP

    nikto -h 10.10.12.121:8080

Scanning Multiple Hosts & Ports:

Nikto is extensive in the sense that we can provide multiple arguments in a way that's similar to tools such as Nmap. In fact, so much so, we can take input directly from an Nmap scan to scan a host range. By scanning a subnet, we can look for hosts across an entire network range. We must instruct Nmap to output a scan into a format that is friendly for Nikto to read using Nmap's  -oG  flags

For example, we can scan 172.16.0.0/24 (subnet mask 255.255.255.0, resulting in 254 possible hosts) with Nmap (using the default web port of 80) and parse the output to Nikto like so:

    nmap -p80 172.16.0.0/24 -oG - | nikto -h - 


Scanning multiple ports on one specific host with "p" paramter:

    nikto -h 10.10.10.1 -p 80,8000,8080


Introduction to Plugins :

List all plugins : `--list-plugins`

Usege plugins : 

    -Plugin PLUGIN_NAME

    -Plugin apacheusers

`apacheusers` : Attempt to enumerate Apache HTTP Authentication Users

`cgi` : Look for CGI scripts that we may be able to exploit

`robots` : Analyse the robots.txt file which dictates what files/folders we are able to navigate to

`dir_traversal` : Attempt to use a directory traversal attack (i.e. LFI) to look for system files such as /etc/passwd on Linux (http://ip_address/application.php?view=../../../../../../../etc/passwd)




---
[Tools](../tools.md) | [Ana Sayfa](../README.md)