# SCC On Demand and VS Code

We will be largely interacting with the SCC using the OnDemand web application.
This platform has many built-in functionalities for using the cluster more
easily with a GUI.

Please launch OnDemand by going to this link: https://scc-ondemand.bu.edu/. You
will see a number of tabs which you will get more familiar with across your
courses. The most important for today is the Interactive Apps Tab (Top middle).

Please click on it and open the dropdown and select VS Code Server (near the
bottom of the list). This is a GUI that will launch an interactive VS Code
session on a compute node on the SCC. This will let you work and develop your
code on the cluster and submit jobs to it for the many computationally intensive
analyses you will be performing. You'll see a number of settings you can adjust.
The most important for today to point out will be listed below:

**Additional modules to load (space separated, optional)**
- Please use the Select Modules button and add `miniconda`

**Number of hours**
- This value cannot be changed once started and your job and unsaved work will
be lost if the job expires

**Number of cores**
- You can safely set this at `1` for the majority of your working sessions
unless specified otherwise

**Project**
- This will likely be set automatically but change it to the class project you
are working on at that moment (e.g. bf528, bf550, etc.)

Once done, if you click launch, you will open a VS Code session where you will
be doing the majority of your work. VS Code is an integrated development
environment that will enable you to develop and run your code as you write it.

Please ensure you are comfortable with the following in VS Code:

- [ ] Open a terminal
- [ ] Create new files and directories
- [ ] Open a new directory as the working directory

Install the following VS Code plugins:

- [ ] R extension for Visual Studio Code (REditorSupport)
- [ ] Jupyter (ms-toolsai)
- [ ] Nextflow (nextflow)
- [ ] Python (ms-python)
- [ ] Snakemake Language (snakemake)

You can find the extensions on the left tab if you click on the icon that
resembles several blocks.
