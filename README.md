# ERC-Convener-Q.2.-Submission
I have made use of Python to analyze and demodulate the signal.
The given original audio was modulated and the image below is the FFT plot obtained.

![FFT graph](https://github.com/user-attachments/assets/c9268529-e91c-4f7e-b82c-2cf71e8d0ef7)

We can conclude from the graph that the carrier frequency is 10000 Hz (10 kHz)


Demodulation steps:

Step 1: I have loaded the audio to the code.

Step 2: I multiplied the signal with cosine to demodulate. Then "demodulate= signal*carrier". This is the key step. It displaces the desired signal from a noisy signal. We get the demodulated but unfiltered and obtain a plot of it.


![demod(unfilt) graph](https://github.com/user-attachments/assets/13bf40b2-7c28-4093-afae-3ac20833ce5f)



Filtering steps:

Step 1: Low pass filter allows only low frequencies and obstruct high frequency (i.e. noise in this case). Here Nyquist formula is applied (i.e. fs=2fmax). For that I defined a function called "lowpass" and uploaded demod_op.wav. Then I chose a cutoff frequency which is approximately around the the frequency of music content which we listen to. (i.e. cutoff_freq=4000 Hz).

Step 2: With the help of "lowpass" function, clean audio could be obtained (i.e. demod_op_4k.wav). I also explored a bit by changing the values of cutoff frequency back and forth. I observed that lower cutoff frequency removes more of noise than higher one. The original audio already had noise of frequency 9000-11000Hz. When I set cutoff freq to 10000Hz, it was still noisy and sharp but clearer than the original audio. So I tried to reduce the cutoff frequency to 500 Hz and it was much cleaner than before but muffled.

Step 3: A plot of the 3 filtered and demodulated audio signals were obtained

1) Filtered signal with cutoff frequency=4000 Hz
   
![filtered_4k graph](https://github.com/user-attachments/assets/e9fd35f6-aeb2-4f5d-a53c-f9911e3f5e11)



2) Filtered signal with cutoff frequency=10000 Hz

![filtered_10k graph](https://github.com/user-attachments/assets/6d2be136-c966-4f09-8be5-4fe7439e2fb2)



3) Filtered signal with cutoff frequency=500 Hz

![filtered_500 graph](https://github.com/user-attachments/assets/b5df26a6-70c0-4eab-8a59-78ca95bec5d2)



We can observe the drastic difference in the plot. We see more of noise in 4000Hz one than 500Hz one and the most in 10000 Hz one.
