## Running the code

The code for this workshop is in Jupyter notebooks.
If you are not familiar with Jupyter, you can run a tutorial by [clicking here](https://jupyter.org/try).  
Then select "Try Classic Notebook".  It will open a notebook with instructions for getting started.

To run the workshop code, you have three options:

Option 1: Run the notebooks on Google Colab.

Option 2: Run the notebooks on Binder.

Option 3: Install Jupyter on your computer and run the notebooks locally.

The following sections explain these options in detail.

### Option 1: Run on Colab

You can run the workshop notebooks by clicking on the links below.  
If you want to modify and save any of them, you can use Colab to save a copy in a Google Drive or your own GitHub repo, 
or on your computer.

* COMING SOON

### Option 2: Run on Binder

To run the code for this book on Binder, press this button:

[![Binder](http://mybinder.org/badge.svg)](http://mybinder.org/repo/AllenDowney/2020-11-16-astrodc-online)

It takes a minute or so to start up, but then you should see the Jupyter home page with a list of files.  
[TODO: Add instructions for finding the notebooks], then click on one of the notebooks (with the .ipynb extension).


### Option 3: Install Python+Jupyter

For this workshop you need Python, Jupyter, and some additional libraries.
If you don't already have Jupyter, we recommend installing Anaconda, which is a Python distribution that 
contains everything you need to run the ThinkDSP code.  It is easy to install on Windows, Mac, and Linux, 
and because it does a user-level install, it will not interfere with other Python installations.

[Information about installing Anaconda is here](https://www.anaconda.com/distribution/).

If you have the choice of Python 2 or 3, choose Python 3.

There are two ways to get the packages you need for ThinkDSP.  You can install them by hand or create a Conda environment.

To install them by hand run

```
conda install jupyter numpy scipy pandas matplotlib seaborn
conda install -c conda-forge 
``` 

Or, to create a conda environment, run

```
wget 
conda env create -f environment.yml
conda activate ThinkDSP
```

To start Jupyter, run:

```
jupyter notebook
```

Jupyter should launch your default browser or open a tab in an existing browser window.
If not, the Jupyter server should print a URL you can use.  For example, when I launch Jupyter, I get

```
~/ThinkComplexity2$ jupyter notebook
[I 10:03:20.115 NotebookApp] Serving notebooks from local directory: /home/downey/ThinkDSP
[I 10:03:20.115 NotebookApp] 0 active kernels
[I 10:03:20.115 NotebookApp] The Jupyter Notebook is running at: http://localhost:8888/
[I 10:03:20.115 NotebookApp] Use Control-C to stop this server and shut down all kernels (twice to skip confirmation).
```

In this case, the URL is [http://localhost:8888](http://localhost:8888).  
When you start your server, you might get a different URL.
Whatever it is, if you paste it into a browser, you should should see a home page with a list of directories.

Click on `code` to open the folder with the notebooks, then click on one of the notebooks (with the .ipynb extension).

Select the cell with the import statements and press "Shift-Enter" to run the code in the cell.
If it works and you get no error messages, **you are all set**.  

If you get error messages about missing packages, you can install the packages you need using your
package manager, or install Anaconda.

If you run into problems with these instructions, let us know and we will make corrections.  Good luck!


