# atomic-saigon &nbsp; [![build-ublue](https://github.com/blue-build/template/actions/workflows/build.yml/badge.svg)](https://github.com/blue-build/template/actions/workflows/build.yml)

This is the setup of my customized ublue images, using the BlueBuild toolkit, based on Fedora 40.

For more information i refer to their website at https://universal-blue.org/. You can find a large number of other specific images there as well.

A specific part of their toolkit is the Tinkerers Guide to building your own images. That has now been spun-off to BlueBuild at https://blue-build.org/. 

It's a work in progress, but as they mention it is 'the easiest way to build your own desktop Linux images'.

## Current image

Since it is so easy to rebase I will be making some recipe's per DE. In the config directory of this repo you will find additional yaml files, that i rename to recipe.yml and then rebase to. You can look through them for my specific adaptations.

N.B ! If you rebase to my image (without cloning) you will currently find yourself in:

- 7th of November 2024: Cosmic DE

The idea of running an alpha on top of ublue-core was irresistible. That's what all this was originally made for. 

Be aware that this (with some very minor adaptations) is the Cosmic 'basic' spin; Ublue also has versions of Cosmic on top of Silverblue and Kinoite available.
  
## Idea

In 2022 I already made a number of adapted images, but that got shelved and discontinued by me after some time.

Now, with the availability of KDE Plasma 6, it was time to revive it and remake that custom image. 

These images will deliver an atomic desktop, with all Ublue tooling and tweaks included, but with the visible applications brought back to a bare minimum, as I like it.


## What's in & What's out

All tooling added by the Ublue project remains pristine. Suffice to say I don't run the DX (developers) or Nvidia images here; it is the 'standard' version of their and Fedora's images that I'm adjusting here.

This means software like distrobox, fzf, firewalld, vim and htop has already been included in the base image.

An extensive job has been done in the last years to make most other applications available through a flatpak as well. So, no need to include a lot in the images. 

I've only included some applications per DE that I use and that have not (yet) been flatpak'ed, plus some cli tools that i use. Can't live without my Midnight Commander!

One flatpak is installed ootb; Zen browser is included. I suggest you look at the individual recipes to see what I left out for that specific DE or WM.

With regards to flatpaks: I suggest to use the verified versions. That 'proves' the application you are installing has been provided by the official publisher. More and more applications are reaching that status.


      What has been added:            What has been removed:          
      - fastfetch                     - kcharselect
      - kde-print-manager             - kde-connect
      - krusader                      - kde-connect-libs
      - eza                           - kdeconnectd
      - mc                            - kfind
      - micro                         - kmousetool
      - zsh (incl. completions)       - krfb, krfb-libs
                                      - nvtop
                                      - plasma-discover-notifier
                                      - plasma-welcome
     
                                  
   
 
## How do you get it?

Start with any Fedora Atomic image and install it. Then follow these instructions:

Rebase to the unsigned variant of the base image by running the following commands:

      rpm-ostree rebase ostree-unverified-registry:ghcr.io/thesaigoneer/atomic-saigon:latest

* Reboot: systemctl reboot

Rebase to the signed variant of the image: 

      rpm-ostree rebase ostree-image-signed:docker://ghcr.io/thesaigoneer/atomic-saigon:latest

* Reboot: systemctl reboot

Login to your new Atomic from Saigon!

## WIP

* This is a work-in-progress, so expect some changes over time (although nothing fundamental). 
      
* At a certain moment i'd like to get rid of Discover altogether, but for now I've just disabled the nagging notifier

                         
## Current Quirks:

None

## Nota bene

Feel free to use these builds and dots. I do not, however, offer or imply any form of support or ongoing maintenance. 

And of course, you use them entirely at your own risk. 

Have fun!
