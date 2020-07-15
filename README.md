# .dotfiles  
  
--These are my dotfiles as of now, they will be updated and fixed but here is what ive got right now. This is my first time using a tiling window manager so I am no expert.  
  
https://imgur.com/a/cuYutwL
  
#  Programs  
As of now, the programs I customize in my dotfiles are:  
```  
alacritty - terminal  
dunst - notifications  
i3 - tiling window manager  
lf - terminal based file browser  
picom - compositor  
polybar - status bar  
zsh - shell (with ohmyzsh, and powerlevel10k)  
.Xresources - customize rofi (place in home directory)  
```  
  
# Installation - Easy Way  
The easiest way to use my dotfiles is using stow.  
`git clone https://github.com/ethannij/.dotfiles.git` - to your home folder  
`cd .dotfiles`  
Per each config you would like to copy:  
`stow --adopt -nvSt ~ *programfolder*`  
If the directory exists, delete your current config folder (or move/rename)  
`stow --adopt -vSt ~ *programfolder*`  
   
Example:  
`stow --adopt -nvSt ~ *alacritty*`  
`rm -rf ~/.config/alacritty`  
`stow --adopt -vSt ~ *alacritty*`  
  
I would HIGHLY recommend going one program at a time to ensure nothing goes wrong.  
  
# Installation - Hard Way  
The hard way, is to manually move each config folder into your desired directory, all but ".zshrc" and ".Xresources" go into the .config folder.  
  
# Scripts  
Unzip the "scripts.zip" and place them in your home directory.  
You should edit each script to ensure they are compatible with you (not me).  
Make sure they are executable  
  
What do they do?  
  
hide polybar when fullscreen  
tile in a spiral pattern  
`autoscript $NAME` creates an executable .sh script in the scrips directory  
updates pacman and removes orphaned packages from polybar  
connects to ssh server from polybar  
open timeshift from polybar  
  
# Configuration  
Within the `~/.config/i3/config`, you should change the feh path, to match your wallpaper.  
Within the `~/.config/polybar/config`, add and remove modules if you would like. the font "font-awesome" is required to use the icons at the top of the screen.  
If you experience lag, picom is most likely responisible. Commenting out  
```
blur:
{
  method = "gaussian";
  size = 50;
  deviation = 20;
};
```  
usually fixes this problem.  
By default, the i3 mod key is alt.  
The power menu is an internal module of polybar, however, I have not gotten it to work for myself (good luck).  
If you have any questions, DM me on twitter @ethannij.  
