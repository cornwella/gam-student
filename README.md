# gam-student
Python script to create and run GAM batch files based on nightly student import data

## Prerequisites
- [GAM](https://github.com/jay0lee/GAM/wiki)
- [Python 2.7](https://www.python.org/downloads/)


### Setting up GAM
See [this guide](https://github.com/jay0lee/GAM/wiki#running-gam-for-the-first-time)!

### Creating the Task Scheduler job


## SIS Customization
Our student import script generates a file called `diff.csv` which includes only the students not present in AD that have been added to the SIS (MiStar in our case). This script reads the `diff.csv` file and generates a GAM batch file to reset their account password in Google.

Depending on your setup, you likely have to adjust which columns are being handled; our last two are password and username respectively.
You can edit this on line `34`.





