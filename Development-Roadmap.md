This is a list of what is considered more or less high priority in the project, and things that are in progress right now. The numbers of features in each release are intended to comply with short (or shortest as possible) development cycles.

## Webcamoid 8.6.0

### Storing/Restoring device configs

issue [#62](https://github.com/webcamoid/webcamoid/issues/62).

**Done**

### Packaging and source control improvements

Add support for MSYS2.  
Support CI for FreeBSD.  
Add static code analysis.  
Daily builds.  

**Done**

### Improve GStreamer support

Until now GStreamer was used as an alternative codec framework to FFmpeg, in case FFmpeg was not available in the target system. To provide an acceptable quality of formats and codecs, only those GStreamer plugins marked as GST_RANK_PRIMARY was enabled by default. The result of the that is the big lack of common formats and codecs. The rank must be lowered and formats and codecs must be tested thoroughly to fix issues and ensure a good quality result.

### Add a new control area on top of frame

Allow plugins to put user controls (buttons, sliders, comboboxes, etc.) on top of the frame. This can be used to create draw plugins and plugins depending on visual cues relative to the frame.

## Webcamoid 9.0.0

The much expected platform limits breaking release.

### Android port

Make Webcamoid work in Android. It must be available in F-Droid (free) and Play Store (donation pay).

### New GUI

Current GUI doesn't play well with mobile and small screens at all and it's outdated anyways. This is a big requirement for Android port.

### Scripted plugins (aka Add-ons)

Current plugin model is ok for high performance frame process and low level system access in case you want to add support for some hardware device, but is a pain in the ass if you want to distribute your own plugins outside Webcamoid's tree, and target multiple platforms. So, the best way to solve this issue is to allow developers to create platform independent plugins using an scripting language, in this case using Qml and JavaScript duo. It could be modeled after [WebExtensions](https://developer.mozilla.org/en-US/Add-ons/WebExtensions) (but without the web, obviously).

### Plugin repository support

Once the developer has completed writing the their Add-ons, the next step is distributing it. One way will be distributing it through compressed packages, and it's ok and will be possible to do so, but this leads to a big problem: upstream syncing and security updates, that's why a plugin repository is needed. 
The repository will be designed to be decentralized, including repositories index, and using a VCS infrastructure, so developers will be able to create and distribute their Add-ons, create repositories and repositories index, through their Github, Gitlab, Bitbucket, other VCS instance, or their own VCS instance. The VCS infrastructure will be implemented in git first, other VCS systems could be added later. You have a good example of this design [here](https://github.com/Homebrew).
