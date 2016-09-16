![Devoxx4Kids](./app/views/logo.jpg)


# ![Devoxx4Kids](./app/views/jumping-sumo.jpg)  Sumo4scratch  ![Devoxx4Kids](./app/views/jumping-sumo-flipped.jpg)
*from Stefan Höhn*

[Tobias Schneider]: https://github.com/derTobsch
[Scratch-Offline-Editor]: https://scratch.mit.edu/scratch2download/
[Jumping Sumo Drone]: http://www.parrot.com/usa/products/jumping-sumo/
[Parrot]: http://www.parrot.com/
Proxy __Server__ Implementation __to bridge Jumping Sumo commands__ within the [Scratch-Offline-Editor] with the help of the [controllers.DroneController-Library] (by [Tobias Schneider]) via Wireless to the [Jumping Sumo Drone] from [Parrot] as well as the necessary __Scratch Extension__.

[controllers.DroneController-Library]: https://github.com/Devoxx4KidsDE/drone-controller
[activator]: https://www.lightbend.com/activator/download

## Instructions

### Build, distribute and run the Sumo4Scratch server

[latest release]: https://github.com/Devoxx4KidsDE/sumo4scratch/tree/master/release/sumo4scratch.zip

* __Download__: You can just download the [latest release] which is in the release folder of this repository.

* Unpack the zip file, goto \bin-directory and start "sumo4scratch"
* Note: If you get a permission denied on a Mac then make sure it has the right file permissions. A chmods 777 sumo4scratch will help then.
* This will run the server listening on port 9000

__To build the server__ the setup is pretty simple. All you need to have, is at least Java 8 and [activator] installed

* To build a standalone server you need to have [activator] installed on your machine (something that any scala developer will have anyway).
* Go to the homedirectory of your project and type activator (it should come up with [ Sumo4Scratch ] in the prompt.)
* Enter "dist" and return. It will then build a zip-file with all required dependencies. It will tell you at the end what the location is where the zip was saved.
* Now you can distribute that zip file to anyone. The system that you run it on should have at least Java 8 installed.

### Setup Scratch to Sumo4Scratch

*Language of the extension*: Two different extension files are provided for German and English.

[sumo4Scratch.s2e-german]:  https://github.com/Devoxx4KidsDE/sumo4scratch/tree/master/Scratch/de/sumo4Scratch_de.s2e
[sumo4Scratch.s2e-english]: https://github.com/Devoxx4KidsDE/sumo4scratch/tree/master/Scratch/en/sumo4Scratch_en.s2e

* Download the file [sumo4Scratch.s2e-german] or [sumo4Scratch.s2e-english] from github and save it at a convenient place as you need to open it from Scratch later on.
* You need to have the [Scratch-Offline-Editor] of Scratch running
* After you have started Scratch, open "File" while *holding SHIFT* at the same time. This reveals a secret menu entry "Import Experimental Extension". Now you can chose the file [sumo4Scratch.s2e-german] or [sumo4Scratch.s2e-english] which will be loaded by scratch.
* Then you can go to the "more block" section of script tab and you will recognize the Jumping Sumo section.
* Drop the blocks into the code and have fun.
* One more thing: of course you need to connect your wireless to the sumo first to be able to connect to it.

[localization-behaviour]: https://scratch.mit.edu/discuss/topic/191003/
*Note:* In the current Scratch version I am using (445.2), extensions do not really have a complete support for localizations. Scratch seems to save the extension configuration in your program. See more at this description where I explained that [localization-behaviour].

## Using Sumo for Scratch

The usage of the blocks is straight forward and rather obvious.

* use the *Connection* Block first, when a scratch program is started. With the block you can define to which drone you like to connect. If you have only one drone, just go for the default.
* There is also a *Sumo off* with which you can disconnect that can be used. Of course, after that you need use the *Connect* again
* Now you can
	* Move in any direction (even with providing __speed and time__)
	* Turn by providing the angle in degrees
	* Jump high and far
	* Show __video and take photos__ (new!)
	* Do some __tricks__


[sumo-programm_de.sb2]: https://github.com/Devoxx4KidsDE/sumo4scratch/tree/master/Scratch/de/sumo-programm.sb2
[sumo-programm_en.sb2]: https://github.com/Devoxx4KidsDE/sumo4scratch/tree/master/Scratch/en/sumo-programm.sb2

There is a __sample program__ for Scratch for __each__ language that you can find in the root directory of the project which is called [sumo-programm_de.sb2] or [sumo-programm_en.sb2] .

Also there is a __cool web page__ that allows to show the __video__ of the drone and to show __captured photos__ which can be accessed via http://localhost:9000/monitor.

![Video and Photo web page](./monitor.png)

This is how it looks like in Scratch:

![English Sample](./scratch-sample_en.jpg)

and here is the German version:

![German Sample](./scratch-sample_de.jpg)
