# gam-student
Python script to create and run GAM batch files based on nightly student import data

## Prerequisites
- [GAM](https://github.com/jay0lee/GAM/wiki)
- [Python 2.7](https://www.python.org/downloads/)

### Setting up GAM
See [this guide](https://github.com/jay0lee/GAM/wiki#running-gam-for-the-first-time)!

### SIS Customization
Our Powershell student import script generates a file called `diff.csv`, which includes only the students not present in AD / Google that have been added to the SIS (MiStar in our case). This script reads the csv and generates a GAM batch file to reset their account password in Google.

Depending on the setup, one likely has to adjust which columns are being handled; our last two are password and username respectively.
This can be edited on line `34`.

Set your student's Google domain in the `student_domain` variable.

### Creating the Task Scheduler job
Create your task at the desired time and interval (we run it M-F at 10PM, since our SIS sync runs at 8, giving it enough of a buffer. Point it at the Python executable, and give it the script's absolute path as parameter:

![configuring Task Scheduler for gam-student](https://i.imgur.com/Z41dL2W.jpg)







