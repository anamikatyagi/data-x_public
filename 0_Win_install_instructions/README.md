
# Data-X: Windows 10 Installation (March 8 2017)

**Complete guide of how to setup your Python / Anaconda installation on Windows 10 so that all notebooks can be run up to lecture 8.**

## Download Anaconda with Python 2.7:
* https://www.continuum.io/downloads#windows


### **Create two virtual environments** (one for Python 2.7 and one for Python 3.5):

**In the bash prompt run:**

* ``conda create -n py35 python=3.5 anaconda``
* ``conda create -n py27 python=2.7 anaconda``

To work with either Python 2.7 or Python 3.5. Every time you open the command prompt you have to run:

* ``activate py27`` (to run Python 2 virtual environment)

* ``activate py35`` (to run Python 3 virtual environment)

**Note1:** In order to install packages to a specific virtual environment it has to be activated.

**Note2:** To return to "root" user, i.e. no virtual environment, run: ``deactivate``


**Note3:** Root user means that you are not running a virtual environment. This is the case every time you open the command prompt, or when you run "deactivate"
when a virtual environment is sourced.


## Install packages

Anaconda comes with many packages when it is installed. However to install new packages run

* ``conda install pkg-name`` (replace "pkg-name" with the name of the missing package)

**Note1:** If a package does not exist run ``conda install pip``, then ``pip install pkg-name``

**Note2:** If neither conda install nor pip works for package installation, try finding your package on by searching on the Anaconda cloud (see column to the far right that the package is designed for your platform, i.e. win-64 most likely). [https://anaconda.org/search?q=opencv](https://anaconda.org/search?q=opencv)


## Install OpenCV:

**Python 2.7**

In both the virtual environment and for the root user w/o virtual environment run:

* ``conda install -c menpo opencv``

**Python 3.5 (Note: not ported to 3.6 yet)**

* conda install -c menpo opencv3

**Troubleshoot with this link (Look for Windows installation further down)**: [http://stackoverflow.com/questions/23119413/how-to-install-python-opencv-through-conda](http://stackoverflow.com/questions/23119413/how-to-install-python-opencv-through-conda)


## Install Theano 
**Note:** These packages have to be installed in conda root user, as well as the virtual environments - works for both Python 2.7 and Python 3.5, but have to be installed in all three separately, i.e. *root, py27* and *py35*.

1. Download and install: [http://tdm-gcc.tdragon.net/](http://tdm-gcc.tdragon.net/)

2. Run ``conda install mingw libpython``

3. (Optional) The lines below requires Git to be installed. Download it here: [https://git-scm.com/download/win](https://git-scm.com/download/win) (use standard settings)

4. ``pip install --upgrade --no-deps git+git://github.com/Theano/Theano.git``

5. ``pip install git+git://github.com/fchollet/keras.git``


**Troubleshooting, look here:**

* [http://stackoverflow.com/questions/34097988/how-do-i-install-keras-and-theano-in-anaconda-python-on-windows](http://stackoverflow.com/questions/34097988/how-do-i-install-keras-and-theano-in-anaconda-python-on-windows)
* [http://deeplearning.net/software/theano/install_windows.html](http://deeplearning.net/software/theano/install_windows.html)

### Set Keras to work with Theano as the back end, in Python run: 

	from keras import backend as K
	K.set_image_dim_ordering('th')







## Install Tensorflow on Windows

**Note:** Right now TensorFlow only works with Python 3.5 on Widnows. Therefore, run ``activate py35`` before running the commands below. And always work in the *py35*  virtual environment when you're gonna use Tensorflow on Windows.

1. ``conda install pip``

2. ``pip install tensorflow``


#### Set Keras to use Tensorflow as a backend, in Python run:

	from keras import backend as K
	K.set_image_dim_ordering('tf')
	
	
## Optional troubleshooting:

1. Update all your packages by running ``conda update conda`` and ``conda update --all``
1. Google is the key to everything
2. Send us an email or ask on Piazza
3. Come to Office Hours and ask us
4. Ask after the lecture or during lecture break
3. Reinstall Anaconda