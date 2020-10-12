GCS in Python
=============

Python 3 implementation of the Graduated Cylindrical Shell model ([Thernisien, 2011](https://dx.doi.org/10.1088%2F0067-0049%2F194%2F2%2F33)).
Based on the existing IDL implementation in SolarSoft (`cmecloud.pro`, `shellskeleton.pro`).

The code in `gcs.py` provides the basic implementation of the GCS geometry, while the Matplotlib-based GUI
in `gcs_gui.py` uses [SunPy](https://sunpy.org/) to plot the model on top of coronagraph images provided by
[Helioviewer.org](https://www.helioviewer.org/).

![Screenshot](/img/screenshot.png?raw=true)

Note
----

This code is still in a quite early stage. It has been compared with the original IDL/SolarSoft version to verify the results, but only for a few case studies.
Please be careful when using it and compare to IDL when in doubt. If you find a bug or have suggestions for improvement, please notify me with a
GitHub [issue](https://github.com/johan12345/gcs_python/issues/new) or [Pull Request](https://github.com/johan12345/gcs_python/compare).

How to run the GUI
------------------

Python 3.7 or later is required.

It is recommended to use a [virtual environment](https://docs.python.org/3/tutorial/venv.html) so that the
Python packages you install as dependencies of GCS don't interfere with your globally installed packages.
On some Linux distributions, the additional `python3-venv` package needs to be installed for this to work.

```shell
python3 -m venv env
. env/bin/activate
```

Then, you can continue to install the dependencies and run the GCS GUI:
```shell
# install requirements
python3 -m pip install --upgrade pip setuptools
pip3 install -r requirements.txt

# run GCS GUI, providing a date/time and the spacecraft to use
python3 gcs_gui.py "2020-04-15 06:00" STA SOHO
```

Information on the available command line arguments for the GUI is given when you run the help option:
```shell
python3 gcs_gui.py -h
```
