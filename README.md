Overview
============
A project that trains a LSTM recurrent neural network over a dataset of MIDI files. Implemented in TensorFlow. More information can be found on the [writeup about this project](http://yoavz.com/music_rnn/) or the [final report](http://yoavz.com/music_rnn_paper.pdf) written. *Warning: Some parts of this codebase are unfinished.*

Dependencies
============

* Python 2.7 (due to python-midi)
* Anaconda
* Numpy (http://www.numpy.org/)
* Tensorflow (https://github.com/tensorflow/tensorflow) - 0.8
* Python Midi (https://github.com/vishnubob/python-midi.git)
  * some newer fork than available via PyPI
* Mingus (https://github.com/bspaans/python-mingus)
* Matplotlib (http://matplotlib.org/)

Basic Usage
===========

## Install the environment:

First install Anaconda.

Then create conda environment `music_rnn`, install dependencies and download data:

```shell
./install.sh
```

## Activate the conda environment

```shell
source activate music_rnn
```

## Prepare data

Generate the sequences and chord mapping file to `data/nottingham.pickle`:

```shell
python nottingham_util.py
```

## Train a model

Start training a model:

```shell
python rnn.py --run_name <run_name>
```

Use the grid object in `rnn.py` to edit hyperparameter configurations.

## Generate a song using a trained model

```shell
python rnn_sample.py --config_file <some_config_file>
```

Output will be stored in `best.midi`.

## Deactivate conda environment

When you're finished and want to switch to another project you can deactivate the conda environment:

```shell
source deactivate
```
