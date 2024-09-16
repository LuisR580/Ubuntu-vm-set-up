# Ubuntu-vm-set-up

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















