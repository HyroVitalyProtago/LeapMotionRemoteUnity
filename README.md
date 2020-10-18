# LeapMotionRemoteUnity
Some code to use the Leap Motion remotely in Unity based on Websockets

For example, you can use it with VirtualHere on your Standalone Virtual Reality Headset as the Oculus Quest or the Pico Neo, connect your Leap Motion on the headset directly and let a remote pc compute hands data for you and access it remotely in your Unity Android app on your headset.

- 1) add two Plugins to your Unity Project (so under a Plugins folder in your Assets):
  - [websocket-sharp](https://github.com/sta/websocket-sharp)
  - [Newtonsoft.Json](https://www.newtonsoft.com/json)
- 2) add the [Leap Motion Unity Core Plugin](https://developer.leapmotion.com/unity)
- 3) add the scripts of this repository to your project, replace the `IController.cs` code by the one in this repository and fix the Leap Motion code:
  - replace the Controller type by IController in the LeapServiceProvider : `protected IController _leapController;`
  - propagate the change everywhere to remove errors
- 4) unsure in the Leap Control Panel that you give access to web applications
- 5) use the Leap Motion SDK as normal, and just check the `Remote Connection` box in the `LeapServiceProvider` or `LeapXRServiceProvider` in the Unity inspector
- 6) by default, the Leap Motion software is configured to allow only local connection on the hidden webserver, so don't forget to enable the "websocket_allow_remote" in the config file (like explained here https://forums.leapmotion.com/t/read-leap-data-from-guest-vm-on-host-machine-using-websockets/1523/10 and there https://developer.leapmotion.com/documentation/v4/configuration.html) and restart the leap software
- 7) if that don't work, check your anti-virus or firewall on your pc
