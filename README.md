# KinectSetupGuide

Include Kinect Setup Guide and Libraries (OpenNI, NiTE, SensorKinect, &amp;&amp;More)

***

## Setting up the Kinect on macOS (Sierra)

With Apple buying out PrimeSense (Thanks Apple…), installing the Kinect on OSX has become a little fumbly. Here’s a step by step guide on getting it up and running.

### Disable System Integrity Proctection

System Integrity Protection (SIP) is a new default security measure introduced by Apple in OS X 10.11 onward. This rootless feature prevents Mac OS X compromise by malicious code, therefore locking down specific system level locations in the file system. This prevents the user from making changes to the system via Sudo commands. Therefore in order for us to proceed, we need to turn it off.

* Restart your Mac in Recovery mode
* Restart your Mac holding down `Cmd-R`
* Find  Terminal in the Utilities menu and type in the following : `csrutil disable`
Restart your Mac

Great! Easy start. Now we will be able to have full access.

### Download and install MacPorts

[http://www.macports.org/install.php](http://www.macports.org/install.php)

### Install Dependencies

* First we have to download a few libraries in order to get the USB port on your Mac working with the Kinect. If you haven’t got them already.
* Go into Terminal and type:

```
sudo port install libtool
```

* Now restart your Mac
* Next, install the development version of libusb. Type into Terminal:

```
sudo port install libusb-devel +universal
```

* Once its been installed, restart your Mac once again.

### Install OpenNI

* (Optional) Create a Kinect directory in Home to place all applications you’ll need to run the Kinect on the Mac.
* Open up Terminal and type in:

```
mkdir ~/Kinect
cd ~/Kinect
```

* As the download page from the Primesense website is not working. Here’s a link to the OpenNI unstable release. Do not try to Download OpenNI v2 beta as it relies solely on the Microsoft Kinect SDK which we cannot use. The version we are going to use is OpenNI SDK (V1.5.7.10)
* You can download here [https://mega.nz/#!yJwg1DJS!uJiLY4180QGXjKp7sze8S3eDVU71NHiMrXRq0TA7QpU](https://mega.nz/#!yJwg1DJS!uJiLY4180QGXjKp7sze8S3eDVU71NHiMrXRq0TA7QpU). **Or use this file in our repository: `/kinect/xxx`**
* Move the Zip file to your Kinect folder and double-click to uncompress and reveal the SDK folder.
* Open Terminal and navigate to the OpenNI SDK folder.
* Once in the folder, type:

```
sudo ./install.sh
```

### Install SensorKinect

* First type this command in Terminal to prevent errors when installing SensorKinect.

```
sudo ln -s /usr/local/bin/niReg /usr/bin/niReg
```

* Go to this Github repository and click Download ZIP.
* You can download here [https://github.com/avin2/SensorKinect](https://github.com/avin2/SensorKinect). **Or use this file in our repository: `/kinect/xxx`**
* Move the Zip to the Kinect folder and uncompress it
* Navigate to the SensorKinect093-Bin-MacOSX-v5.1.2.1.tar file inside the Bin folder and uncompress it.
* Open Terminal and navigate to the SensorKinect093-Bin-MacOSX folder
* Install by typing the following command:

```
sudo ./install.sh
```

* It will prompt you to enter your password
* If it works it will install the Primesense sensor

### Install NiTE

* Last thing to install. Download `NiTE-Bin-MacOSX-v1.5.2.21.tar.zip`. **Use this file in our repository: `/kinect/xxx`**.
* Add this file to your Kinect folder and uncompress it
* Go into Terminal and navigate to the NiTE folder
* Install NiTE by typing in the following command:

```
sudo ./install.sh
```

Once that is done, you’ve pretty much finished! Now try and run some examples!

* Plug in the Kinect
* Copy the sample XML files from NiTE/Data over to the Data folder in SensorKinect
* Open Terminal and navigate to `NiTE/Samples/Bin/x64-Release`
* Run the first Demo by typing in the following command:

```
./Sample-PointViewer
```

If everything is setup correctly then a new window should pop up and display a tracking demo!

(Note: You might want to restart and enable the SIP again if you want)
