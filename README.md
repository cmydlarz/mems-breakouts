# MEMS microphone breakout boards
After working on various audio sensing projects I built up a collection of breakout boards for different MEMS microphones. The repo is broken down by microphone model. Some microphones have multiple board sizes to fit the different housings we were experimenting with.

## TDK Invensense ICS-40720 - high SNR analog
When [this analog mic](https://invensense.tdk.com/products/analog/ics-40720) came out it blew everything else out of the water. The 70dBA SNR was a huge jump from the \~60dBA alternatives at the time and the differential output helped overcome the major analog mic drawback of RFi noise pickup. This SNR has since been beaten by the [Invensense ICS-40730](https://invensense.tdk.com/products/analog/ics-40730) with its larger housing. The ICS-40720 shown below (image credit: [valordk](https://imgur.com/gallery/FbyeXKg)), had a pretty weak frequency response with a low frequency roll-off at around 75Hz making it less than ideal for urban sound monitoring applications and to be honest, most high-fidelity recording in general.

<p align="center">
<img src=ics40720/img/ics40720-front-back.png width="95%">
</p>

The application in our case was a first order ambisonic microphone that could use the small size of the MEMS microphone housing to reduce the overall size of the microphone array to reduce the impact of high frequency spatial aliasing that can reduce the perceived quality of spatial audio recordings. This project was undertaken with a fantastic team of NYU Music Tech students (Gabriel Zalles, Yigal Kamel, Ian Anderson, Chris Neil, and Spencer Cappiello). We published an AES paper on the design, build and testing of an initial prototype:

G. Zalles, Y. Kamel, I. Anderson, MI. YA. Lee, C. Neil, M. Henry, S. Cappiello, C. Mydlarz, M. Baglione, and A. Roginska (2017). 
[A low-cost, high-quality MEMS ambisonic microphone](https://www.researchgate.net/profile/Gabriel-Zalles/publication/320188555_A_Low-Cost_High-Quality_MEMS_Ambisonic_Microphone/links/59d3ad864585150177f9674c/A-Low-Cost-High-Quality-MEMS-Ambisonic-Microphone.pdf).
AES Convention 143, 9857.

The project was a lot of fun but was tricky as we were having to mechanically add directivity to each MEMS microphone breakout board to move them closer to a cardioid response. This wasn't easy and in all honesty reduced the immersion of recordings made using this microphone. For the short duration of the project and the steep learning curve the team went through the results were very impressive. You really had to scrutinize the recordings to tell the difference between our microphone and a [high-end Sennheiser](https://en-us.sennheiser.com/microphone-3d-audio-ambeo-vr-mic).

I've also included the CAD models for the mic in the ICS40720 directory in case that's of use to anyone. There are various board sizes but the CAD models were designed for the 12.5mm boards.

NB: seems like there's a directional version of the ICS-40720 that could be great for this application. The [ICS-40800](https://invensense.tdk.com/products/analog/ICS-40800) uses a dual port housing and according to their datasheet provides a cardioid-like response, very interesting and uses the same footprint as the ICS-40720 so a drop-in replacement!

## TDK Invensense ICS-43432 - high SNR digital
This model has gone into 2 of our urban noise monitoring sensors because of: (1) it's I<sup>2</sup>S output being able to interface directly with many single board computers and microcontrollers; (2) solid low frequency performance with a roll-off at \~30Hz; and (3) very high RFi and EMi resistance from it's almost immediate analog to digital conversion on the built-in ASIC.

<p align="center">
<img src=ics43432/img/ics43432.png width="75%">
</p>

This one was a real tight squeeze as I wanted it's diameter to be 1/4" so that it could fit inside a 1/4" calibrator and be closer to omni-directional. This ones tricky to assemble but with a stencil and PCB oven it usually works out fine. With a reliable design that fits inside this size of calibrator, you can quickly calibrate your field deployed MEMS mics periodically and calibrate them when using different types of waterproof screens.

