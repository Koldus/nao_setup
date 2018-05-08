# Setting up Nao Dev Environment (Ubuntu 16.04)

Here is a series of steps I had to take to setup the environment 

## 1. Dependencies

In order to successfully build this environment, you will need **Python 2.7**. Nao SDK is not compatible with Python 3. I first tried running it as an anaconda environment, ended up retracing my steps and starting with a clean Python install.

You also need to create an account on the [Aldebaran developer community site](https://community.ald.softbankrobotics.com/). It's free. 

## 2. Download Resources

Once you have an account and you are logged in, proceed to the [Resouces/Software/Nao](https://community.ald.softbankrobotics.com/en/resources/software/language/en-gb/robot/nao-2) and download the following files:

- Choregraphe 2.1.4 Linux 64 Binaries
- Python 2.7 SDK 2.1.4 Linux 64
- C++ SDK 2.1.4 Linux 64

Feel free to browse the page for addition resources you may need.

## 3. Install Choreographe

Unpack the downloaded file.

```
tar -xvzf choregraphe-suite-2.1.4.13-linux64.tar.gz
```

Rename the folder for an easier access. Feel free to move it to a different folder in the process.

```
mv ./choregraphe-suite-2.1.4.13-linux64 ~/nao/software/choreographe
```

Last step is to test the installation and activate the product.

```
cd ~/nao/software/choreographe
./choreographe
```

You can retrieve the license during the purchase of your Nao Robot or it can also be found [here](https://hayuulr.wordpress.com/2017/10/24/installation-on-ubuntu-16-04-2-x64-at-desktop-machine/).

More information can be found [here](http://doc.aldebaran.com/2-5/software/choregraphe/installing.html#desktop-installation).

## 4. Install Python 2.7 SDK / C++ SDK

```
tar -xvzf ./naoqi-sdk-2.1.4.13-linux64.tar.gz
mv ./naoqi-sdk-2.1.4.13-linux64 ~/nao/software/naoqi-sdk-2.1.4.13-linux64
tar -xvzf ./pynaoqi-python2.7-2.1.4.13-linux64.tar.gz
mv ./pynaoqi-python2.7-2.1.4.13-linux64 ~/nao/software/pynaoqi-python2.7-2.1.4.13-linux64
cd ~/nao/software/
ls
```

And make sure all three parts (Choreographe and both SDKs) are present.

```
echo 'export PYTHONPATH=${PYTHONPATH}:/home/user_name/nao/software/pynaoqi-python2.7-2.1.4.13-linux64' >> ~/.bashrc
echo 'export LD_LIBRARY_PATH="/home/user_name/nao/software/naoqi-sdk-2.1.4.13-linux64:$LD_LIBRARY_PATH"' >> ~/.bashrc
sudo ldconfig
sudo cp -a /home/user_name/nao/software/naoqi-sdk-2.1.4.13-linux64/lib/libboost_*.so.* /home/user_name/nao/software/naoqi-sdk-2.1.4.13-linux64/
source ~/.bashrc
```

To make sure everything is in order, run python from the terminal and import the SDK.

```
python
>>> import naoqi
```

If you do not see any errors, the installation was successful.

## 5. Install Numpy


## 6. Install OpenCV


## 7. Install ROS (Kinetic)


## 8. Install Nao Connector for ROS


## Anything else?


To make this happen, I've followed a series of tutorials. The credit goes to them. [Here](https://hayuulr.wordpress.com/2017/10/24/installation-on-ubuntu-16-04-2-x64-at-desktop-machine/), [here]() and [here](). I decided to document all steps since I couldn't find a complete pictures with all the materials in one place.