# Sensor Fusion Project
 Project Submission for RBE 595 Sensor Fusion and Perception

## Prerequisite

Install manually the following packages :

```
pytorch >= 1.0.1
pebble
scipy
scikit-image
argparse
matplotlib
imageio
tensorboardX
blessings
progressbar2
path.py
```

## Preparing training data
Preparation is roughly the same command as in the original code.

For [KITTI](http://www.cvlibs.net/datasets/kitti/raw_data.php), first download the dataset using this [script](http://www.cvlibs.net/download.php?file=raw_data_downloader.zip) provided on the official website, and then run the following command.

## Training
Once the data are formatted following the above instructions, you should be able to train the model by running the following command
```bash
python3 train.py /path/to/the/formatted/data/ -b4 -m0.2 -s0.1 --epoch-size 3000 --sequence-length 3 --log-output [--with-gt]
```

## Trained Model
The trained model has been pushed to the following drive link,
https://drive.google.com/drive/folders/1-EoR79WtM-1QsEILbLS8xm8o8peg6y4b?usp=share_link

## Evaluation

Disparity map generation can be done with `run_inference.py`
```bash
python3 run_inference.py --trained_model /path/to/dispnet --dataset-dir /path/pictures/dir --output-dir /path/to/output/dir
```
Will run inference on all pictures inside `dataset-dir` and save a jpg of disparity (or depth) to `output-dir` for each one see script help (`-h`) for more options.