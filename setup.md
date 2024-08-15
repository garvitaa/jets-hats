---
title: Setup
---


The current version of this tutorial has been tested in the [Purdue Analysis Facility](https://analysis-facility.physics.purdue.edu/en/latest/index.html) (AF). Please follow the next steps to set up all you need.

# Run exercises at Purdue AF

Please follow [these steps to create your account](https://analysis-facility.physics.purdue.edu/en/latest/doc-getting-started.html). In short, if you have a fnal/cern account follow the link to log in into the Purdue AF: [https://cms.geddes.rcac.purdue.edu/hub](https://cms.geddes.rcac.purdue.edu/hub). Choose between your CERN/FNAL/Purdue account and follow the instructions to log in.  

Once you logged in into the jupyterhub, it will ask you for the server options. Choose the **default options** and click on start. After a couple of minutes your session will be ready to start and you will see a jupyter notebook environment.

Now you need to clone the [jets-hats](https://github.com/FNALLPC/jets-hats) repository. For that you can go to the menu `Git > Clone a repository`. A small window will pop up and you can fill `Enter the URI of the remote Git repository` with the following url: [https://github.com/FNALLPC/jets-hats](https://github.com/FNALLPC/jets-hats). Click on `Clone` and you should be ready to go.



# Run exercises at the CMS-LPC

**If the instructions above do not work, you can follow this instructions.**


Open a terminal/console, connect to cmslpc-sl7 and prepare your working area:

~~~
kinit username@FNAL.GOV
ssh -L localhost:8888:localhost:8888 <YOUR USERNAME>@cmslpc-sl7.fnal.gov
~~~
{: .language-bash}

If you haven't done it yet, go to your `nobackup` area (`/uscms_data/d3/<YOUR USERNAME>/`) and create a folder for the CMSDAS exercises. Once you are there you can clone our repository:

~~~
git clone git@github.com:cms-jet/JMEDAS.git -b DASJan2024
cd JMEDAS/notebooks/DAS/
~~~
{: .language-bash}

> ## Remember
> Once you clone the repository, using the `DASJan2024` branch, the exercise notebooks are located
> in `JMEDAS/notebooks/DAS/`
{: .callout}

Activate your grid certificate:
~~~
voms-proxy-init -voms cms -valid 192:00
~~~
{: .language-bash}

The following commands one has to do it *everytime you log in into a new session*. They load the
environment and the packages needed for the exercises and open a jupyter notebook:
~~~
source /cvmfs/sft.cern.ch/lcg/views/LCG_104/x86_64-centos7-gcc11-opt/setup.sh
jupyter notebook --no-browser --port=8888 --ip 127.0.0.1
~~~
{: .language-bash}

If these two lines are running sucessfully, you should see something like this:
~~~
[I 11:09:47.019 NotebookApp] Serving notebooks from local directory: /uscms_data/d3/user/CMSDAS/ShortExJets2024/JMEDAS/notebooks/master
[I 11:09:47.019 NotebookApp] Jupyter Notebook 6.4.0 is running at:
[I 11:09:47.019 NotebookApp] http://127.0.0.1:8888/?token=7b7fed77cb9d6b3b18708b86bgfdsgsd069c6bc8ce0a9abad2
[I 11:09:47.019 NotebookApp]  or http://127.0.0.1:8888/?token=7b7fed77cb9d6b3b18708b86bgfdsgsd069c6bc8ce0a9abad2
[I 11:09:47.019 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
[C 11:09:47.028 NotebookApp]

    To access the notebook, open this file in a browser:
        file:///uscms/homes/u/user/.local/share/jupyter/runtime/nbserver-10677-open.html
    Or copy and paste one of these URLs:
        http://127.0.0.1:8888/?token=7b7fed77cb9d6b3b18708b86bgfdsgsd069c6bc8ce0a9abad2
     or http://127.0.0.1:8888/?token=7b7fed77cb9d6b3b18708b86bgfdsgsd069c6bc8ce0a9abad2

~~~
{: .output}

Copy and paste one of the last two urls in your favorite browser and now you can continue with the lesson 1 (Episode 1).


> ## If you are using PUTTY
> Go to ssh tab on the left then type in source port (ex. 8888) with destination (ex. localhost:8888) and then hit "add" to add this to the list of ports
> If 8888 is occupied, use another port (ex. anything above 8000) instead
{: .callout}




## Useful settings

If you like seeing your working directory in the commandline, you can do also this by adding a line to ~/.bashrc and activating it with the 'source' command:

~~~
echo "PS1='\W\$ '" >> ~/.bashrc
source ~/.bashrc
~~~
{: .language-bash}



{% include links.md %}
