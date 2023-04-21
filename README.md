# BLUETOOTH CONFIGURATION FOR ARCH LINUX

Bluetooth configuration for _Arch Linux_ (Endevour Os)

## INSTALLATION

- Install the ***bluez package***, providing the Bluetooth protocol stack.
- Install the ***bluez-utils package***, providing the bluetoothctl utility.
 Alternatively install ***bluez-utils-compat*** (with AUR) to additionally have the deprecated BlueZ tools.
- The generic Bluetooth driver is the btusb kernel module. Check whether that module is loaded. If it is not, then load the module.
- Start/enable bluetooth.service.

### INSTALL PACKAGES
~~~ sh
	$ sudo pacman -S bluez bluez-utils
~~~
### CONTROL BLUETOOTH MODULE

To see if the bluetooth module is present

~~~ sh
	$ lsmod | grep btusb
~~~
## CONFIGURATION
### START AND ENABLE BLUETOOTH SERVICE

~~~ sh
	$ sudo systemctl start bluetooth.service
~~~

~~~ sh
	$ sudo systemctl enable bluetooth.service
~~~

### START BLUETOOTHCTL
Launch the command of the bluetooth

~~~ sh
	$ bluetoothctl
~~~
#### Power on bluetooth
~~~ sh
	[bluetooth]$ power on
~~~
#### Set the agent

~~~ sh
	[bluetooth]$ agent on
~~~

~~~ sh
	[bluetooth]$ default-agent
~~~
#### SCAN DEVICES

~~~ sh
	[bluetooth]$ scan on
~~~

find and select the MAC ADDRESS of the devices you want to connect
#### TRUST
With this line we can remember the device even if is not connected
~~~ sh
	[bluetooth]$ trust <Mac Address>
~~~

#### PAIR

~~~ sh
	[bluetooth]$ pair <Mac Address>
~~~

#### CONNECT

~~~ sh
	[bluetooth]$ connect <Mac Address>
~~~

#### CLOSE SCAN AND EXIT
At the end power off the scan and exit

~~~ sh
	[bluetooth]$ scan off
~~~
~~~ sh
	[bluetooth]$ exit
~~~

## ON STARTUP
To Start it automatically at startup
~~~ sh
 	$ sudo vim /etc/bluetooth/main.conf
~~~

if is not working try use

~~~ sh
	$ sudo vi /etc/bluetooth/main.conf
~~~

And change the comment 
~~~
	AutoEnable=true
~~~


