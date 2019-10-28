# ubuntu_setup
This is how I setup my computer for bioinformatics and personal usage.

Current: Ubuntu 18.04 4.18.0-25-generic

## Installing Git, Synaptic package manager, htop monitor and Gdebi installation manager
```
sudo apt-get install git
sudo apt install synaptic
sudo apt install gdebi-core
sudo apt install htop
```

## Install media codecs and addons
```
sudo apt install ubuntu-restricted-extras
sudo apt install ubuntu-restricted-addons
sudo apt install vlc
```

## NVidia_GTX_1050 driver
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-XXX  #current 390
```

## Installing R (current 3.6.1)
```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu bionic-cran35/'
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
Installing packages
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

## Install Zotero reference manager

Download [Zotero](https://www.zotero.org/download/) and extract.

```
sudo mv Zotero_linux-x86_64 /opt
sudo ln -s /opt/Zotero_linux-x86_64/zotero /usr/bin/zotero
sudo add-apt-repository ppa:smathot/cogscinl
sudo apt-get update 

```
To add Zotero on Applications tab
```
sudo ln -s /opt/Zotero-5.0.76_linux-x86_64/Zotero_linux-x86_64/zotero.desktop /usr/share/applications/zotero.desktop

```
Open as root
```
sudo zotero
```

## Install QGIS LTR 
```
sudo sh -c 'echo "deb http://qgis.org/ubuntu-ltr bionic main" >> /etc/apt/sources.list'
sudo sh -c 'echo "deb-src http://qgis.org/ubuntu-ltr bionic main" >> /etc/apt/sources.list'

wget -O - https://qgis.org/downloads/qgis-2019.gpg.key | gpg --import
gpg --fingerprint 51F523511C7028C3
gpg --export --armor 51F523511C7028C3 | sudo apt-key add -

sudo apt-get update
sudo apt-get install qgis qgis-plugin-grass

```


## Install Tweak tools for  
```
sudo add-apt-repository universe
sudo apt install gnome-tweak-tool
```
# Install Steam from official package
```
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install wget gdebi-core libgl1-mesa-dri:i386 libgl1-mesa-glx:i386
wget http://media.steampowered.com/client/installer/steam.deb
sudo gdebi steam.deb
```

## Install programs via Snap
> Skype, spotify, whatsapp.desktop, etc.. check the list.

