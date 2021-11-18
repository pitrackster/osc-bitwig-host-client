# Use a tablet to control Bitwig via Open Stage Control

> Done with ubuntu and an iPad


## Definitions
- Host: computer hosting Bitwig and Open Sound Control app
- Client: your tablet / computer that will send messages to the host

## Steps

This are the steps I followed to make it work


### Install Driven By Moss bitwig extension 


> Pay attention to the extension version according to your current Bitwig version


- Download [Driven by Moss bitwig extension](http://www.mossgrabers.de/Software/Bitwig/Bitwig.html)  
- Copy `DrivenByMoss.bwextension` in `{USERHOME}/Bitwig Studio/Extensions/` folder

### Install and configure Open Stage Control

- Download [Open Stage Control](https://openstagecontrol.ammd.net/) and install it on your host
- Launch Open Stage Control and configure it as shown below

![Open Stage Control conf window](./assets/osc_osc_conf_window.png "Open Stage Control conf window")


### Make a wifi hotspot

Your "host" (computer hosting Bitwig and Open Sound Control app) and "client" (Tablet/iPad/Other computer) need to be on the same network so create a wifi hotspot in your computer and connect your "client" to this hotspot

> I think this is not mandatory, you could just be connected to the same wifi network... but then you'd probably have to open your internet router to let your client come in and you'd probably face latency issues...


### Add a controller in Bitwig

- Add an Open Sound Control controller in bitwig and leave the default configuration

> You must select a midi device... on my computer I just enable Alsa Virtual MIDI (`modprobe snd-virmidi`) and select one of the virtual device

![Bitwig OSC controller configuration](./assets/osc_bitwig_conf.png "Bitwig OSC controller configuration")


### Go go go !

- Launch Open Stage Control server by hiting the "play" button

![Open Stage Control launch server](./assets/osc_launch_server.png "Open Stage Control launch server")

- With debug enabled you'll see some IP:PORT appearing, one of them is the one you should use to connect your client to the host (10.42.0.1:8080 in the example below)

![Open Stage Control IPs](./assets/osc_console_ips.png "Open Stage Control IPs")

- Open a webbrowser in your "client" (I used Firefox in my iPad) and enter the adress and Tada !

![Open Stage Control on iPad](./assets/osc_ipad_firefox.png "Open Stage Control on iPad")
