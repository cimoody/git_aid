## Windows Subsystem for Linux Setup
#### Courtesy of Sina Rafati 

1. First, install the windows terminal
https://github.com/microsoft/terminal/releases/tag/v1.13.10983.0

2. Install Ubuntu from the Microsoft store

3. Link windows to your Linux (do this in your Linux terminal)
`-s  /mnt/c/Users/<your username on windows>  ~/win-home` 
*This didn't work for me, but I set my directory in the settings to open to `/mnt/c/Users/<your username on windows>`
now you have a folder in your Linux called win-home that is linked to your Windows file system

4. From your Linux terminal download anaconda
https://repo.anaconda.com/archive/Anaconda3-2021.11-Linux-x86_64.sh
5. From your Linux terminal install anaconda
          `bash Anaconda3-2021.11-Linux-x86_64.sh`
6. Set the source for your conda
	   `source ~/.bashrc`

7. upgrade and install git
	`sudo apt update`
	`sudo apt upgrade`
	`sudo apt install git-all`

8. make your conda environment and install packages
	`conda create --name py39_12 python=3.9.12 –yes`
	`conda activate py39_12`
	`pip install --upgrade pip`
	`sudo apt install tree`
	`pip install -U pytest transformers praw torch numpy pandas ipython`

9. make sure all packages are installed (note that you will see more packages than what you installed as there are some dependencies)
	`pip list`
	
at this point your environment is ready and you don’t need to change anything and plz don’t! :P

Your user file system on windows is linked with your Linux at step 3 so from your Linux terminal you have access to all folders in your windows account (such as Downloads, Documents, Desktop etc. ) (edited) 
