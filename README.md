# TalkNet-ASD Video Reframing Project

## Overview

This project utilizes TalkNet-ASD for video processing to highlight key participants in video frames. The goal is to reframe video footage to place the most active individuals in prominent sections of the frame, making it optimized for mobile viewing. The workflow includes downloading a YouTube video, trimming it for efficient processing, and running TalkNet-ASD to generate bounding boxes and scores for each person in the video. The output is a reframed video that focuses on the most active participants.

This project also includes videos showing the process before and after reframing, providing a clear visual demonstration of the transformation.

## Prerequisites

Make sure you have the following installed before running this project:
- **Git**: To clone the repository.
- **Python**: Ensure Python is installed and accessible.
- **ffmpeg**: For video trimming.
- **yt-dlp**: To download sample videos from YouTube.

## Installation Steps

1. **Clone the TalkNet-ASD Repository**:

```sh
!git clone https://github.com/TaoRuijie/TalkNet-ASD.git
```

2. **Install Dependencies**:

Navigate to the project directory and install the required dependencies:

```sh
!pip install -r requirement.txt
```

3. **Install yt-dlp**:

To download a YouTube video for sample testing:

```sh
!pip install yt-dlp
```

## Workflow

1. **Download Sample Video**:

Use `yt-dlp` to download a sample video from YouTube for testing purposes.

2. **Trim the Video**:

To improve performance, you may want to trim the downloaded video. You can use `ffmpeg` to do this:

```sh
!ffmpeg -i demo/youtube_video.mp4 -ss 00:10:48 -to 00:12:10 -c copy demo/upd_trimmed_video.mp4
```

3. **Run TalkNet-ASD**:

Run the `demoTalkNet.py` script to analyze the trimmed video and generate the bounding box and activity score data (saved as pickle files):

```sh
!python demoTalkNet.py --videoName upd_trimmed_video.mp4
```

After running this, you will get the pickle files that contain tracking data for each individual in the video.

## Video Reframing

Using the generated pickle files, the next step is to run the Python script to reframe the video. This will focus on the most active participants by placing one person in the top section and another in the bottom section of a vertical frame.

The reframed video is created with a resolution of 720x1280 pixels, following a 9:16 aspect ratio. This vertical format is ideal for mobile viewing, ensuring that the most important participants are highlighted effectively.

1. **Run the Reframing Script**:

```sh
python reframe_video.py
```

The script will use the bounding boxes and scores to create a new video output with a vertical layout, highlighting key participants.

## Technologies Used

- **OpenCV (cv2)**: For video processing and manipulating video frames.
- **NumPy**: For efficient numerical operations and handling arrays.
- **MoviePy**: For working with video and audio editing.
- **Pickle**: For storing and loading pre-processed data.
- **SciPy**: For handling missing data through interpolation.
- **ffmpeg**: For trimming the input video.
- **yt-dlp**: For downloading YouTube videos.


 ## Output

The project includes two video files to demonstrate the changes:

- **Before Video**: The original video before processing, showing all participants without specific emphasis. 

- **After Video**: The reframed video highlighting the most active participants, optimized for mobile viewing.
- https://github.com/user-attachments/assets/25465a45-4d3b-4ca4-95de-c3a9c249535c


The output video will be saved in the specified directory, focusing on the most active individuals by placing them in a vertical frame format (9:16 aspect ratio) suitable for mobile viewing.

## Contribution

Contributions are welcome! Feel free to submit pull requests to add features, improve the existing code, or fix bugs.
 

## Contact

For any questions or suggestions, please reach out via  rayirahul67@gmail.com.

