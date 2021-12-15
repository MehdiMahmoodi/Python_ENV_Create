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






