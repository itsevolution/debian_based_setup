# ubuntu_setup
Things that I do to prepare my computer for gamming and bioinformatics.

Current: Ubuntu 18.04 4.18.0-25-generic x86_64 

```
sudo apt update
sudo apt upgrade
```

Install Synaptic package manager
```
sudo apt install synaptic
```
Install Gdebi for debian installation manager
```
sudo apt install gdebi-core
```

Install htop monitor
```
sudo apt install htop
```

Install media codecs and addons
```
sudo apt install ubuntu-restricted-extras
sudo apt install ubuntu-restricted-addons
sudo apt install vlc
```

NVidia_GTX_1050
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-XXX  #current 390
```

Installing R 3.6.1
```
sudo apt update
sudo apt install r-base r-base-dev
```

Installing packages and dependencies for genetic analyses on Ubuntu 18.04, recomended by [Grunwald lab](https://grunwaldlab.github.io/)

Install *devtools* and *bioconductor* packages
```
sudo apt install build-essential libcurl4-gnutls-dev libxml2-dev libssl-dev
sudo -i R
> install.packages(*devtools*)
> if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
> BiocManager::install()
```
[*units* package](https://github.com/r-quantities/units)
```
sudo apt-get install libudunits2-dev
```
[*sf* package](https://github.com/r-spatial/sf)
```
sudo add-apt-repository ppa:ubuntugis/ubuntugis-unstable
sudo apt-get update
sudo apt-get install libudunits2-dev libgdal-dev libgeos-dev libproj-dev 
```
```
sudo -i R
> require(devtools)
> install.packages('units')
> install.packages('sf')
# After installing this packages, other dependencies will install automatically.
> install.packages('adegenet')
> install_github(repo = "grunwaldlab/poppr", build_vignettes = TRUE)
> install_github("dwinter/mmod")
```

Download RStudio (IDE)
```
cd ~/Downloads
sudo gdebi rstudio-XXX.deb
```

Install Steam from official package
```
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install wget gdebi-core libgl1-mesa-dri:i386 libgl1-mesa-glx:i386
wget http://media.steampowered.com/client/installer/steam.deb
sudo gdebi steam.deb
```

Install Tweak tools for  
```
sudo add-apt-repository universe
sudo apt install gnome-tweak-tool
```


Install programs via Snap
> Skype, spotify, whatsapp.desktop, etc.. check the list.

