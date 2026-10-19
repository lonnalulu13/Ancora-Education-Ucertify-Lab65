# Ancora-Education-Ucertify-Lab65
# Configuring Linux Firewall using iptable

> **Original Lab Source**
> 
> This lab was available through:
>
> [https://ancoraeducation.ucertify.com/app/?func=navigate_items&item_sequence=18]

## Objective of the Lab 
In this lab, you will learn to configure a Linux firewall using the iptable. The Iptable is the command-line firewall utility that uses the policy chains to allow or block the traffic. When a connection tries to establish itself on your system, iptables look for a rule in its list to match it to. If it doesn’t find any rule, it resorts to the default action. 
## Instructions 
### STEP 1 
From the bottom-left bar, for the Ubuntu tab, click On/Connect to power on the machines. 
### STEP 2 
From the bottom-left bar, for the Base VM tab, click On/Connect to power on the machines. 
### STEP 3
From the taskbar, click the Search icon. 
### STEP 4
In the Search box, type (command prompt) and click Command Prompt. 
### STEP 5
In the Command Prompt window, execute the following command to verify that you are able to ping Ubuntu (192.168.1.243):
```bash
ping 192.168.1.243
```
### STEP 6 
Minimize the Command Prompt window. 
### STEP 7
From the desktop, open PuTTY. 
### STEP 8
In the PuTTY Configuration dialog box, in the Host Name (or IP address) text box, type (192.168.1.243), and click Open. 
### Caution
If the PuTTY Security Alert prompt appears, click Yes. 
### STEP 9
In the PuTTY terminal window, type the following details and press Enter to log into the PuTTY terminal window: 

a.login as: ucertify

b.password: ucertify 
### Caution
You will not be able to observe the password being typed in. 
### STEP 10
In the PuTTY terminal window, execute the following command to drop all ICMP packets sent from any host:
```bash
sudo iptables -A INPUT -p icmp --icmp-type echo-request -j REJECT
```
### CAUTION
When asked for the password, type (ucertify) and press Enter. 
### Note 
* sudo: It allows to temporarily elevate the current user account to have root privileges.
* INPUT: It is a standard built-in chain.
* -p icmp: It sets the IP protocol for the rule; it is icmp in this case.
* -j: It tells the iptables to jump to a particular target when a packet matches a particular rule.
* REJECT: It rejects the packet without responding to the requester.
### STEP 11
Minimize the PuTTY terminal window. 
### STEP 12 
From the taskbar, switch back to the Command Prompt window. 
### STEP 13
In the Command Prompt window, execute the following command and try to ping Ubuntu:
```bash
ping 192.168.1.243
```
### STEP 14
You will not receive any echo-reply messages from Ubuntu. 
### STEP 15
From the taskbar, switch back to the PuTTY terminal window. 
### STEP 16
In the PuTTY terminal window, execute the following command to flush all rules from the input chain:
```bash
sudo iptables -F
```
### STEP 17
Switch back to the Command Prompt window. 
### STEP 18
In the Command Prompt window, execute the following command and again try to ping Ubuntu:
```bash
ping 192.168.1.243
```
### STEP 19
You will observe that you can ping your Ubuntu's host again after the rules get flushed in Ubuntu. 
### STEP 20
Close all windows. 
### STEP 21
At the PuTTY Exit Confirmation prompt, click OK.
## Disclaimer

This repository is for **educational and personal learning purposes only**.  

The original lab content belongs to **uCertify / Ancora Education** and remains their copyrighted material.  
This repository is not affiliated with, endorsed by, or sponsored by uCertify or Ancora Education.  

No copyright infringement is intended.  
Use of any tools or techniques mentioned here should only be performed in authorized, legal environments.
