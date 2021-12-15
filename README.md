# Linux:Creating a virtual environment:
## Useful links:<br>
*[Link-1](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#creating-a-virtual-environment)
*[link-2](https://code.visualstudio.com/docs/python/environments#_global-virtual-and-conda-environments)<br>
*[link-3](https://pip.pypa.io/en/latest/user_guide/#requirements-files)<br>
*[link-4](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
*[link-5](https://conda.pydata.org/docs/using/envs.html)
*[link-6-recomended](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html#creating-an-environment-with-commands)
## create a virtual environment, 
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

    conda create -n myenv scipy<br>

    OR:<br>

    conda create -n myenv python
    conda install -n myenv scipy

    *To create an environment with a specific version of a package:<br>

    conda create -n myenv scipy=0.15.0<br>

    OR:<br>

    conda create -n myenv python<br>
    conda install -n myenv scipy=0.15.0<br>

    *To create an environment with a specific version of Python and multiple packages:<br>

    conda create -n myenv python=3.6 scipy=0.15.0 astroid babel<br>


## Activating a virtual environment
*Before you can start installing or using packages in your virtual environment you’ll need to activate it. 
Activating a virtual environment will put the virtual environment-specific python and pip executables into your shell’s PATH.<br>
source newenv/bin/activate<br>
You can confirm you’re in the virtual environment by checking the location of your Python interpreter:<br>
which python<br>
It should be in the env directory:<br>
.../env/bin/python<br>
As long as your virtual environment is activated pip will install packages into that specific environment and you’ll be able to import and use packages in your Python application.
## Leaving the virtual environment<br>

If you want to switch projects or otherwise leave your virtual environment, simply run:<br>

deactivate<br>

If you want to re-enter the virtual environment just follow the same instructions above about activating a virtual environment. There’s no need to re-create the virtual environment.
##Installing packages

*Now that you’re in your virtual environment you can install packages. Let’s install the Requests library from the Python Package Index (PyPI):<br>
python3 -m pip install requests<br>
## Installing specific versions

pip allows you to specify which version of a package to install using version specifiers. For example, to install a specific version of requests:<br>
python3 -m pip install requests==2.18.4<br>
To install the latest 2.x release of requests:<br>
python3 -m pip install requests>=2.0.0,<3.0.0<br>
To install pre-release versions of packages, use the --pre flag:<br>
python3 -m pip install --pre requests<br>
If you have a local copy of a Distribution Package’s archive (a zip, wheel, or tar file) you can install it directly with pip:<br>
python3 -m pip install requests-2.18.4.tar.gz<br>
## Upgrading packages

*pip can upgrade packages in-place using the --upgrade flag. For example, to install the latest version of requests and all of its dependencies:<br>
python3 -m pip install --upgrade requests<br>
## Using requirements files
Instead of installing packages individually, pip allows you to declare all dependencies in a Requirements File. For example you could create a requirements.txt file containing:<br>“Requirements files” are files containing a list of items to be installed using pip install like so:<br>


requests==2.18.4<br>
google-auth==1.1.0<br>




