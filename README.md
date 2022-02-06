# Fall Detection using Pose Estimation

## Introduction
Fall Detection model based on [OpenPifPaf](https://github.com/vita-epfl/openpifpaf)

PyPI Library: https://pypi.org/project/openpifpaf/

The detection can run on both GPU and CPU, on multiple videos, RTSP streams, and webcams/USB cameras. Unlike most open-source fall detection models that work on large single subjects, this improved model integrates a person tracker that can detect falls in scenes with more than one person.

## Demo Videos
![Walking Trip](https://github.com/cwlroda/falldetection_openpifpaf/blob/master/media/walking_trip.gif)
![Stubbed Toe](https://github.com/cwlroda/falldetection_openpifpaf/blob/master/media/stubbed_toe.gif)
![Drunk](https://github.com/cwlroda/falldetection_openpifpaf/blob/master/media/drunk.gif)

Video credits: 50 Ways to Fall ([Link](https://www.youtube.com/watch?v=8Rhimam6FgQ)), ran on a single NVIDIA Quadro P1000

## Test Results
UR Fall Detection Dataset ([Link](http://fenix.univ.rzeszow.pl/~mkepski/ds/uf.html)), tested on two NVIDIA Quadro GV100s.
- Precision: 100%
- Recall: 83.33%
- F1 Score: 90.91%

_Note: Due to lack of available datasets, false positives and true negatives were not tested._

## Environment
- Ubuntu 18.04 x86_64
- Python 3.7.6
- Anaconda 3
- CUDA 10.2

## Usage
**Setup Conda Environment**
```console
$ conda create --name falldetection_openpifpaf python=3.7.6
$ conda activate falldetection_openpifpaf
```

**Clone Repository**
```console
$ git clone https://github.com/cwlroda/falldetection_openpifpaf.git
```

**Download OpenPifPaf 0.11.9 (PyPI)**
```console
$ pip3 install openpifpaf
```

**Install Dependencies**
```console
$ pip3 install -r requirements.txt
```

**Execution**

For videos/RTSP streams, navigate to _config/config.xml_ to edit the video/RTSP stream path, then run:
```console
$ python3 -m openpifpaf.video --show
$ (use --help to see the full list of command line arguments)
```
For webcams/USB cameras, run:
```console
$ python3 -m openpifpaf.video --source {CAMERA_ID} --show
$ (use --help to see the full list of command line arguments)
```

