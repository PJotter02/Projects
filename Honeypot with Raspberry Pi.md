# Raspberry Pi 4 Honeypot
Welcome to my tutorial for setting up a honeypot using a Raspberry Pi 4

## What You Will Need
- Raspberry Pi 4
- MicroSD
- MicroSD adapter to be able to plug MicroSD into computer

## Prepping Your Raspberry Pi
1) Login to your computer and navigate to https://www.raspberrypi.com/
2) On top of the webpage click on "software"
3) Download "Raspberry Pi Imager"
4) Open "Raspberry Pi Imager" and plug your MicroSD in
5) Select "Choose OS"
6) Select "Raspberry Pi OS (Other)"
7) Select "Raspberry Pi OS Lite (32-bit)"
8) Then, select "Choose Storage"
9) Select your MicroSD
10) Now press, CTRL + SHIFT + X, to open the advanced menu option
11) Set hostname to "raspberrypi"
12) If you have the option to configure your username make it "pi"
13) Ensure "Enable SSH" is checked
14) You can make the password for SSH anything you want
15) If you are using Wi-Fi, go ahead and configure
16) Select "save"
17) Select "write"
18) Once the OS has been loaded on to your MicroSD, you can eject

## Update Raspberry Pi
1) Plug in your MicroSD into your Raspberry Pi
2) Boot up your Raspberry Pi
3) On your desktop (not the raspberry Pi), open Windows Powershell
   - This can be done by searching Powershell in your windows search bar
4) Run this command "ssh pi@raspberrypi"
5) Then enter in the password you set up while configuring your Raspberry Pi OS
   - If done correctly, you will see "pi@raspberrypi:~"
6) Run this command "sudo apt update && sudo apt-get -uy dist-upgrade
7) Once download is complete, reboot your Raspberry Pi using this command "sudo reboot"
8) SSH back into your Raspberry Pi after a few minutes
   - Repeat steps 4 and 5

## Installing DShield
1) Once you have SSH back into your Raspberry Pi run this command to download git "sudo apt-get -y install git"
2) After git has finished installing run this command "git clone https://github.com/DShield-ISC/dshield.git"
3) Next run this command, "cd dshield/bin/", followed by this command "sudo ./install.sh"
4) After a bit you will see a warning, select "yes"
5) Select "yes" again
6) On the "Automatic Updates" page, select "automatic", then select "yes"
7) You will see a page with the header "DShield Account Information"
8) On your PC navigate to https://isc.sans.edu/honeypot.html and create an account
9) Once your account has been made, on the webpage select "My Account" and you will see your API key
10) Go back to PowerShell and enter in your account email address and the API key associated with your account
11) Once entered you should see "Your API key is valid", select "OK"
12) Leave the Default Interface set to "eth0" and select "OK"
13) On the "Local Network and Access" leave everything as default
    - Write down the "Local Network" IPs and the "Admin Port"
14) On the next page select "OK"
15) On the "IPs to Ignore for FW Log", leave the IP as the default
16) Select "OK"
17) On "IPs / Ports to disable Honeypot For" leave on default
18) Select "OK"
19) In a few moments a page with the header "Creating SSL Certificate", leave as default and select "OK"
20) In a few moments you'll see a page with the header "Signing Certificate" select "yes"
21) Now reboot your raspberry pi using the command "sudo reboot"

## Using Putty to SSH Using the Admin Access
### These are additional steps if you want to know your Raspberry Pi IP address
1) Navigate to https://www.putty.org/ on your PC and download Putty
2) Launch putty and fill in the below settings
3) ![image](https://github.com/user-attachments/assets/27f1e44a-62b3-4f70-ab56-5b6137ed1909)
4) Select "open"
5) If a warning pops up select "yes"
6) You will see a new window has openned with the prompt "login as:", enter "pi" then hit "enter"
7) Enter in the password you set to SSH into the Raspberry Pi

    
