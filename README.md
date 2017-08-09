calculating-spaceweather-keywords
=================================

The Solar Dynamics Observatory (SDO) takes about a terabyte and a half of data a day, which is more data than any other satellite in NASA history. SDO data are stored in a [publicly-available, web-accessible pSQL database](http://jsoc.stanford.edu/ajax/lookdata.html) at Stanford University. These data are also accessible via a JSON API called [jsoc_info](http://jsoc.stanford.edu/jsocwiki/AjaxJsocConnect) and a python library called [drms](https://drms.readthedocs.io/en/stable/).

One of the data products released by the Solar Dynamics Observatory is called [Space-weather HMI Active Region Patches](http://link.springer.com/article/10.1007%2Fs11207-014-0529-3), or SHARPs. SHARPs include patches of vector magnetic field data taken by the Helioseismic and Magnetic Imager (HMI) instrument aboard SDO. These patches encapsulate automatically-detected active regions. SHARP data also include spaceweather keywords describing these active regions. [Bobra & Couvidat (2015)](http://arxiv.org/abs/1411.1405) and [Bobra & Ilonidis (2016)](https://arxiv.org/abs/1603.03775) used machine-learning algorithms to show that these spaceweather keywords are useful for predicting solar activity. 

### Contents

This repository contains several codes designed to show you how to interact with and understand SHARP data (view ipython notebooks on the [ipython notebook viewer](http://nbviewer.ipython.org/)).

* `plot_swx_d3.ipynb` generates interactive [d3](https://d3js.org/) plots of keywords and images, and movies using image data.
* `movie.ipynb` generates movies of SHARP data.
* `hedgehog.ipynb` provides a way to visualize the vector magnetic field in SHARP data.
* `feature_extraction.ipynb` takes images from another instrument on SDO, called the Atmospheric Imaging Assembly (AIA), to determine which AIA pixels fall within the SHARP bounding boxes; this code also contains examples of how to automatically extract features from AIA data.
* `calculate_swx_fits.py` calculates spaceweather keywords from vector magnetic field data. The inputs, dependencies, and example useage for `calculate_swx_fits.py` are described below.
* `disambiguation.py` contains several functions that disambiguate the azimuthal component of the vector magnetic field data and construct the field vector in spherical coordinate components on a CCD grid. See `disambiguate_data.py` for some examples.

Sample data are included in this repository under the test_fits_files directory. All SDO data are publicly available. 

### Dependencies
The various codes in this repository depend on the [NumPy](http://numpy.org/), [SciPy](http://www.scipy.org/), [SunPy](http://www.sunpy.org/), [AstroPy](http://www.astropy.org/), and [drms](https://drms.readthedocs.io/en/stable/) libraries.

