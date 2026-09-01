# SCC and Conda Environment Setup

For many of your courses, you will be creating and utilizing Conda to create
portable and reproducible computational environments with specific packages
installed. You will gain experience with this across the semester, but we first
need to handle a few logistics of using Conda on the SCC. Technically, we will
be using miniconda - a stripped down version of Conda that only contains the
installer. You may find a copy of the directions here if you find them easier to
follow:
https://www.bu.edu/tech/support/research/software-and-programming/common-languages/python/python-software/miniconda-modules/#Conda%20Modules

In a terminal in your VS Code session, please type in the following command:

```
module load miniconda
```

The first time you enter this command, your terminal should be populated with
directions on how to set up miniconda. Please follow them and when asked for the
location of storage, provide the following path:

/projectnb/bioinfo-ms/students/

If you wish to manually confirm, by the end of this, the .condarc file in your
home directory (~/.condarc) should look something like below:

```bash
envs_dirs:
    - /projectnb/bioinfo-ms/students/<your_loginname>/.conda/envs
    - ~/.conda/envs
pkgs_dirs:
    - /projectnb/bioinfo-ms/students/<your_loginname>/.conda/pkgs
    - ~/.conda/pkgs
env_prompt: ({name})
```
Please make sure to replace <your_loginname> with your BU username.
