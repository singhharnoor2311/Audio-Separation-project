# Audio Separation Project
In our audio separation project, we demonstrate using machine-learning techniques the capability of separating the different components of an audio track, such as vocals, drums, and bass, from a mixed audio signal by using machine-learning techniques.  
  
There are a wide variety of applications for the ability to isolate sound components, ranging from remixing music tracks to isolating vocals for karaoke or voice-over purposes. Furthermore, music separation has become a popular topic in recent years as a result of the increasing demand for personalized audio content in recent years. Because there are several applications that require the analysis and understanding of sound data, this is inevitable.  
  
Python was used in our project to separate music from audio files obtained from YouTube by using Python code. Through the use of different algorithms, we were able to separate the different components of the audio tracks into individual channels by utilizing different algorithms in our project. With this method, greater control was available over the audio content as each component could be adjusted or modified independently of the others, allowing for greater control over the content.  
  
Explanation of Code:  
  
The first step of the code is to mount Google Drive to the Colab notebook. The next line clones the FFMPEG repository, which is a tool used for working with audio and video files. The following three lines install Python packages: PyTube, PyDub, and OpenUnmix. OpenUnmix is a library that allows you to separate audio sources from video sources by using PyTube, PyDub, and Line. PyTube downloads videos from YouTube, PyDub manipulates audio files, and Line. Open-Unmix is a powerful open-source library designed to separate individual sources, such as vocals and instruments, from a mixed audio signal. Built using the PyTorch framework, it provides high-quality results, and is modular and easily extensible, allowing users to customize it to their specific use cases. Additionally, it comes with pre-trained models, has a well-documented API, and is compatible with popular audio processing libraries like Librosa and TorchAudio. For these reasons, Open-Unmix was chosen for our project as it offered high-quality results, customizability, ease of use, an open-source license, and compatibility with other audio processing libraries.  
  
The next line of code defines a function that takes YouTube video stream data and a key name. The function then applies various transformations to the stream data, parsing the query string encoded values, and converting them to a dictionary. "url_encoded_fmt_stream_map," this function gets the streaming data formats and adaptive formats from the player response. It creates a list of dictionaries with information about each format and appends it to the stream data. If the key is not "url_encoded_fmt_stream_map," the function unquotes the query string values and creates a list of dictionaries. This function modifies YouTube video stream data to make it more usable.  
  
We use the `yt_dlp` package to download YouTube audio. It first extracts video information from the specified YouTube URL using `YoutubeDL().extract info()`. Then it sets some download options, such as the audio format and the output file name. It uses `YoutubeDL(options)` to download the audio from the video. The downloaded audio is saved in the current working directory as a `.mp4` file with the same name as the video title. The `with` statement ensures that the `YoutubeDL` object is properly cleaned up after use.  
  
After that, it converts an MP4 audio file into a WAV audio file. It displays the resulting audio and a waveform plot. It first checks if the WAV file already exists and loads it if it does. If the WAV file does not exist, it exports the MP4 audio file to WAV format and loads the resulting WAV file. Finally, it displays the audio and a waveform plot in the notebook.  
  
   
  
In the next code, we load an audio file and resample it at a fixed sample rate of 44100 Hz. It then normalizes the audio so that the maximum amplitude is 1.0. This is a common pre-processing step before using audio data for machine learning applications, as it ensures that the audio data is consistent and within a reasonable range of values. The code also checks if the GPU is available and sets the device accordingly.  
This code splits the audio into 20-second segments and displays them. Then, it computes the spectral centroid of each segment and stores it in a list. It finds the segment with the highest spectral centroid and stores its index. It then retrieves the segment with the highest spectral centroid and stores it as a dictionary containing audio data and sample rate. Finally, it displays the audio with the highest spectral centroid and plots the corresponding waveform.  
  
The last code uses the open-unmix library to separate audio data into its components, such as vocals, drums, and bass. It first loads the audio data into a tensor and then uses the `separate` function to separate it. The separated components are then printed out and displayed as audio files in the notebook. Finally, a wave plot is generated for each component to visualize its amplitude over time.  
   
The image shows the Wave Plot of vocals  
  
        
The image shows the bass Wave Plot  
   
The image shows the wave plot of drums.  
  
               
This image shows the other wave plot.  
  
Theory and concepts from the module that our project links back to:  
  
Unit 2- Basic Audio Processing:   
  
Audio processing using Python starts with loading and playing audio files. This involves understanding the audio file's characteristics, such as the format, sample rate, and number of channels. To process audio data, we typically need to work with audio in segments, so we may need to divide audio data into smaller parts called segments. By doing this, we can manipulate or analyze each segment separately, which makes it easier to work with audio as a whole.  
  
  
Unit 3- Characteristics of Speech:  
Audio processing focuses on understanding how speech is produced and its general characteristics. This involves analyzing aspects such as the volume or loudness of speech. It also involves the distribution of frequencies, the rate at which syllables are pronounced, and the rate at which pitch changes. Additionally, we also study the structure of speech which includes smaller units of sound like phonemes and syllables which make up words and sentences. By understanding these patterns and characteristics, we can develop techniques to better process and analyze speech audio.  Unit 5- Psychoacoustics:  
  
It is a branch of science that studies how humans perceive sound. It examines how the ear and brain work together to understand different aspects of sound. This includes frequency, amplitude, and other factors that affect sound perception. Psychoacoustics helps us understand how we hear sounds in different environments, even when background noise or other external factors affect our perception of sound.  
Unit 8- Audio Analytics and Data Features:  
In this unit, we will analyze the raw audio data and extract specific features that can help us better understand the sound. Before we can do this, we need to understand the audio data format. For example, we need to know the sample rate, which tells us how many sound samples are taken per second. We also need to understand the sample format, which tells us how each sample is represented (for example, as an integer or a floating-point number). We need to know aliasing, which occurs when the sample rate is too low to capture all frequencies in the sound. We also need to know how many channels the audio data has (for example, mono or stereo), and the container format (for example, WAV or MP3). Once we have this information, we can extract the salient features of the audio data we require for our analysis.  
  
Unit 11- Music Information Retrieval and Analysis:  
  
Music Information Retrieval (MIR) is a field that extracts meaningful information from music recordings. This includes identifying features such as beats, rhythm, and melody, as well as recognizing the song structure, such as verse-chorus patterns. MIR techniques use machine learning and deep learning algorithms to analyze audio recordings and extract relevant information. MIR's ultimate goal is to provide useful information about music, such as artist or genre classification, recommendation systems, and even automated music creation.  
