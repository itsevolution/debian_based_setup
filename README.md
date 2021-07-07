# debian_based_setup
This is how I setup my computer for bioinformatics and personal usage.
I really like [Willi Mutschler's guides](https://mutschler.eu/linux/install-guides/)

Current: Pop!_OS 20.04 LTS 5.4.0-7642-generic (NVIDIA)

## bash with [Startship](https://starship.rs/)

then I increase the history size and ignore command duplications
```
export HISTFILESIZE=1000000000
export HISTSIZE=1000000000
setopt HIST_IGNORE_ALL_DUPS
```

## Install Java Development Kit builds
```
sudo apt install default-jre default-jdk

java -version
```

## Install media codecs and addons
```
sudo apt install ubuntu-restricted-extras
sudo apt install ubuntu-restricted-addons
sudo apt install vlc
```

## Intel(R) Graphics Compute Runtime for OpenCL(TM) drivers
```
sudo apt install intel-opencl-icd
```
## NVidia_GTX_1050 driver (for Ubuntu)
```
sudo add-apt-repository ppa:graphics-drivers/ppa
sudo apt update
sudo apt install nvidia-driver-XXX  #current 455.28
sudo reboot
```
if Ubuntu freezes after installation, try the solution of [Mari Linhares](https://gist.github.com/mari-linhares/cef4cb3440408e44963d1447a7db5ae0)

## Install Vim and Sublime
```
sudo apt install vim sublime-text latexmk biber
```

## [Installing R](https://cran.r-project.org/)
```
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
sudo add-apt-repository 'deb https://cloud.r-project.org/bin/linux/ubuntu bionic-cran35/'
sudo apt update
sudo apt install r-base r-base-dev
```

Installing packages and dependencies for genetic analyses on Ubuntu 18.04, recomended by [Grunwald lab](https://grunwaldlab.github.io/)
```
sudo apt install build-essential libcurl4-gnutls-dev libxml2-dev libssl-dev
```

[*units* package - r-quantities](https://github.com/r-quantities/units)
```
sudo apt install libudunits2-dev
```
[*sf* package - r-spatial](https://github.com/r-spatial/sf)
```
sudo add-apt-repository ppa:ubuntugis/ubuntugis-unstable
sudo apt update
sudo apt install libgdal-dev libgeos-dev libproj-dev 

```
Installing packages

Install *devtools* and *bioconductor* packages
```
sudo -i R
install.packages("devtools")
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")
BiocManager::install() #for package installation 
install.packages('units')
install.packages('sf')
# After installing this packages, other dependencies will be installed automatically.
install.packages('adegenet')
require(devtools)
devtools::install_github(repo = "grunwaldlab/poppr", build_vignettes = TRUE)
install_github("dwinter/mmod")
```

Download RStudio (IDE)
```
cd ~/Downloads
sudo gdebi rstudio-XXX.deb
```

## Install packages via Conda

bcftools htslib cutadapt plink vcftools raxml

## Install iPyrad
Follow the instructions at [iPyrad.docs](https://ipyrad.readthedocs.io/en/latest/3-installation.html).

## Install Stacks
Download [Stacks](http://catchenlab.life.illinois.edu/stacks/) and extract.
```
tar xfvz stacks-2.xx.tar.gz
cd stacks-2.xx
./configure
make -j 8 #number of processors available 
sudo make install

```
## Install samtools, bcftools and htslib (following [Biostars](https://www.biostars.org/p/328831/) tutorial)

## Install [VSEARCH](https://github.com/torognes/vsearch)
```
wget https://github.com/torognes/vsearch/archive/vXXXXXXXX.tar.gz
tar xzf vXXXXXXXX.tar.gz
cd vsearch-vXXXXXXXX
./autogen.sh
./configure
make
make install  # as root or sudo make install
```

## Install QGIS

[QGIS LTR for Debian-ubuntu](https://www.qgis.org/en/site/forusers/alldownloads.html#debian-ubuntu)

## Install Zotero reference manager

Download [Zotero](https://www.zotero.org/download/) and extract.

```
sudo mv Zotero_linux-x86_64 /opt
sudo ln -s /opt/Zotero_linux-x86_64/zotero /usr/bin/zotero
sudo add-apt-repository ppa:smathot/cogscinl
sudo apt update 

```
To add Zotero on Applications tab
```
sudo ln -s /opt/Zotero-5.0.76_linux-x86_64/Zotero_linux-x86_64/zotero.desktop /usr/share/applications/zotero.desktop
sudo zotero
```
# to install [qnotero](http://www.cogsci.nl/qnotero)

## Install Tweak tools for  
```
sudo add-apt-repository universe
sudo apt install gnome-tweak-tool
```
## themes
```
apt search arc-theme
sudo apt install arc-theme 
sudo add-apt-repository ppa:papirus/papirus
sudo apt install papirus-icon-theme 
```

# Install Steam from official package
```
sudo dpkg --add-architecture i386
sudo apt update
sudo apt install wget gdebi-core libgl1-mesa-dri:i386 libgl1-mesa-glx:i386
wget http://media.steampowered.com/client/installer/steam.deb
sudo gdebi steam.deb
```

## Install other programs 
spotify, Discord, termdown, cheese etc.. check the list.

