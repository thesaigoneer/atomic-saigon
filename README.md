# Atomic-KDE-Saigon &nbsp; [![build-ublue](https://github.com/blue-build/template/actions/workflows/build.yml/badge.svg)](https://github.com/blue-build/template/actions/workflows/build.yml)

This the setup for my customized Ublue-Kinoite image, using the BlueBuild toolkit.

## Idea

Eventhough the Ublue project creates outstanding tooling, there is always something to wish for. 
In 2022 I already made a number of adapted images, but that got shelved and discontinued by me after some time.

Now, with the availability of KDE Plasma 6, it is time to revive it and remake that slimmed down image.

Stay tuned!

## What's in & What's out

All tooling added by the Ublue project remains pristine. Suffice to say I don't run the DX (developers) or Nvidia images here; it is the 'standard' version of their (and Fedora's!) Kinoite image that I'm adjusting here.
For more information i refer to their website at https://universal-blue.org/. You can find a large number of other specific images there as well.

A specific part of their toolkit is the Tinkerers Guide to building your own images. That has now been spun-off to BlueBuild at https://blue-build.org/. It's a work in progress, but as they mention it is 'the easiest way to build your own desktop Linux images'.
Since I already build some images and played around with the fundamentals, it was pretty easy for me to pick up again.

      What has been added:                        What has been removed:      
      
      - kde-print-manager                             - firefox
      - krusader                                      - firefox-langpacks
      - lsd                                           - kcharselect
      - mc                                            - kfind
      - micro                                         - kde-connect
      - neofetch                                      - kde-connect-libs
                                                      - kdeconnectd
                                                      - kmousetool
                                                      - krfb
                                                      - krfb-libs
                                                      - nvtop
                                                      - plasma-discover-notifier
                                                      - plasma-welcome
      
       The rpm of Firefox has been removed; a flatpak of Floorp has been added so the user 
       at least has a browser available out of the box.     
      
## How do you get it?

Start with any Fedora Atomic image and install it. Then follow these instructions:

. Rebase to the unsigned variant of the base image by running the following commands:

rpm-ostree rebase ostree-unverified-registry:ghcr.io/thesaigoneer/atomic-saigon:latest

Reboot:

systemctl reboot

Rebase to the signed variant of the image: 

rpm-ostree rebase ostree-image-signed:docker://ghcr.io/thesaigoneer/atomic-saigon:latest

Reboot:

systemctl reboot


## WIP

* This is a work-in-progress, so expect some changes over time (although nothing fundamental). 
      
* At a certain moment i'd like to get rid of Discover altogether, but for now I've just disabled the nagging notifier
                         
## Current Quirks:


## Nota bene

Feel free to use these builds and dots. I do not, however, offer or imply any form of support or ongoing maintenance. And of course, you use them entirely at your own risk. Have fun!
