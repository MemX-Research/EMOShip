# EMOShip

This repository contains the EMO-Film dataset described in the paper "Do Smart Glasses Dream of Sentimental Visions? Deep Emotionship Analysis for Eyewear Devices".

If you use this dataset in your work, please cite our paper:
```bibtex
@article{chang2021memx,
  title={MemX: An Attention-Aware Smart Eyewear System for Personalized Moment Auto-capture},
  author={Chang, Yuhu and Zhao, Yingying and Dong, Mingzhi and Wang, Yujiang and Lu, Yutian and Lv, Qin and Dick, Robert P and Lu, Tun and Gu, Ning and Shang, Li},
  journal = {Proc. ACM Interact. Mob. Wearable Ubiquitous Technol.},
  year={2021},
  doi = {10.1145/3463509}
}

@article{zhao2022smart,
  title = {Do Smart Glasses Dream of Sentimental Visions? Deep Emotionship Analysis for Eyewear Devices},
  author = {Zhao, Yingying and Chang, Yuhu and Lu, Yutian and Wang, Yujiang and Dong, Mingzhi and Lv, Qin and Dick, Robert P. and Yang, Fan and Lu, Tun and Gu, Ning and Shang, Li},
  journal = {Proc. ACM Interact. Mob. Wearable Ubiquitous Technol.},
  year = {2022},
  doi = {10.1145/3517250}
}

```

## Dataset
The data of EMO-Film dataset is collected in a controlled laboratory environment. The video clips were selected from the FilmStim dataset, as FilmStim is one of the widely-used emotion-eliciting video dataset. We divided all videos of FilmStim dataset (64 video clips in total) into 7 categories based on the provided sentiment labels, each category corresponding to one emotional class (the neutral plus six basic emotion). The detailed description was given in Section 4.1 in the paper. 

Due to the privacy concerns raised by some volunteers, we cannot release the full dataset with all 25 the subjects included. However, following the outcomes of the privacy survey, we are able to make public a filtered version of our dataset, which consists of 16 subjects giving their permissions to release the data. The videos from the rest 9 participants are therefore omitted to protect their privacy.

The dataset can be downloaded [here](https://www.dropbox.com/s/eob69vsz90qf7uf/EMO-Film.tar.gz).

## Data Format
EMO-Film has two parts and a csv file:

**eye.tar.gz**: This compressed package contains eye images captured when each participant watched different video segments. It contains 16 folders, each corresponding to participants. There are two subfolders under each user folder, corresponding to the two video clips watched by the participant. Each subfolder contains eye images stored in JPG format.

**filmstim.tar.gz**: This compressed package contains the 64 video clips mentioned above. There are 64 folders corresponding to 64 video clips, and each folder contains the frames in JPG format of video clips.

**label.csv**: This CSV file contains the corresponding relationship between the eye part and the filmstim part, as well as the gaze position of the eyes and the user's emotion annotation.

It contains the following attributes:

`user`: The participant number.

`eye_frame_path`: The relative path of eye image frame. The frame has cropped to preserve only the eye area.

`world_frame_path`: The relative path of filmstim image frame. Please note that participants actually watched video clips from the display with glasses. After post-processing, the area outside the monitor has been excluded. Here is the content displayed on the monitor, that is, the frame of FilmStim dataset.

`gaze_x` and `gaze_y`: The gaze position in the space of the scene frame. The are floating point numbers and origin 0,0 at the bottom left and 1,1 at the top right. Please note that corresponding to the above, the areas outside the screen have been excluded.

`PD_x` and `PD_y`: The pupil diameter in pixels in two axial directions.

`confidence`: The confidence of pupil position. A value of 0 indicates no confidence and 1 indicates perfect confidence.

`label`: The emotion categories marked by the user, 0-6 respectively indicate angry, disgust, fear, happy, sad, surprise, and neutral.

