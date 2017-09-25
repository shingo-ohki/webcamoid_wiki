A virtual webcam is a program that create some interfaces that other programs can detect and interact as it were a real webcam hardware, creating fake devices nodes. Creating a virtual webcam may involve in most cases very low level system access, and that depends on how much the operating system allow software developers to have access to the lower level.  

In most Free and Open Source operating systems this is not a problem, and depends on how well documented are their API, so virtual webcam support here is 100% guaranteed if they provide good interfaces and documentation.

Supporting virtual webcam for proprietary operating systems may impose more restrictive measures for having lower level access, like creating system drivers. Sometimes they may require code signing, or ever worse, non-disclosure of source code, that will affect Free Software code model of Webcamoid. In that case, Webcamoid will always provide a Free Software alternative, that may not be perfect, but at least provide some sort of solution. Other software projects are encouraged to use the same interfaces Webcamoid use to create a smooth interaction between us.

Supporting signed drivers is not discarded if some users are interested in so, but at this point of development is not possible to provide that solution.

## GNU/Linux ##

Webcamoid create the virtual webcam through [v4l2loopback](https://github.com/umlaeute/v4l2loopback), if webcam programs list the webcams from _/dev/video*_ and they are are not very picky about resolutions or formats, it will work well. If the programs detects the webcams by listing USB devices, the programs will be not able to detect the webcam, but it will be possible in a future.

## Mac ##

Creating a virtual webcam in Mac involves creating a Kernel Extension (kext) and [signing it](https://developer.apple.com/library/content/documentation/Darwin/Conceptual/KEXTConcept/KEXTConceptAnatomy/kext_anatomy.html#//apple_ref/doc/uid/20002364-SW1), so it's unlikely to provide to provide a solution that interact with other webcam programs in this way.

Alternatively, Webcamoid supports [Syphon](https://github.com/Syphon/Syphon-Framework) that's a framework that allow sharing frames between programs that have support for it, you can check [Syphon website](http://syphon.v002.info/) for which programs supports Syphon. 

## Windows ##

Webcamoid create the virtual camera as a DirectShow filter, so all programs supporting webcam capture from DirectShow can capture frames from Webcamoid.

Some other programs may use [Microsoft Media Foundation](https://msdn.microsoft.com/en-us/library/windows/desktop/ms694197(v=vs.85).aspx) for webcam capture, making it incompatible with DirectShow filters. It may be required to create a [KMDF or UMDF driver](https://en.wikipedia.org/wiki/Windows_Driver_Frameworks) to make the virtual webcam work in this programs. This is actually under research.

## Other operating systems ##

Other operating system (like Android and FreeBSD) are not supported yet.
