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

Instructions for building properly
---------------

To use it, you'll need to [download](http://developer.parrot.com/docs/SDK3/#download-all-sources) and [compile your own sdk](http://developer.parrot.com/docs/SDK3/#how-to-build-the-sdk).<br/>
Remember, so far, it only works if built for arsdk-native.
However, this package is not a part of the official SDK by Parrot, so you would have to make a few changes in the build directory before building it. After downloading the SDK3, go through the following steps:

1. Once in the SDK root, folder, go to `packages` folder, and clone this repository:   
`cd packages`  
`git clone https://github.com/khizar-anjum/bebopController.git`  

2. Go back and delete the `products/arsdk` directory:  
`cd ../products`  
`rm -r arsdk`  
`git clone https://github.com/khizar-anjum/arsdk_products.git`  

Alternatively, you can just chnage `line 168` in `<SDK_ROOT>/products/arsdk/build_cfg.py` to:  
`    samples = ["BebopSample", "JumpingSumoSample", "BebopController"]`  

3. To be sure, in the sdk root folder, execute:  
`./build.sh -p arsdk-native -tt`  
If `build-sample-BebopController` and `clean-sample-BebopController` show up as available tasks, then you have done the procedure correctly.

4. Once done, in the sdk root folder, you can build the bebopController:<br/>
`./build.sh -p arsdk-native -t build-sample-BebopController -j`  
Then run it:<br/>
`./out/arsdk-native/staging/native-wrapper.sh ./out/arsdk-native/staging/usr/bin/BebopController`  
or if you are on a MacOs computer:<br/>
`./out/arsdk-native/staging/native-darwin-wrapper.sh ./out/arsdk-native/staging/usr/bin/BebopController`  


