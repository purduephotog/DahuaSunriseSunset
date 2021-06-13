# DahuaSunriseSunset
A Windows Service which changes the profile of dahua cameras between Night and Day at each sunset and sunrise.

## Requirements

1) Windows OS
2) One or more Dahua IP cameras to control, accessible by http or https.

## Usage

1) Download from here: https://github.com/bp2008/DahuaSunriseSunset/releases
2) Run `DahuaSunriseSunset.exe` to open the service manager GUI.

![Service Manager](https://i.imgur.com/qIJZPOT.png)

3) Click `Configure Service`.  Your location (latitude and longitude) is used to determine the time of sunrise and sunset.  In this example, two (imaginary) cameras located in Denver, CO will be switched to day profile one hour before sunrise.  Night profile will be enabled one hour after sunset.

![Configuration](https://i.imgur.com/a9cKsuO.png) ![Add Camera](https://i.imgur.com/jqELba5.png)

4) Install and Start the service, using the buttons in the service manager.
Note: The Camera should be IP, no http or https, and no trailing slash- pure numerics.

If the service is running when you modify configuration, then for best results you should stop and restart the service.  If you forget to restart the service, the new configuration will be learned at the next profile switch.

The buttons `Simulate Sunrise` and `Simulate Sunset` will cause the program to enable Day and Night profiles, respectively, in all configured cameras.

## Camera Configuration

Configure the camera's **Conditions** the way you want them using the camera's web interface.

If the service isn't able to switch the camera's profile, try going to **Profile Management** and choosing **Full Time**:

![Profile Management Screenshot](https://i.imgur.com/s6JACCu.png)

## Building from source

This project is built with Visual Studio 2017 (Community Edition).  To build from source, you will also need my general-purpose utility library, which must be downloaded separately, here: https://github.com/bp2008/BPUtil
