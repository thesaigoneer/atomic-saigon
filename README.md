# atomic-saigon &nbsp; [![build-ublue](https://github.com/blue-build/template/actions/workflows/build.yml/badge.svg)](https://github.com/blue-build/template/actions/workflows/build.yml)

This is the setup of my customized ublue images, using the BlueBuild toolkit, based on Fedora 40.
For more information i refer to their website at https://universal-blue.org/. You can find a large number of other specific images there as well.
A specific part of their toolkit is the Tinkerers Guide to building your own images. That has now been spun-off to BlueBuild at https://blue-build.org/. 

It's a work in progress, but as they mention it is 'the easiest way to build your own desktop Linux images'.

## Current image

Since it is so easy to rebase I will be making some recipe's per DE. In the config directory of this repo you will find additional yaml files, that i rename to recipe.yml and then rebase to. You can look through them for my specific adaptations.
N.B ! If you rebase to my image (without cloning) you will currently find yourself in:

- 15th of November 2024: nwg-shell on hyprland

Many thanks to https://github.com/kuba3351 for enabling all this on Copr and of course to https://github.com/nwg-piotr, the maker of nwg-shell. Read more here: https://github.com/nwg-piotr/nwg-shell/wiki
  
## Idea

In 2022 I already made a number of adapted images, but that got shelved and discontinued by me after some time.
These images will deliver an atomic desktop, with all Ublue tooling and tweaks included, but with the visible applications brought back to a bare minimum, as I like it.

## What's in & What's out

All tooling added by the Ublue project remains pristine. Suffice to say I don't run the DX (developers) or Nvidia images here; it is the 'standard' version of their and Fedora's images that I'm adjusting here.

This means software like distrobox, fzf, firewalld, vim and htop has already been included in the base image. I have only included fastfetch and zsh ootb and removed a ton of fonts and Firefox (which surprisingly enough is installed from the repo's).
All other required/desired software can be installed through flatpak and/or distrobox. In this Ucore based image Homebrew is not installed.
With regards to flatpaks: I suggest to use the verified versions. That 'proves' the application you are installing has been provided by the official publisher. More and more applications are reaching that status.


      What has been added:            What has been removed:          
      - hyprland                       - firefox
      - nwg-shell                      - nvtop
      - fastfetch                      - various fonts and themes        
      - mc, micro, rofi
      - zsh (incl. completions)       
                                      
                            
                                    
## How do you get it?

Start with any Fedora Atomic image and install it. Then follow these instructions:
Rebase to the unsigned variant of the base image by running the following commands:

      rpm-ostree rebase ostree-unverified-registry:ghcr.io/thesaigoneer/atomic-saigon:latest

* Reboot: systemctl reboot

Rebase to the signed variant of the image: 

      rpm-ostree rebase ostree-image-signed:docker://ghcr.io/thesaigoneer/atomic-saigon:latest

* Reboot: systemctl reboot

Login to your new Atomic from Saigon!

##  Additional steps for nwg-shell:

    Press Super + M to open the Kitty terminal (part of the Hyprland package)
    Type: nwg-shell-installer -a -hypr  and press Enter
    Press Super + Q to exit Hyprland 
    Re-login into nwg-shell and start making your own adaptations
                    
## Current Quirks:

None

## Nota bene

Feel free to use these builds and dots. I do not, however, offer or imply any form of support or ongoing maintenance. 
And of course, you use them entirely at your own risk. 

Have fun!
