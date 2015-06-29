#![](http://i.imgur.com/msEXHsu.png) dotfiles

## .files
- Replace current dot files with your own (`mv ~/.dotrc ~/dotfiles/dot/. `) or use mine.
- Run `./redot.sh` to symlink
	- If you receive an error running `./redot.sh` run `chmod +x ./redot.sh`

## [Atom](https://atom.io/) 
All of my atom settings are saved in `config.cson`. The `package-install.sh` file will restore these settings as well as all my packages and themes. The file `package-list.txt` is my list of currently installed packages.

#### Backup 
- Run `./backup-packages.sh` while in the `atom/` folder. 
- Both `config.cson` and `package-list.txt` should now be updated with your latest settings.

#### Restore
- Run `./package-install.sh` and it will install all the atom packages and restore settings.

## [Arch Linux](https://www.archlinux.org/) 

My arch installation uses the tool [Yaourt](https://wiki.archlinux.org/index.php/Yaourt) for package management from [AUR](https://aur.archlinux.org/). My script can be easily adapted to support any package manager.

#### Backup
- Run `./backup-arch.sh` to backup your packagelist (using yaourt) and your `pacman.conf` file. (This requires sudo)
	- This will backup your packagelist to the `backups/` folder
	- Only one copy of your packagelist is saved

#### Restore
The restore script will assume you are on a fresh install and haven't even installed yaourt. It will download the tarball from AUR and install it for your.

- Run `./initial-setup.sh` (Thats it!)
	- This requires the `backups/` folder to not be empty and contain a yaourt backup of your packagelist
	- This will download yaourt and save it to the `tmp/` folder, be sure to remove it if you do not wish to have the tarball after the script has finished