A virtual webcam is a program that create some interfaces that other programs can detect and interact as it were a real webcam hardware, creating fake devices nodes. Creating a virtual webcam may involve in most cases very low level system access, and that depends on how much the operating system allow software developers to have access to the lower level.  

## GNU/Linux ##

Webcamoid create the virtual webcam through [v4l2loopback](https://github.com/umlaeute/v4l2loopback), if webcam programs list the webcams from _/dev/video*_ and they are are not very picky about resolutions or formats, it will work well. If the programs detects the webcams by listing USB devices, the programs will be not able to detect the webcam, but it will be possible in a future.  
Following compatibility table is based on tests made using v4l2loopback:

:green_heart: Works  
:yellow_heart: Works under some conditions  
:heart: Does not works

<table>
    <thead>
        <tr><th>Program</th><th>Works?</th><th>Notes</th></tr>
    </thead>
    <tbody>
        <tr><td>Cheese</td><td>:heart:</td><td>Only real cameras are detected</td></tr>
        <tr><td>ffmpeg</td><td>:green_heart:</td><td></td></tr>
        <tr><td>ffplay</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Firefox Adobe Flash Player</td><td>:heart:</td><td>Only real cameras are detected</td></tr>
        <tr><td>Firefox HTML5</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Google Chrome Adobe Flash Player</td><td>:heart:</td><td>Not detecting any webcam in general</td></tr>
        <tr><td>Google Chrome HTML5</td><td>:heart:</td><td>Only real cameras are detected</td></tr>
        <tr><td>GStreamer</td><td>:green_heart:</td><td></td></tr>
        <tr><td>guvcview</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Kamoso</td><td>:heart:</td><td>Only real cameras are detected</td></tr>
        <tr><td>mplayer</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Opera Adobe Flash Player</td><td>:heart:</td><td>Not detecting any webcam in general</td></tr>
        <tr><td>Opera HTML5</td><td>:heart:</td><td>Only real cameras are detected</td></tr>
        <tr><td>Skype</td><td>:green_heart:</td><td></td></tr>
        <tr><td>VirtualBox</td><td>:green_heart:</td><td></td></tr>
        <tr><td>VLC</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Wine v4l2loopback</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Wine DirectShow</td><td>:green_heart:</td><td>Virtual camera for Windows works for other Windows apps in Wine based on <b>Webcamoid 8.5.0</b> tests</td></tr>
    </tbody>
    <tfoot>
        <tr><th>Program</th><th>Works?</th><th>Notes</th></tr>
    </tfoot>
</table>

## Mac ##

Creating a virtual webcam in Mac is fully supported, but only available in development branch.  
Following compatibility table is based on tests made in development branch (future **Webcamoid 8.5.0**):

:green_heart: Works  
:yellow_heart: Works under some conditions  
:heart: Does not works

<table>
    <thead>
        <tr><th>Program</th><th>Works?</th><th>Notes</th></tr>
    </thead>
    <tbody>
        <tr><td>CamTwist</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Firefox Adobe Flash Player</td><td>:heart:</td><td></td></tr>
        <tr><td>Firefox HTML5</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Google Chrome Adobe Flash Player</td><td>:heart:</td><td>Flash not working</td></tr>
        <tr><td>Google Chrome HTML5</td><td>:green_heart:</td><td></td></tr>
        <tr><td>ManyCam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Photo Booth</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Safari</td><td>:heart:</td><td>Nothing works</td></tr>
    </tbody>
    <tfoot>
        <tr><th>Program</th><th>Works?</th><th>Notes</th></tr>
    </tfoot>
</table>

## Windows ##

In **Webcamoid 8.1.0**, Virtual camera works out of the box in Windows. If you are running Windows 64 bits, and want to use the virtual webcam with Skype you must install Webcamoid 32 bits, otherwise it will not detect the virtual webcam.  
Following compatibility table is based on tests made in development branch (future **Webcamoid 8.5.0**):

:green_heart: Works  
:yellow_heart: Works under some conditions  
:heart: Does not works

<table>
    <thead>
        <tr><th>Program</th><th>Works?</th><th>Notes</th></tr>
    </thead>
    <tbody>
        <tr><td>AlterCam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>AMCap</td><td>:heart:</td><td></td></tr>
        <tr><td>aMSN</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Bandicam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>CyberLink PerfectCam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>CyberLink YouCam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Firefox Adobe Flash Player</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Firefox HTML5</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Free2X Webcam Recorder</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Google Chrome Adobe Flash Player</td><td>:heart:</td><td>Not detecting any webcam in general</td></tr>
        <tr><td>Google Chrome HTML5</td><td>:green_heart:</td><td></td></tr>
        <tr><td>GraphEdit</td><td>:green_heart:</td><td></td></tr>
        <tr><td>GraphStudioNext</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Internet Explorer</td><td>:heart:</td><td></td></tr>
        <tr><td>iSpy</td><td>:green_heart:</td><td></td></tr>
        <tr><td>ManyCam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Microsoft Edge</td><td>:heart:</td><td>UWP apps does not supports DirectShow filters</td></tr>
        <tr><td>Open Broadcaster Software (OBS)</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Pidgin</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Skype for Desktop</td><td>:green_heart:</td><td></td></tr>
        <tr><td>Skype UWP</td><td>:heart:</td><td>UWP apps does not supports DirectShow filters</td></tr>
        <tr><td>SparkoCam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>SplitCam</td><td>:green_heart:</td><td></td></tr>
        <tr><td>VirtualBox</td><td>:heart:</td><td>Can detect the camera, but on guest it show a blue frame with some predefined formats.</td></tr>
        <tr><td>VLC</td><td>:green_heart:</td><td></td></tr>
        <tr><td>WebCam2000</td><td>:heart:</td><td></td></tr>
        <tr><td>WebcamMax</td><td>:green_heart:</td><td></td></tr>
        <tr><td>WebcamViewer</td><td>:green_heart:</td><td></td></tr>
        <tr><td>webcamXP</td><td>:heart:</td><td></td></tr>
        <tr><td>Yawcam</td><td>:heart:</td><td>Crash</td></tr>
    </tbody>
    <tfoot>
        <tr><th>Program</th><th>Works?</th><th>Notes</th></tr>
    </tfoot>
</table>

## Other operating systems ##

Other operating system (like Android and FreeBSD) are not supported yet.
