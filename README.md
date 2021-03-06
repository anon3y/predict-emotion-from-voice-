Aim : Predict Emotions from audio

link for data files : <a href= https://zenodo.org/record/1188976#.XQtAlrxKiM8>RAVDNESS</a>
Each RAVDESS file has a unique filename. The filename consists of seven two-digit numerical identifiers, separated by hyphens (e.g., 02-01-06-01-02-01-12.mp4). Each two-digit numerical identifier defines the level of a different experimental factor. The identifiers are ordered: Modality–Channel–Emotion–Intensity–Statement–Repetition–Actor.mp4 or .wav. The numerical coding of levels is described in Table 1. For example, the filename “02-01-06-01-02-01-12.mp4” refers to: Video-only (02)–Speech (01)–Fearful (06)–Intensity normal (01)–Statement “dogs” (02)–First repetition (01)–Twelfth actor, female (12). The gender of the actor is coded by the actor’s number, where odd numbered actors are male, even numbered actors are female.

Filename identifiers

Modality (01 = full-AV, 02 = video-only, 03 = audio-only).

Vocal channel (01 = speech, 02 = song).

Emotion (01 = neutral, 02 = calm, 03 = happy, 04 = sad, 05 = angry, 06 = fearful, 07 = disgust, 08 = surprised).

Emotional intensity (01 = normal, 02 = strong). NOTE: There is no strong intensity for the ‘neutral’ emotion.

Statement (01 = “Kids are talking by the door”, 02 = “Dogs are sitting by the door”).

Repetition (01 = 1st repetition, 02 = 2nd repetition).

Actor (01 to 24. Odd numbered actors are male, even numbered actors are female).

<li> For Strorage Google drive was used and each file was then read into google colab </li>

<li><b>approach taken for  feature engineering  : Cepstral mean and variance normalization (CMVN)</b> is a computationally efficient normalization technique for robust speech recognition.
For each audio file the<a href = https://en.wikipedia.org/wiki/Mel-frequency_cepstrum>mfccs</a> was extracted using python library <a href = https://librosa.github.io/librosa/>Librosa</a>the number of mfcc's extracted was 20 then mean of the mfcc was taken for each audio file, with sampling rate same for each file i.e 3 seconds.

<li> <b> ML approach to classify emotions </b>, only audio speech files are used and  Random Forest algorithm  is used for classifying emotions the ML protoype is in the file ML_Prototype.ipynb in the repository </li>

<b> Scaling </b>
<li> Since audio file/data the mean is taken and fed to the model this approach can scale easily byt  using the any audio files and extracting and storing the mean of mfcc for that file which is not  storage intensive </li>

<b> DL Approach to classify emotions</b>

<li> each audio file is read from google drive and mffcc are extracted then spectrogram is plotted using  <a href = https://librosa.github.io/librosa/>Librosa</a> and stored on gdrive for training the model. each Spectogram is then fed to a CNN network to produce the classification prediction.DL protoype is in the file DL_Prototype.ipynb in the repository</li>
<b> Scaling </b>
<li> for training each audio file is converted to .jpg images and stored on gdrive, this approach is also not storage intensive and can scale with newer data to train </li>
















  
  

  
  
