# Ubuntu-vm-set-up

A video going over all of this will be made available at the following link:

Make sure you source the Virtual machine from either Josh Wile or some other method of availability

The Folder containing all the files should be named UAV_Autonomy_20

This Virtual Machine has been created to contain all the currently necessary files and folders to run simulations and example codes using MAVSDK. Although it presently contains all the necessary files to do simpler beginner stuff feel free to modify and play around with the virtual machine as it won't affect other virtual machines and it can be easily replaced with a previously working version if any problems occur.

Once you have gotten a hold of the file make sure to copy it over inside a folder in the documents section of your file explorer called Virtual Machines. (Make sure you COPY not move as it will become important later)

After moving it here open up VMWare Workstation and instead of selecting a pre-existing VM or creating a new one select <b>Open a Virtual Machine</b> and go to the location you previously placed the UAV_Autonomy_20 Virtual Machine.

NOTE: if your computer does not have as much RAM and or cores in the CPU you may want to limit those in the settings similarly to how you may have before.

It may ask you if you moved or copied the virtual machine and if so select <b>I copied it</b>

After this wait a short while as it loads for the first time on your computer.

After finishing setting up you should end up in the Ubuntu homescreen. please make sure to ignore and or remove any requests to update the virtual machine or Ubuntu.

The first thing we can do here is open Qground control and make sure it is working. You can do this by double-clicking the Qgroundcontrol.AppImaghe file on the home screen. If it gives you a black screen with some lines of commands to enter into the terminal open a terminal using:

<pre>CTRL-ALT-T</pre>

This should open up a terminal window Where you can paste the following lines and press enter. This can be done by pressing CTRL-SHIFT-V
<pre>sudo usermod -a -G dialout $USER
sudo apt-get remove modemmanager</pre>

After doing this press Y to continue if needed and if not then just wait for it to finish. It is finished when it returns you back to an empty line that only has the green and blue text.

Then close Qground control and click on it again to open. It should now work as intended.

Qground control will mostly be used to monitor any real and or simulated drone.

Next to actually start using a simulated drone open a new terminal as we did before and type the following:
<pre>cd Desktop/PX4-Autopilot/</pre>

This command makes it so we change directories in the files and then use a command to run the SITL Gazebo simulation.

Choose one of the vehicles from this link: https://docs.px4.io/v1.12/en/simulation/gazebo.html#set_world_location\

Copy and paste on of the commands used there and before pasting it into the terminal make sure to add "sudo" in front of it for example:

<pre>sudo make px4_sitl gazebo_standard_vtol</pre>

This should open a gazebo window and show the vehicle you attempted to open. The vehicle should automatically connect to Qgroundcontrol and its data should be viewable there.

While this is all great we can also control the vehicle using MAVSDK scripts by opening a new terminal and typing the following:

<pre>cd Desktop/MAVSDK/examples
ls</pre>

By typing ls we can see a list of the files and folders in this section of the directory and can take a look at the various examples we can use. Because we want to test waypoint travel the best option might be fly_mission. Unfortunately, there can be problems using the VTOL Vehicle for this example so it be best to use another like the Typhoon H480.

<pre> cd fly_mission
  ls
</pre>

if we can see that there is no folder named "build" we must create it using:

<pre>mkdir build</pre>

then ls again to make sure it was made correctly and cd build to be placed inside the folder. you can ls again to see that the folder is currently empty as we just made it.

since the folder did not exist the other files needed to run the example did not exist either therefore type
<pre>cmake ..</pre>

then 

<pre>make</pre>

to make those files needed to run the example

to actually run the example type:

<pre>./fly_mission udp://:14540</pre>

if you are running another exaple you can replace the fly_mission part with  the name of the example you are doing and it should work.

the terminal will tell you messages about what is taking place and in gazebo, you should see your drone and or vehicle moving to the waypoints.

to actually see the code that is doing this example you must wait for the exxample to finish or kill the example by typing CTRL-c in the terminal you ran the example.

Then you must go back a directory by typing:

<pre>cd ..</pre>

and then typing

<pre>code .</pre>

and this will open Visual Studio Code in the file directory you are currently in.

Click on the .cpp file shown in the lefthand bar and the code is easily accessible to mess with.

if you want to change something edit the file in any way you want in VSCode then save the fle in the top left-hand corner and return to the terminal you were previously using.

cd back into the build folder and type "make" again in order to save and build the changes. then run the example again as before and see your changes take place.

This should be all for this intro to the virtual machine and its contents and if any help is needed or probles come up following this feel free to message me (Luis Rivera) in either the evtol discord or any other method you need.

for later : src/modules/simulation/simulator_mavlink/sitl_targets_gazebo.cmake
https://discuss.px4.io/t/create-custom-model-for-sitl/6700/4
