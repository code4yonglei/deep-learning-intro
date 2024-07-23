---
title: Setup
---
## Software Setup

::::::::::::::::::::::::::::::::::::::: discussion

### Installing Python

[Python][python] is a popular language for scientific computing, and a frequent choice
for machine learning as well. 
To install Python, follow the [Beginner's Guide](https://wiki.python.org/moin/BeginnersGuide/Download) or head straight to the [download page](https://www.python.org/downloads/).

Please set up your python environment at least a day in advance of the workshop.
If you encounter problems with the installation procedure, ask your workshop organizers via e-mail for assistance so
you are ready to go as soon as the workshop begins.

:::::::::::::::::::::::::::::::::::::::::::::::::::

## Installing the required packages{#packages}

[Pip](https://pip.pypa.io/en/stable/) is the package management system built into Python.
Pip should be available in your system once you installed Python successfully.

1. [Create a virtual environment](https://packaging.python.org/en/latest/guides/installing-using-pip-and-virtual-environments/#create-and-use-virtual-environments) called `dl_workshop`:

::: spoiler

### On Linux/macOs

```bash
python3 -m venv dl_workshop
```

:::

::: spoiler

### On Windows

```bash
py -m venv dl_workshop
```

:::

2. Activate the newly created virtual environment

::: spoiler

### On Linux/macOs

```bash
source dl_workshop/bin/activate
```

:::

::: spoiler

### On Windows

```bash
dl_workshop\Scripts\activate
```

:::

3. Install the required packages:

::: spoiler

### On Linux/macOs

```bash
python3 -m pip install seaborn scikit-learn pandas
```

:::

::: spoiler

### On Windows

```bash
py -m pip install seaborn scikit-learn pandas
```

:::

4. Install the TensorFlow library:

::: spoiler

### On Linux/macOs

```bash
python3 -m pip install tensorflow
```

::: spoiler

### Advanced: TensorFlow with support for Mac M1/M2/M3

Recent Macs have special chips (M1/M2/M3) that can accelerate deep learning processes.
Apple has developed the [tensorflow-metal](https://developer.apple.com/metal/tensorflow-plugin/) package to support these chips in TensorFlow.
This is not supported by the standard TensorFlow installation, and not required for this lesson.

Nevertheless, you can install the on top of the standard `tensorflow`:

```bash
python -m pip install tensorflow-metal
```

:::
:::

::: spoiler

### On Windows

```bash
py -m pip install tensorflow
```

:::

Note that Tensorflow makes Keras available as a module too.

### Python package installation troubleshooting

:::::::::::::::: spoiler

### Troubleshooting for Windows
It is possible that Windows users will run into version conflicts. If you are on Windows and get
errors running the command, you can try installing the packages using pip within a conda environment:

```bash
conda create -n dl_workshop python jupyter
conda activate dl_workshop
pip install tensorflow>=2.5 seaborn scikit-learn pandas
```

:::::::::::::::::::::::::

::::::::::::::::::: spoiler

### Troubleshooting for Macs with Apple silicon chip
Newer Macs (from 2020 onwards) often have a different kind of chip, manufactured by Apple instead of Intel.
This can lead to problems installing Tensorflow.
If you get errors running the installation command or conda hangs endlessly,
you probably [need to change the version of Anaconda you have installed](https://www.youtube.com/watch?v=BEUU-icPg78).

1. Uninstall Anaconda
2. [Download the version of Anaconda for Apple chips][anaconda-distribution] (i.e. the version with "(M1)" in the name)
   and install it with the default settings
3. Follow [the instructions above](#packages) to install the required packages

::::::::::::::::::::::::::::

## Starting Jupyter Lab

We will teach using Python in [Jupyter Lab][jupyter], a programming environment that runs in a web browser.
Jupyter Lab is compatible with Firefox, Chrome, Safari and Chromium-based browsers.
Note that Internet Explorer and Edge are *not* supported.
See the [Jupyter Lab documentation](https://jupyterlab.readthedocs.io/en/latest/getting_started/accessibility.html#compatibility-with-browsers-and-assistive-technology) for an up-to-date list of supported browsers.

If you installed Python using Anaconda, Jupyter should already be on your system. If
you did not use Anaconda, use the Python package manager pip
(see the [Jupyter website][jupyter-install] for details.)

To start Jupyter Lab, open a terminal (Mac/Linux) or Anaconda prompt (Windows) and type the command:

```bash
jupyter lab
```

To start the Python interpreter without Jupyter Lab, open a terminal (Mac/Linux) or Anaconda prompt (Windows)
or git bash and type the command:

```bash
python
```

## Check your setup
To check whether all packages installed correctly, start a jupyter notebook in jupyter lab as
explained above. Run the following lines of code:
```python
import sklearn
print('sklearn version: ', sklearn.__version__)

import seaborn
print('seaborn version: ', seaborn.__version__)

import pandas
print('pandas version: ', pandas.__version__)

import tensorflow
print('Tensorflow version: ', tensorflow.__version__)
```

This should output the versions of all required packages without giving errors.
Most versions will work fine with this lesson, but:
- For Keras and Tensorflow, the minimum version is 2.12.0
- For sklearn, the minimum version is 1.2.2

## Fallback option: cloud environment
If a local installation does not work for you, it is also possible to run this lesson in [Binder Hub](https://mybinder.org/v2/gh/carpentries-incubator/deep-learning-intro/scaffolds). This should give you an environment with all the required software and data to run this lesson, nothing which is saved will be stored, please copy any files you want to keep. Note that if you are the first person to launch this in the last few days it can take several minutes to startup. The second person who loads it should find it loads in under a minute. Instructors who intend to use this option should start it themselves shortly before the workshop begins.

Alternatively you can use [Google colab](https://colab.research.google.com/). If you open a jupyter notebook here, the required packages are already pre-installed. Note that google colab uses jupyter notebook instead of Jupyter Lab.

## Downloading the required datasets

Download the [weather dataset prediction csv][weatherdata] and [Dollar street dataset (4 files in total)][dollar-street]

[anaconda]: https://www.anaconda.com/products/individual
[anaconda-distribution]: https://www.anaconda.com/products/distribution
[dollar-street]: https://zenodo.org/api/records/10970014/files-archive
[jupyter]: http://jupyter.org/
[jupyter-install]: http://jupyter.readthedocs.io/en/latest/install.html#optional-for-experienced-python-developers-installing-jupyter-with-pip
[python]: https://python.org
[video-mac]: https://www.youtube.com/watch?v=TcSAln46u9U
[video-windows]: https://www.youtube.com/watch?v=xxQ0mzZ8UvA
[penguindata]: https://zenodo.org/record/3960218/files/allisonhorst/palmerpenguins-v0.1.0.zip?download=1
[weatherdata]: https://zenodo.org/record/5071376/files/weather_prediction_dataset_light.csv?download=1
[weatherbbqdata]: https://zenodo.org/record/4980359/files/weather_prediction_bbq_labels.csv?download=1


