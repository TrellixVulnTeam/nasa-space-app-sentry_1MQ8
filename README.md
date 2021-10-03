# nasa-space-app-sentry
Software repository for 2021 NASA space apps challenge - Team SENTRY

Add introduction here ??

# landslide_sentry

The *landslide_sentry* package implements a complete routine for detecting landslide locations using satellite data as inputs. The required satellite data includes: optical images (B2, B3, B4 from Sentinel 2), elevation, hillshade and slope data. The routine also accepts optional cloud mask to prevent wrongly classifying cloud regions as landslides.

*landslide_sentry* package features an automatic data downloader (*landslide_sentry.tiff_downloader.py*) which is based on Google Earth Engine API. The data are pre-processed by *landslide_sentry.tiff_utils.py* and feed into a convolution neural network for landslide detection. The neural network model and classifying functionality is provided by a separate [repository](https://github.com/ChenyuZhang16/landslide-mapping-with-cnn), which is adapted from the [work](https://github.com/nprksh/landslide-mapping-with-cnn) of Nikhil Prakash, Andrea Manconi and Simon Loew. The output of the routine are landslide regions in tif formats, and optional png images.

# Example

This [jupyter notebook](example/detect_landslide_colab.ipynb) provides a complete walkthough of how to use *landslide_sentry*. We recommend running the notebook on Google Colab via: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/ChenyuZhang16/nasa-space-app-sentry/blob/main/example/detect_landslide_colab.ipynb) to avoid any frustration of setting up the environment.

This [folder](example/example_outputs) provides some example outputs of regions with recent documented landslides.

# Installation

## Requirement
- numpy
- matplotlib
- tqdm
- tensorflow
- osgeo
- gadl
- Open CV
- earthengine-api
- pyna:
```bash
pip install git+https://github.com/nargyrop/pyna.git
```
- cnn_landslide_mapping:
```bash
pip install git+https://github.com/ChenyuZhang16/landslide-mapping-with-cnn.git
```

## How to install
Using `pip`:

``` bash
pip install git+https://github.com/ChenyuZhang16/nasa-space-app-sentry.git
```

From source:
``` bash
pip install --editable .
```