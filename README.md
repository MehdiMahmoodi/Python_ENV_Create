# Creating a virtual environment:
## Useful links:<br>
*[Link-1](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment)<br>
*[link-2](https://code.visualstudio.com/docs/python/environments#_global-virtual-and-conda-environments)<br>
*[link-3](https://pip.pypa.io/en/latest/user_guide/#requirements-files)<br>
*[link-4](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)<br>
*[link-5](https://conda.pydata.org/docs/using/envs.html)<br>
*[link-6-recomended](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands)<br>
## create a virtual environment, (conda create --help)
Use the terminal or an Anaconda Prompt for the following steps:<br>
1-  To create an environment:<br>
conda create --name myenv<br>
Note:Replace myenv with the environment name.<br>
2- When conda asks you to proceed, type y:<br>

    proceed ([y]/n)?<br>

    *This creates the myenv environment in /envs/. No packages will be installed in this environment.

    *To create an environment with a specific version of Python:

    conda create -n myenv python=3.6

    *To create an environment with a specific package:

    conda create -n myenv scipy

    OR:

    conda create -n myenv python
    conda install -n myenv scipy
    *To create an environment with a specific version of a package:

    conda create -n myenv scipy=0.15.0

    OR:

    conda create -n myenv python
    conda install -n myenv scipy=0.15.0

    *To create an environment with a specific version of Python and multiple packages:

    conda create -n myenv python=3.6 scipy=0.15.0 astroid babel

3-  To add the libraries to your created ENV, you can activate your library:<br>
    conda activate myenv<br>
    then start installing whatever libraries which you want:<br>
    conda install scipy=0.15.0<br>
    *To add a specific version of a package:
    conda install scipy=0.15.0
    

    

## Activating/Deactivating a virtual environment
*Before you can start installing or using packages in your virtual environment you’ll need to activate it. 
Activating a virtual environment will put the virtual environment-specific python and pip executables into your shell’s PATH.<br>
conda activate myenv<br><br>

for deactivating:<br><br>

conda deactivate myenv<br>
## Creating an environment from an environment.yml file

Use the terminal or an Anaconda Prompt for the following steps:

    Create the environment from the environment.yml file:

    conda env create -f environment.yml

    The first line of the yml file sets the new environment's name. For details see Creating an environment file manually.

    Activate the new environment: conda activate myenv

    Verify that the new environment was installed correctly:

    conda env list

    You can also use:
    
    conda info --envs.

## Specifying a location for an environment

You can control where a conda environment lives by providing a path to a target directory when creating the environment. You need to navigate to the subdirectory which you want to have the env (your project folder) through the terminal/anaconda prompt, then create the ENV. For example, the following command will create a new environment in a subdirectory of the current working directory called myenvs:

conda create --prefix ./myenvs jupyterlab=0.35 matplotlib=3.1 numpy=1.16

You then activate an environment created with a prefix using the same command used to activate environments created by name:

conda activate ./envs

    Conda can no longer find your environment with the --name flag. You’ll generally need to pass the --prefix flag along with the environment’s full path to find the environment.

    Specifying an install path when creating your conda environments makes it so that your command prompt is now prefixed with the active environment’s absolute path rather than the environment’s name.

After activating an environment using its prefix, your prompt will look similar to the following:

(/absolute/path/to/envs) $

This can result in long prefixes:

(/Users/USER_NAME/research/data-science/PROJECT_NAME/myenvs) $

To remove this long prefix in your shell prompt, modify the env_prompt setting in your .condarc file:

$ conda config --set env_prompt '({name})'

This will edit your .condarc file if you already have one or create a .condarc file if you do not.

Now your command prompt will display the active environment’s generic name, which is the name of the environment's root folder:

$ cd project-directory
$ conda activate ./env
(env) project-directory $

## Updating an environment

You may need to update your environment for a variety of reasons. For example, it may be the case that:

    one of your core dependencies just released a new version (dependency version number update).

    you need an additional package for data analysis (add a new dependency).

    you have found a better package and no longer need the older package (add new dependency and remove old dependency).

If any of these occur, all you need to do is update the contents of your environment.yml file accordingly and then run the following command:

$ conda env update --prefix ./env --file environment.yml  --prune

Note

The --prune option causes conda to remove any dependencies that are no longer required from the environment.


## Viewing a list of your environments

To see a list of all of your environments, in your terminal window or an Anaconda Prompt, run:

conda info --envs

OR

conda env list

A list similar to the following is displayed:

conda environments:
myenv                 /home/username/miniconda/envs/myenv
snowflakes            /home/username/miniconda/envs/snowflakes
bunnies               /home/username/miniconda/envs/bunnies

If this command is run by an administrator, a list of all environments belonging to all users will be displayed.
## Viewing a list of the packages in an environment

To see a list of all packages installed in a specific environment:

    If the environment is not activated, in your terminal window or an Anaconda Prompt, run:

    conda list -n myenv

    If the environment is activated, in your terminal window or an Anaconda Prompt, run:

    conda list

    To see if a specific package is installed in an environment, in your terminal window or an Anaconda Prompt, run:

    conda list -n myenv scipy

## Using pip in an environment

To use pip in your environment, in your terminal window or an Anaconda Prompt, run:

conda install -n myenv pip
conda activate myenv
pip <pip_subcommand>

Issues may arise when using pip and conda together. When combining conda and pip, it is best to use an isolated conda environment. Only after conda has been used to install as many packages as possible should pip be used to install any remaining software. If modifications are needed to the environment, it is best to create a new environment rather than running conda after pip. When appropriate, conda and pip requirements should be stored in text files.

We recommend that you:

Use pip only after conda

        Install as many requirements as possible with conda then use pip.

        Pip should be run with --upgrade-strategy only-if-needed (the default).

        Do not use pip with the --user argument, avoid all users installs.

Use conda environments for isolation

        Create a conda environment to isolate any changes pip makes.

        Environments take up little space thanks to hard links.

        Care should be taken to avoid running pip in the root environment.

Recreate the environment if changes are needed

        Once pip has been used, conda will be unaware of the changes.

        To install additional conda packages, it is best to recreate the environment.

Store conda and pip requirements in text files

        Package requirements can be passed to conda via the --file argument.

        Pip accepts a list of Python packages with -r or --requirements.

        Conda env will export or create environments based on a file with conda and pip requirements.








