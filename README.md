# Problem
We want to be able to visualize and understand the audio analysis from different songs.

# Questions
1. What is its value in analyzing audio?
2. How does the FFT work?
3. How can we use the FFT for implementing an audio analysis visualizaion?

# Resources
1. [FFT Audio Analysis]
2. [FFT Data]

### 1. Mini-abstract and relevance of [FFT Audio Analysis]:
The FFT is another approach for solving the linear Discrete Fourier Transform, which
solves the signal's frequency spectrum. The DFT converts a list of equally spaced
samples of a function into a list of coefficients by summing up all of the sine waves.
In digital signal processing, the DFT function is any quantity or signal that varies
over time. These signals are sample over a finite time interval in a window function.
The FFT is a much faster calculation, since it is a log based algorithm. The FFT computes
the DFT of size N in O(N log N) operations. When you look at a sample and it does not have
interger multiples in the cycles, the DFT will think there are other frequencies in the
window frame. If the sample frame does not have a sine wave then there other tones in it.
IF there are glitches in the sine waves, this will create an inaccurate summation of the
function in the frame. In order to avoid these issues, we have window functions. Some have
larger bandwidths because of the different amplitude frequencies. There are window functions
dominate for different types of noise. 


*This answers question 1 and 2*

### 2. Mini-abstract and relevance of [FFT Data]:



*This answers question 3*

[FFT Audio Analysis]: https://www.youtube.com/watch?v=tqcZrPMi4nk
[FFT Data]: https://www.youtube.com/watch?v=H144ipQa22Q
