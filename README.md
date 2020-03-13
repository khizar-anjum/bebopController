bebopController
=======
This repo is built on [Samples Repo](https://github.com/Parrot-Developers/Samples) by Parrot Developers. It is built by using Parrot's [ARSDK3](https://developer.parrot.com/docs/SDK3/). While, it can be extended to Android and iOS, for now, it is only intended to be used as a Python Library on Unix platform. Much of the code used as a base is taken from parent repo and is written in C. However, you can port it and use it with Python as a scripting language.

Functionality
---------------
This repo has functions implemented which will allow you to connect, pilot, take pictures, display video stream if available, and download medias from the drone.

It supports the following drones:

* Bebop 2
* Bebop 

But is only tested to work on Unix-based (native) systems. 

Native samples
---------------

#### [BebopSample](https://github.com/ARDroneSDK3/Samples/tree/master/Unix/BebopSample)
This example enables you to **connect** to a Bebop drone and **send and receive commands** to pilot it and get its battery level. It also **receives the video stream**. <br/>

To use it, you'll need to [download](http://developer.parrot.com/docs/SDK3/#download-all-sources) and [compile your own sdk](http://developer.parrot.com/docs/SDK3/#how-to-build-the-sdk).<br/>
Once done, in the sdk root folder, you can build the sample:<br/>
`./build.sh -p arsdk-native -t build-sample-BebopSample -j`
Then run it:<br/>
`./out/arsdk-native/staging/native-wrapper.sh ./out/arsdk-native/staging/usr/bin/BebopSample`

or if you are on a MacOs computer:<br/>
`./out/arsdk-native/staging/native-darwin-wrapper.sh ./out/arsdk-native/staging/usr/bin/BebopSample`


