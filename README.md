# Compiling a software documentation

## Requirement 

* Access to sootsplash
* A "Build: Passing" project from github
* Knowledge on how to compile the software

### Accessing sootsplash
To gain access to sootsplash input following command and enter password for your account:
~~~shell
ssh -i path/to/user_rsa <username>@sootsplash.csci2461.com
~~~

### Picking project on github

I wanted something that I can use so I picked [Motion-Project](https://github.com/Motion-Project/motion)
a program that monitors the video signal and detects if the picture has changed


### Compiling the project

From Linux book chapter 16:
steps to take

1. Unpack the source code archive
2. Configure the package
3. Run `make` to build the programs
4. Run make install or a distribution-specific install command to install the package

Unable to do anything on sootsplash I attempt to simulate the steps I would take 
to compile and install the project on my linux os:

Unsure what to do I download the repository with the download zip link
Created and folder call motion and moved the zip file into that folder
#### Unpacking 
After downloading the zip and moving it to a folder I extracted the zip file
now I had a motion-master folder and inside was a bunch of file and more folders
following the 

#### Configure the package

There does not seems to be a configure file anywhere in the motion-master folder 
so I just skipped this step

#### Running `make`

I ran the `make` command in the motion-master folder and this is what resulted:
~~~shell
make: *** No targets specified and no makefile found.  Stop.
~~~
Unsure of what this means I skipped this step too

#### Running `make install`

The linux book instructed that we do a test installation first with the command:
~~~shell
make -n install
~~~
This resulted with the following:
~~~shell
make: *** No rule to make target 'install'.  Stop.
~~~
Unsure of what to do I decided to move on to the `make install` command

running the command 'make install' resulted in this:
~~~shell
make: *** No rule to make target 'install'.  Stop.
~~~

Because non of the following command are working I did a `checkinstall make install`
This is suppose to help
Result: 
~~~shell
The program 'checkinstall' is currently not installed. You can install it by typing:
sudo apt install checkinstall
~~~
so I attempt to install the command
Result: 
~~~shell
E: Unable to locate package checkinstall
~~~

Unsure what to do about using the command line to install the program I skipped
running `make install` command and just used the GUI to install the program

under the motion-master folder there is a install file so I ran that file
Result: ** It was a text file ** and inside were the steps to install the program

Steps from the txt file:
Install basic build packages:
    `sudo apt-get install autoconf automake pkgconf libtool libjpeg8-dev build-essential libzip-dev`

Install FFMPEG packages
    `sudo apt-get install libavformat-dev libavcodec-dev libavutil-dev libswscale-dev libavdevice-dev`

Once required packages are installed, execute:
~~shell  
autoreconf -fiv
./configure
make
make install
~~~
The errors I got trying to install the basic build package:
~~~shell
E: Unable to locate package pkgconf
E: Unable to locate package libzip-dev
~~~
solution for the error I went on the Ubuntu [package website](https://packages.ubuntu.com/)
and searched up the package that were unable to be located even after a update

The search for the package didn't help so I just removed the two package from the command
and installed the reset of the package

Installing the FFMPEG packages:
Results: 
~~~shell
E: Unable to locate package libavformat-dev
E: Unable to locate package libavcodec-dev
E: Unable to locate package libavutil-dev
E: Unable to locate package libswscale-dev
E: Unable to locate package libavdevice-dev
~~~
Unsure what to do I skipped the FFMPEG

running the Execution command: 
Result from running the `./configure` command:

~~~shell
configure: error: Required ffmpeg packages 'libavutil-dev libavformat-dev libavcodec-dev libswscale-dev libavdevice-dev' were not found.  Please check motion_guide.html and install necessary dependencies or use the '--without-ffmpeg' configuration option.
~~~
skipping on to the next one, I am unsure what to do.

Result from running the `make` command:
~~~shell
make: *** No targets specified and no makefile found.  Stop.
~~~
assuming the `make install` will result in the same error I gave up.
 
### Problem I could not fix

I did not have admin right on soot splash and because of this I was unable to do anything on 
soot splash so I just install the program on my linux os instead.

### Thank You for your time
