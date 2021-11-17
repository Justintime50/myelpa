# MyELPA (Personal Emacs Package Mirror)

Due to a series of unfortunate events, installing packages doesn't work on my work Emacs instance (Emacs doesn't use openssl, can't build the newest version of Emacs on our OS, etc, etc). 

Here is the collection of `*.el` package files (including dependencies) which can be manually installed into `~/.emacs.d/packages` to get the same effect until that's fixed. If nothing else, this is a manually created mirror of my installed Emacs packages that can be used in the ulikely event of a catostrophic recovery.

## Install

1. Unzip all the tar archives `tar -xf path/to/package.tar`
1. Move all of the `*.el` package files from `src` into `~/.emacs.d/packages` 
1. Require the individual packages in `~/.emacs` such as `(require 'ivy)`

## Usage

Use the following tool to craft the mirror locally (must be done from an Emacs instance that can install packages - as is the case on my personal machine.) https://github.com/redguardtoo/elpa-mirror
