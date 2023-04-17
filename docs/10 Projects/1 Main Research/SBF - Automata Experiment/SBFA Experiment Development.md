---
type: [dash, devproject]
status: active
priority: p1
project: SBF-automata
creationtag: 2023-03-03 13:53
infotags:
people:
date: [dev, development, documentation, py, python]
---
Were you looking for [[SBFA Development Log]]?

# Statement
I need a dashboard to keep track of how to do the development.
This is specific to the development stuff surrounding [[SBF - Automata Experiment]]

See also: [[Learning Python|python project]]


# Info
## additional directions
To 



## Clearer directions

Via bash connect to `ssh labbox
- I have already set up the ssh keys and added a alias `labbox`

See screens `screen -ls`
There should be one named `Jlab`
Connect to it with `screen -r Jlab`
If not, create it
you should be in the main home folder by default
Navigate to the `pyvenv` folder
~~Then into the virtual environment you have created~~ 
You do not navigate into the directory for the venv, but instead create/start it the pyvenv folder, in fact you can even activate it from the home directory
In this case `sbfa` but this can be anything
```
source pyvenv/sbfa/bin/activate
```

After which start jupyerlab, preferably from the home directory (gives directory access starting at that point)
```
jupyter lab --no-browser --port 8887
```

Then in local bash screen, port forward the instance to your client
```
ssh -N -L localhost:8887:localhost:8887 labbox
```

You can then open the lab in your browser, or in VScode









Lol you set an overlord pass for the jupyterlab




## Accessing Lab Sandbox Server #SBF-automata
Move into an lab internal wikidoc.
Actually make a project as well.
I guess this may go under the general development project.

From Sidney: 
> I just created a user account in one of our machines in the AI lab server. Its operating system is Ubuntu.
> 
> Here is your information to access the server:
> 
> IP address: 128.39.89.130 
> 
> Username: michaelt
> 
> Password: Mt.SNN.RL.Project.2327
> 
> You need to be in the OsloMet network, then you should use EduVPN. I believe only ansatt-vpn.oslomet.no is working. You can use your student credentials to login.
> 
> To access the server remotely, you are going to do it through SSH. If you are using Mac or Linux, you can do it running this command:
> 
> $ ssh [username]@[ip_address]
> 
> or
> 
> $ ssh [ip_address]
> 
> If you are using Windows, you can do it using PuTTY (You can find it in our “Software Center” or [https://www.putty.org/](https://eur02.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.putty.org%2F&data=05%7C01%7Cmichaelt%40oslomet.no%7C649362418f68480f39c308db0dff859d%7Cfec81f12628645508911f446fcdafa1f%7C0%7C0%7C638119163325992945%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=qWjWKYv7xgTYKFhvYLdsTffB%2B730z5msm1aIKgVonNY%3D&reserved=0 "Original URL: https://www.putty.org/. Click or tap if you trust this link.")) or MobaXterm ([https://mobaxterm.mobatek.net/](https://eur02.safelinks.protection.outlook.com/?url=https%3A%2F%2Fmobaxterm.mobatek.net%2F&data=05%7C01%7Cmichaelt%40oslomet.no%7C649362418f68480f39c308db0dff859d%7Cfec81f12628645508911f446fcdafa1f%7C0%7C0%7C638119163325992945%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=l1LAow6evR8U7GcxNoj%2FaDnZ4mXZLRonDqehZh13ceA%3D&reserved=0 "Original URL: https://mobaxterm.mobatek.net/. Click or tap if you trust this link.")).
> 
> Related to transferring files, you can do it through SCP. Mac has a command in their terminal for that. It would be something like:
> 
> $ scp [path/to/copy] [username]@[ip_address]:[path/to/paste]
> 
> or
> 
> $ scp [username]@[ip_address]:[path/to/copy] [path/to/paste]
> 
> You can transfer files in Windows through MobaXterm and other one called WinSCP (You can find it in our “Software Center” or [https://winscp.net/eng/download.php](https://eur02.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwinscp.net%2Feng%2Fdownload.php&data=05%7C01%7Cmichaelt%40oslomet.no%7C649362418f68480f39c308db0dff859d%7Cfec81f12628645508911f446fcdafa1f%7C0%7C0%7C638119163326149212%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=HGScbZHnCUbUNUGpWCtQR7JXfI%2BP9iXbcgcNrU8D%2Fvs%3D&reserved=0 "Original URL: https://winscp.net/eng/download.php. Click or tap if you trust this link.")).
> 
> There is no routine to use the server. If it is available, you can use it. You can check if anyone is using it with:
> 
> $ htop
> 
> To run jobs on background, you can use the command “screen”.
> 
> The main screen arguments I use:
> 
> $ screen -R           Reattach screen, or create a new one if there is none.
> 
> $ screen --list      List of all screens
> 
> $ screen --help   Command manual
> 
> When you are in the screen, your commands are:
> 
> Ctrl + ‘a’, then ‘d’: It deattaches current screen
> 
> Ctrl + ‘a’, then ‘k’: It kills current screen
> 
> You can read more about screen on: [https://linuxize.com/post/how-to-use-linux-screen/](https://eur02.safelinks.protection.outlook.com/?url=https%3A%2F%2Flinuxize.com%2Fpost%2Fhow-to-use-linux-screen%2F&data=05%7C01%7Cmichaelt%40oslomet.no%7C649362418f68480f39c308db0dff859d%7Cfec81f12628645508911f446fcdafa1f%7C0%7C0%7C638119163326149212%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C3000%7C%7C%7C&sdata=Ds9n2viMXvAIRSns6RlYUNXELUKkee4hsNGBPu%2FLkBw%3D&reserved=0 "Original URL: https://linuxize.com/post/how-to-use-linux-screen/. Click or tap if you trust this link.")
> 
> You do not need to install Anaconda. Python alone can do everything.
> 
> Python 3 is installed. You just need to use in the command line:
> 
> $ python3
> 
> Since we do not use Anaconda, you can install Python packages with:
> 
> $ pip3 install [package_name]
> 
> If you want to see the installed packages, you can use:
> 
> $ pip3 list
> 
> If you would like to have Python virtual environments, you can create one like this:
> 
> $ python3 -m venv [environment_name]
> 
> This command will create a folder with the name of the virtual environment. You can activate the environment like this:
> 
> $ source  [environment_name]/bin/activate
> 
> Then you can install packages for this specific environment. If you want to deactivate it, you just use:
> 
> $ deactivate
> 
> If you have any questions, please let me know.

## Testing out python virtual environments on remote server - jupyterlab
I want to set up jupyter lab or some sort of remote tool 

### Micro #log 
- Installing jupyter lab on remote
- `pip3 install jupyterlab`
- Going to remote into it via ssh
- `ssh -L 8080:localhost:8080
	- https://stackoverflow.com/questions/69244218/how-to-run-a-jupyter-notebook-through-a-remote-server-on-local-machine
	- https://docs.anaconda.com/anaconda/user-guide/tasks/remote-jupyter-notebook/
- Actually, run it first (on the remote)
	- ```jupyter lab --no-browser --port 8887```
	- 
	- `jupyterlab` (no space) does not work despite that being directly taken from their website
- Then ssh (on the local machine):
	- `ssh -N -L localhost:8887:localhost:8887 labbox`

So the virtual environment must be “activated” before anything can be done with it
```
source venv/bin/activate
```

- I think this means it is temporarily added to the `PATH`
- https://towardsdatascience.com/virtual-environments-104c62d48c54
- https://realpython.com/python-virtual-environments-a-primer/
- https://docs.python.org/3/library/venv.html

**OK it works!**

Uploaded the py notebooks from drive

Had to install all packages from scratch
