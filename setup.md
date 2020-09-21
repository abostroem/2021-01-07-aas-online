## Installation

For this workshop, we encourage you to work in a Jupyter notebook.
If you are not familiar with Jupyter, you can run a tutorial by [clicking here](https://jupyter.org/try).

Then select "Try Classic Notebook".  It will open a notebook with instructions for getting started.

You will need to install Python, Jupyter, and some additional libraries.
If you don't already have Jupyter, we recommend installing Anaconda, which is a Python distribution that 
contains everything you need to run the ThinkDSP code.  It is easy to install on Windows, Mac, and Linux, 
and because it does a user-level install, it will not interfere with other Python installations.

[Information about installing Anaconda is here](https://www.anaconda.com/distribution/).

If you have the choice of Python 2 or 3, choose Python 3.

There are two ways to get the libraries you need:

* You can install them in an existing conda environment.

* You can create a new conda environment.

Installing libraries in an existing environment is simpler, but if you use the same environment for many projects, it will get big, complicated, and prone to package conflicts.


### Install libraries in an existing conda environment

Most of the libraries we need can be installed using conda.

```
conda install jupyter numpy scipy pandas matplotlib seaborn libopenblas
conda install -c conda-forge astropy astroquery astro-gala
```

In addition, there's one library we can't install with conda, so we have to use pip:

```
pip install pyia
```

### Create a new conda environment

To create and activate a new conda environment, run:

```
wget https://raw.githubusercontent.com/AllenDowney/2020-11-16-astrodc-online/gh-pages/environment.yml
```

To download an environment file that lists the libraries you need, and then:

```
conda env create -f environment.yml
conda activate astronomy-python
```


### Run Jupyter

Before you launch Jupyter, download this notebook, which contains code to test your environment:

```
wget https://github.com/AllenDowney/2020-11-16-astrodc-online/raw/gh-pages/test_setup.ipynb
```

To start Jupyter, run:

```
jupyter notebook
```

Jupyter should launch your default browser or open a tab in an existing browser window.
If not, the Jupyter server should print a URL you can use.  For example, when I launch Jupyter, I get

```
$ jupyter notebook
[I 10:03:20.115 NotebookApp] Serving notebooks from local directory: /home/username/astronomy-python
[I 10:03:20.115 NotebookApp] 0 active kernels
[I 10:03:20.115 NotebookApp] The Jupyter Notebook is running at: http://localhost:8888/
[I 10:03:20.115 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
```

In this case, the URL is [http://localhost:8888](http://localhost:8888).  
When you start your server, you might get a different URL.
Whatever it is, if you paste it into a browser, you should should see a home page with a list of directories.

Now open the notebook you downloaded and run the cells that contain import statements.
If they work and you get no error messages, **you are all set**.

If you get error messages about missing packages, you can install the packages you need using conda or pip.

If you run into problems with these instructions, let us know and we will make corrections.  Good luck!


