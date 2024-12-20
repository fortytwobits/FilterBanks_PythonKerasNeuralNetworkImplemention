# MDCT Filter Bank Implementation using Python Keras 

Simple programs to use a keras or PyTorch convolutional neural network as implementation of MDCT filter banks.
For background on MDCT filter banks, see our lecture Multirate Signal Processing, 
https://www.tu-ilmenau.de/mt/lehrveranstaltungen/lehre-fuer-master-mt/multirate-signal-processing/
slides lecture 14.

The advantages of the neural network implementation are: 
* The possibility to use the GPU in this way and speed up the computation, 
* hence it might not need a specialized fast implementation,
* It can be easily integrated in NN programs, for instance for source separation, or as a starting point for further optimization or training.
Gerald Schuller, November 2017

## Getting Started
The keras_*.py scripts contain the keras implementations whereas the pt_*.py scripts contain the PyTorch implementations

In the "main" section of the MDCT programs, the variable N=1024 is the number of subbands of the MDCT. It can be set to any even number.
It produces a "sine window" of length 2N.
The analysis program *_MDCTanalysis.py reads in a sound file, for instance the "test.wav" file. In Keras the different subbands appear in its "channels" dimension.
The program writes the subband signals into the file "mdct_subbands.pickle".
The synthesis program *_MDCTsynthesis.py reads in the file "mdct_subbands.pickle" and play back the reconstructed sound, using pyaudio.
The program *_MDCTanasyn.py calls the analysis and synthesis programs in a sequence.

To start, simply execute:
python *_MDCTanasyn.py

The ..stereo.. files process stereo sound files, where stereo is in the signal dimension, and the subbands are again in the Keras/PyTorch channels dimension. 


