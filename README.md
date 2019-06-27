# The 3d World

![](videos/mapillary.gif)

## About this Module
This module is about the mathematics and code that makes 3d computer vision work. This portion of the field is enormous, with a long history, and huge body of literature. We'll hit key areas, and put them together in a fun challenge where you get to build your own 3d model. 

## Lectures
| Order |   Notebook/Slides  | Required Viewing/Reading |  Notes |
| ----- | ------------------ | ----------------------- | ------------------ |
| 1 | [The Pinhole Camera](https://github.com/unccv/the_3d_world/blob/master/notebooks/The%20Pinhole%20Camera.ipynb) | [Prince Computer Vision 14.1-14.6](http://www.computervisionmodels.com/) |  |
| 2 | [Interest Point Detection and Description](https://github.com/unccv/the_3d_world/blob/master/notebooks/Interest%20Detection%20and%20Description.ipynb) | [Szeliski Section 4.1](http://szeliski.org/Book/) | |
| 3 | [Camera Calibration and Image Undistortion](https://github.com/unccv/the_3d_world/blob/master/notebooks/Camera%20Calibration%20and%20Image%20Undistortion.ipynb) |  | |
| 4 | [Transformations](https://github.com/unccv/the_3d_world/blob/master/notebooks/Transformations.ipynb) | [Prince Computer Vision 15](http://www.computervisionmodels.com/) | |
| 5 | [RANSAC](https://github.com/unccv/the_3d_world/blob/master/notebooks/RANSAC.ipynb) | [Prince Computer Vision 15.6](http://www.computervisionmodels.com/) | |

## Setup 

The Python 3 [Anaconda Distribution](https://www.anaconda.com/download) is the easiest way to get going with the notebooks and code presented here. 

(Optional) You may want to create a virtual environment for this repository: 

~~~
conda create -n cv python=3 
source activate cv
~~~

You'll need to install the jupyter notebook to run the notebooks:

~~~
conda install jupyter

# You may also want to install nb_conda (Enables some nice things like change virtual environments within the notebook)
conda install nb_conda
~~~

This repository requires the installation of a few extra packages, you can install them all at once with:
~~~
pip install -r requirements.txt
~~~

(Optional) [jupyterthemes](https://github.com/dunovank/jupyter-themes) can be nice when presenting notebooks, as it offers some cleaner visual themes than the stock notebook, and makes it easy to adjust the default font size for code, markdown, etc. You can install with pip: 

~~~
pip install jupyterthemes
~~~

Recommend jupyter them for **presenting** these notebook (type into terminal before launching notebook):
~~~
jt -t grade3 -cellw=90% -fs=20 -tfs=20 -ofs=20 -dfs=20
~~~

Recommend jupyter them for **viewing** these notebook (type into terminal before launching notebook):
~~~
jt -t grade3 -cellw=90% -fs=14 -tfs=14 -ofs=14 -dfs=14
~~~