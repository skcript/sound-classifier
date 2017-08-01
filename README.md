# Deep-Sound

Environmental sounds are unstructured and similar to noise. However,the recognition of environmental sounds can benefit crime investigations, security systems and build a richer representation of the world than just using vision. One of the obstacles in research activities concentrating on environmental sound classification is the scarcity of suitable and publicly available datasets. In this project we built a sound classifier using various machine learning models and compared its performance. The Datasets used include

1. Google Audioset - https://research.google.com/audioset/
2. ESC 50 - https://github.com/karoldvl/ESC-50
3. ESC 10 - https://github.com/karoldvl/ESC-10 (Smaller version of the previous dataset).
4. UrbanSound8K - https://serv.cusp.nyu.edu/projects/urbansounddataset/taxonomy.html

Using Hand-crafted features : 

This feature extractor uses Librosa (https://github.com/librosa/librosa) library for computing the required feature values.
We used the following features for every sound file,

1. Melspectrogram: Compute a Mel-scaled power spectrogram. The coefficients that collectively make up the short-term power spectrum of a sound 
2. MFCCs : Mel-frequency cepstral coefficients. The Mel Scale is used to provide greater resolution for more
informative (lower) frequencies
3. Chorma-stft: Compute a chromagram from a waveform or power spectrogram. Projects into bins representing the 12 distinct
semitones (or chroma) of the musical octave. Stft stands for Short-time-Fourier Transform.
4. Spectral_contrast -  Distributions of sound energy over octave frequencies  
5. Tonnetz: Estimates tonal centroids as coordinates in a six-dimensional interval space

Concatenating everything, this process gives us feature vectors of length 193 for every sound file processed. Depending on the amount of data available we can apply various classifiers like SVM , Random Forest or a shallow feed forward neural network on top of this to get the required results.

