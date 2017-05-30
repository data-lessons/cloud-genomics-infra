# Software installation instructions
Start with Ubuntu 16.04 LTS

## create directory for binary files in home directory
```sh
mkdir ~/bin
chmod -R +x ~/bin
```

## various software dependencies
```sh
sudo aptitude install tmux
sudo aptitude install curl

# java
sudo aptitude install default-jre
```
## install ngs tools

### FastQC
```sh
cd ~/Downloads
wget http://www.bioinformatics.babraham.ac.uk/projects/fastqc/fastqc_v0.11.5.zip
unzip fastqc_v0.11.5.zip
```
### trimmomatic
```sh
sudo aptitude install trimmomatic
```

### samtools
```sh
cd ~/Downloads
wget https://github.com/samtools/samtools/releases/download/1.4.1/samtools-1.4.1.tar.bz2
tar xvf samtools
./configure
make
sudo make install
```

### bcftools
```sh
wget https://github.com/samtools/bcftools/releases/download/1.4.1/bcftools-1.4.1.tar.bz2
make
sudo make install
```

### BWA
BWA available from the Ubuntu repositories is relatively old. Download and
install the package manually.
```
# zlib.h is necessary to compile bwasudo aptitude install zlib1g-dev
wget https://github.com/lh3/bwa/releases/download/v0.7.15/bwa-0.7.15.tar.bz2
tar xvf bwa-0.7.15.tar.bz2
cd bwa-0.7.15
make
cp bwa ~/bin/
```

## R and RStudio RStudio server
R available from the Ubuntu repositories is relatively old. It is recommended to
install one from CRAN.
```sh
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys E298A3A825C0D65DFD57CBB651716619E084DAB9
sudo add-apt-repository 'deb [arch=amd64,i386] https://cran.rstudio.com/bin/linux/ubuntu xenial/'
sudo apt-get update
sudo apt-get install r-base
```

Install RStudio server
```sh
sudo apt-get install gdebi-core
wget https://download2.rstudio.org/rstudio-server-1.0.143-amd64.deb
sudo gdebi rstudio-server-1.0.143-amd64.deb
```
