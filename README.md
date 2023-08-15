#+TITLE: watermelonos-core-repo
#+DESCRIPTION: A repository of software for watermelonOS.
#+AUTHOR: Stormx920 (Tyrone Watermelon)

* About dtos-core-repo
#+CAPTION: dtos-core-repo
#+ATTR_HTML: :alt dtos-core-repo :title dtos-core-repo :align left
[[https://gitlab.com/dwt1/dotfiles/raw/master/.screenshots/dotfiles04-thumb.png]]

dtos-core-repo is a repository of Arch Linux packages that was created primarily for DTOS, which is still a work-in-progress and not a real thing yet.

=WARNING:= This repo is not meant for public use yet.  The only reason this repo is public is because it has to be public for me to test it out.

* How to "install" dtos-core-repo

You can add dtos-core-repo to any Arch-based Linux distribution.  Just add the following lines to the end of /etc/pacman.conf:

#+begin_example
[dtos-core-repo]
SigLevel = Required DatabaseOptional
Server = https://gitlab.com/dtos/$repo/-/raw/main/$arch
#+end_example

Then, sync the repositories and update your system with:
#+begin_example
sudo pacman -Syyu
#+end_example

And, then:
#+begin_example
sudo pacman -S name-of-package
#+end_example

=NOTE:= Pacman will complain about importing a PGP key that is either invalid or corrupted.  The problem can be fixed by locally signing the imported key:
#+begin_example
sudo pacman-key --lsign-key C71486C31555B12E
#+end_example

* Important information about Suckless programs
** Suckless software
There are several Suckless programs (or programs Suckless in spirit) in this repo, including:
+ dmenu-distrotube
+ dwm-distrotube
+ dwmblocks-distrotube
+ st-distrotube

** Where are the Suckless config files?
Suckless programs are configured by editing the source code and recompiling.  The packages installed from this repo are binary installations, but they do place the source code on your system.  The source code is placed in /opt.  For example, the source code for dwm-distrotube is located at /opt/dwm-distrotube.
