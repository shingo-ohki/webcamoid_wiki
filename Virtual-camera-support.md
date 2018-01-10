A virtual webcam is a program that create some interfaces that other programs can detect and interact as it were a real webcam hardware, creating fake devices nodes. Creating a virtual webcam may involve in most cases very low level system access, and that depends on how much the operating system allow software developers to have access to the lower level.  

## GNU/Linux ##

Webcamoid create the virtual webcam through [v4l2loopback](https://github.com/umlaeute/v4l2loopback), if webcam programs list the webcams from _/dev/video*_ and they are are not very picky about resolutions or formats, it will work well. If the programs detects the webcams by listing USB devices, the programs will be not able to detect the webcam, but it will be possible in a future.

## Mac ##

Creating a virtual webcam in Mac is fully supported, but only available in development branch. 

## Windows ##

Virtual camera works out of the box in Windows. If you are running Windows 64 bits, and want to use the virtual webcam with Skype you must install Webcamoid 32 bits, otherwise it will not detect the virtual webcam.

## Other operating systems ##

Other operating system (like Android and FreeBSD) are not supported yet.
