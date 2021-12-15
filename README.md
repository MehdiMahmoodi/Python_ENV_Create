# Linux:Creating a virtual environment:
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

    You can also use conda info --envs.

##Specifying a location for an environment


You can control where a conda environment lives by providing a path to a target directory when creating the environment. For example, the following command will create a new environment in a subdirectory of the current working directory called envs:

conda create --prefix ./envs jupyterlab=0.35 matplotlib=3.1 numpy=1.16

You then activate an environment created with a prefix using the same command used to activate environments created by name:

conda activate ./envs

Specifying a path to a subdirectory of your project directory when creating an environment has the following benefits:

        It makes it easy to tell if your project uses an isolated environment by including the environment as a subdirectory.

        It makes your project more self-contained as everything, including the required software, is contained in a single project directory.

An additional benefit of creating your project’s environment inside a subdirectory is that you can then use the same name for all your environments. If you keep all of your environments in your envs folder, you’ll have to give each environment a different name.

There are a few things to be aware of when placing conda environments outside of the default envs folder.

    Conda can no longer find your environment with the --name flag. You’ll generally need to pass the --prefix flag along with the environment’s full path to find the environment.

    Specifying an install path when creating your conda environments makes it so that your command prompt is now prefixed with the active environment’s absolute path rather than the environment’s name.

After activating an environment using its prefix, your prompt will look similar to the following:

(/absolute/path/to/envs) $

This can result in long prefixes:

(/Users/USER_NAME/research/data-science/PROJECT_NAME/envs) $

To remove this long prefix in your shell prompt, modify the env_prompt setting in your .condarc file:

$ conda config --set env_prompt '({name})'

This will edit your .condarc file if you already have one or create a .condarc file if you do not.

Now your command prompt will display the active environment’s generic name, which is the name of the environment's root folder:

$ cd project-directory
$ conda activate ./env
(env) project-directory $

Updating an environment

You may need to update your environment for a variety of reasons. For example, it may be the case that:

    one of your core dependencies just released a new version (dependency version number update).

    you need an additional package for data analysis (add a new dependency).

    you have found a better package and no longer need the older package (add new dependency and remove old dependency).

If any of these occur, all you need to do is update the contents of your environment.yml file accordingly and then run the following command:

$ conda env update --prefix ./env --file environment.yml  --prune

Note

The --prune option causes conda to remove any dependencies that are no longer required from the environment.





