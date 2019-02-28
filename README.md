# Shell script that sets up pulseaudio to fix problems with Discord, Skype and Spotify
### SOURCE: https://wiki.debian.org/PulseAudio (stuttering audio topic)
### IMPORTANT:
#### DON'T USE SPACES BETWEEN '=' AND A VALUE
#### REMOVE ';' AND '#' OF THE SETTING YOU WANT TO MAKE IT ACTIVE

## Stuttering and audio interruptions
#### If a low-power machine stutters (audio breaks up), you can try adding the
#### following to /etc/pulse/daemon.conf:
high-priority=no
nice-level=-1
realtime-scheduling=yes
realtime-priority=5
flat-volumes=no
resample-method=speex-float-1
default-sample-rate=48000

## Excessive CPU usage and distortion
#### Add a line to /etc/pulse/default.pa
load-module module-udev-detect tsched=0

## Various problems with Skype and Wine
#### Add or uncomment the line in /etc/pulse/daemon.conf
default-fragments=25
default-fragment-size-msec=25
