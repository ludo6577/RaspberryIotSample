# Remote debugging with VS Code to a Raspberry PI using .NET Core and Microsoft IoT

This project display the Raspberry CPU temperature from a remote VS Code (windows or linux). It use Microsoft .NET Core and `Iot.Device.Bindings`. It's a sample project that will help you to start developping Iot apps on your Raspberry PI.

## Getting Started

Connect your raspery with an ethernet cable, clone this repository, edit the 2 files: launch.json and tasks.json (see below), run it and you are done! You should see the CPU temperature of your Rasberry PI from your VsCode Terminal.
Note: during the first run you will need to give execution access to the executable.

### Prerequisites

The things you need before installing running this project.

* .NET Core 3.1
* pscp
* plink

`Iot.Device.Bindings` will be restored automatically.

### Installation

A step by step guide that will tell you how to get the development environment up and running.

```
//Replace <USER> and <PASSWORD> by your Raspberry user and password in the following files:
// .vscode/launch.json in pipeArgs section:
"pipeArgs": [
	"-pw",
	"<PASSWORD>",
	"<USER>@raspberrypi.local",
],

// .vscode/tasks.json in args section:
"args" : [
	"-pw",
	 "<PASSWORD>",
	  "-v",
	  "-r",
	  "./bin/Debug/netcoreapp3.1/linux-arm/publish/*",
	  "<USER>@raspberrypi.local:/home/pi/iot"
]
```

Then in the first installation you will need to create manually the folder `RaspberryIotSample` in the Rasberry and give execution right to the exec file: `~/RaspberryIotSample/RaspberryIotSample`.

That is all! You can now run and debug this simple program from VsCode in remote!

### Troubleshooting

An issue ? Do not hesitate to open an issue on github, i will try my best to help you :)