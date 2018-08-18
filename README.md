# lybBass FX

This software tries to mimic "Virtual Subwoofer" Technology that was used in certain Windows Application for low end speakers that can't handle frequencies below 80hz.

# [Download here](https://lybsoft.github.io/bassfx_wasapi/release.zip)

# Requirements :

One resource contention free CPU Core recommended, otherwise set the software priority to High or Realtime to avoid crackling.

# Usage :

1. Set up a dummy playback sound device that didn't output to any sound device.

For example, use Voicemeeter but do not run the software or shutdown the voicemeeter engine.

![example_1](https://lybsoft.github.io/bassfx_wasapi/usage1.PNG)

2. Download the lybBass FX Software, Unzip it and open cfg.ini.

3. Change "CHANGE_ME" to the device number of your playback sound. You can guess if you don't know what is your sound device ID number. It starts from 1. Also change the sample rate.

4. Run the Software, your Sound Device should show up. If it doesn't try chaging the device ID number again until it shows up.

![example_2](https://lybsoft.github.io/bassfx_wasapi/usage2.PNG)

5. You're ready to go. We recommend to also install and use [EqualizerAPO](https://sourceforge.net/projects/equalizerapo/) to increase the bass. Install it on your Real Sound Device, not the dummy sound device. Do keep in mind the psuedo bass frequencies you've set on cfg.ini.

# Example Config for Most USB Speakers :
~~~~~~~~
[config]
device=CHANGE_ME
;device id that will be used for output
device_is_sub=0
;set that the device is a subwoofer, crossover effect applied if enabled
tweeter=0
;device id that will be used for output #2, crossover effect applied if 'device_is_sub=1'
xover=200
;tweeter and subwoofer crossover
lshelfgain=0
;low shelf gain for main channel
lshelf=80
;low shelf frequency

;psuedo-bass dsp
pass1=46
;low pass mix, 12 semitones
pass1gain=0
pass1e=1
;enable or disable dsp (saves cpu)
pass2=23
;low pass mix, 24 semitones
pass2gain=0
pass2e=1
;enable or disable dsp (saves cpu)

;system settings
freq=48000
;your sound device sample rate
buffer=50
;buffer size. affects latency, sound quality and cpu usage.
~~~~~~~~

# Example Config for Dell Laptop Speaker with Subwoofer without Dell Audio Drivers :
~~~~~~~~
[config]
device=CHANGE_ME_TO_SUB
;device id that will be used for output
device_is_sub=1
;set that the device is a subwoofer, crossover effect applied if enabled
tweeter=CHANGE_ME
;device id that will be used for output #2, crossover effect applied if 'device_is_sub=1'
xover=200
;tweeter and subwoofer crossover
lshelfgain=0
;low shelf gain for main channel
lshelf=80
;low shelf frequency

;psuedo-bass dsp
pass1=80
;low pass mix, 12 semitones
pass1gain=0
pass1e=1
;enable or disable dsp (saves cpu)
pass2=40
;low pass mix, 24 semitones
pass2gain=0
pass2e=1
;enable or disable dsp (saves cpu)

;system settings
freq=48000
;your sound device sample rate
buffer=50
;buffer size. affects latency, sound quality and cpu usage.
~~~~~~~~
