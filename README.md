# ERC-Convener-Q.2.-Submission
I have made use of Python to analyze and demodulate the signal.
The given original audio was modulated and the image below is the FFT plot obtained.
![FFT graph](https://github.com/user-attachments/assets/c9268529-e91c-4f7e-b82c-2cf71e8d0ef7)
We can conclude from the graph that the carrier frequency is 10000 Hz (10 kHz)

Demodulation steps:
Step 1: I have loaded the audio to the code 
Step 2: I multiplied the signal with cosine to demodulate. Then "demodulate= signal*carrier". This is the key step. It displaces the desired signal from a noisy signal.
Step 3: I applied low pass filter to allow only low frequencies and obstruct high frequency (i.e. noise). Here Nyquist formula is applied (i.e. fs=2fmax). For that I defined a function called "lowpass". Then I chose a cutoff frequency which is approximately around the the frequency of music content which we listen to. (i.e. cutoff_freq=4000 Hz)
Step 4: With the help of "lowpass" function, clean audio could be obtained (i.e. demod_op_4k.wav). I also explored a bit by changing the values of cutoff frequency back and forth. I observed that lower cutoff frequency removes more of noise than higher one. The original audio already had noise of frequency 9000-11000Hz. When I set cutoff freq to 10000Hz, it was still noisy and sharp but clearer than the original audio. So I tried to reduce the cutoff frequency to 500 Hz and it was much cleaner than before but muffled.
Step 5: A plot of both the filtered audio signals were obtained

![demod_500](https://github.com/user-attachments/assets/62f54111-799c-4539-b7a7-0937471e7d91)
![demod_4K](https://github.com/user-attachments/assets/c64f2c4d-482a-4481-b82f-422e1a66fbb8)

We can observe the drastic difference in the plot. We see more of noise in 4000Hz one than 500Hz one.
