# Problem
We want to be able to visualize and understand the audio analysis from different songs.

# Questions
1. What is its value in analyzing audio?
2. How does the FFT work?
3. How can we use the FFT for implementing an audio analysis visualizaion?

# Resources
1. [FFT Audio Analysis]
2. [Frequency Domain]

### 1. Mini-abstract and relevance of [FFT Audio Analysis]:
The Fast Fourier Transform (FFT) is a more efficient approach for solving the linear Discrete Fourier Transform, which solves the signal's frequency spectrum. The DFT converts a list of equally spaced samples of a function (such as an audio file) into a list of coefficients by summing all of the sine waves. 

If the sample frame does not have a sine wave, then there other tones in it. If there are glitches in the sine waves, this creates an inaccurate summation of the function in the frame. In order to avoid these issues, we use/have window functions. Some have larger bandwidths because of the different amplitude frequencies. There are different window functions, which would be more appropriate for different categories of sounds.

When the FFT has a bunch of bins (equally divided strips in a window that describes the spectrum sample and frequency of the window), every signal is in the center of all the bins. If the signal is not in the center of the bin, it will diverge from its true value. This is phenomenon is called the Scallop loss. If you scale the FFT by sine scaling the waves using the Flatop Window approach, it will minimize Scallop loss.

The FFT simply takes a chunk of time (samples) and considers that chunk to be a single period of a repeating waveform. Most sounds are constant. Over any short period of time, the sound usually look like a regularly repeating function. The following is a way to consider this mathematically—taking a window over some portion of some signal that we want to consider as a periodic function.

*This answers question 1 and 2*

### 2. Mini-abstract and relevance of [Frequency Domain]:
In digital signal processing, the DFT function is any quantity or signal that varies over time. These signals are sampled over a finite time interval in a window function. The FFT is a much faster calculation (than the DFT), since it is a log based algorithm. The FFT computes the DFT of size N in O(N log N) operations. When you look at a sample and it does not have interger multiples in the cycles, the DFT will think there are other frequencies in the window frame. 

The more samples we process, the more accurate our FFT will be. We need to create a constant for the amount of fouriers per second (frames per second) and the width is simply the inverse function of that. In addition, we need to get the total number of transforms in order to sum up all of the frequencies within the spectrum. We need to look for the frequency content of the sound at all possible frequencies so we need to divide the frequency spectrum into a number of frequency bins. The number of samples in each analysis frame gives the size of the bin. The number of bins is given by the formula: ```numBins = sampleSize / 2```. The frequency depends on the relationship between the length of the FFT and the sample rate of the audio signal.

```python
fouriersPerSec = 24
fourierWidth = 1.0 / fouriersPerSec
sampleSize = fourierWidth * float(sampleRate)

totalTransforms = round(duration * fouriersPerSec)
freq = sampleRate / sampleSize * np.arange(sampleSize)
```

*This answers question 3*

[FFT Audio Analysis]: https://www.youtube.com/watch?v=tqcZrPMi4nk
[Frequency Domain]: http://music.columbia.edu/cmc/musicandcomputers/chapter3/03_04.php
