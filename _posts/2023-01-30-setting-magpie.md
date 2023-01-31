---
title: 'Installing MAgPIE in local environment'
date: 2023-01-30
permalink: /posts/2019/06/combining-pdfs/
excerpt_separator: <!--more-->
toc: true
tags:
  - magpie
---

The Model of Agricultural Production and its Impact on the Environment (MAgPIE) is a modular open source framework for modeling global land-systems, which is helpful for many researchers. I use Podman & conda to successfully install it on a local environment in an MacOS M2 chip.

# Clone the github repository to computer

```bash
git clone https://github.com/magpiemodel/magpie.git magpie
```

# Use the dockfile

It is possible to use the defualt dockerfile to install it, however, it may be slow because of incomptiable systems. I tested and tailored the dockerfile to allow it to install using conda package manager, which is faster and easier to use.

Change the dockerfile to
```
FROM --platform=linux/x86_64 continuumio/miniconda3

# set the proxy, if needed
ENV HTTP_PROXY="http://192.168.2.104:7890"
ENV HTTPS_PROXY="http://192.168.2.104:7890"

RUN apt-get update --fix-missing \
 && apt-get upgrade -y --fix-missing \
 && apt-get install -y vim

RUN mkdir /home/magpie
COPY . /home/magpie/

COPY .condarc /root/.condarc

RUN conda clean -i

RUN conda install r-base r-ncdf4 r-raster r-tidyverse r-curl r-yaml r-cli r-rlang r-lifecycle r-stringi r-plyr r-stringr r-reshape2 r-jsonlite r-data.table r-ps r-processx r-fs r-igraph r-renv r-callr r-promises r-httpuv r-fontawesome r-gridExtra r-plotly r-shiny r-writexl r-lintr r-systemfonts r-openssl r-gert r-usethis r-devtools r-RcppEigen r-checkmate r-survival r-cluster r-rpart r-lpSolve r-interp r-geometry r-pander r-foreign r-maps r-KernSmooth r-viridis

# Set GAMS version
ENV LATEST=40.2.0
ENV LATEST_SHORT=40.2
ENV GAMS_VERSION=${LATEST}

# Set GAMS bit architecture, either 'x64_64' or 'x86_32'
ENV GAMS_BIT_ARC=x64_64


# Download GAMS
RUN curl -SL "https://d37drm4t2jghv5.cloudfront.net/distributions/${LATEST}/linux/linux_${GAMS_BIT_ARC}_sfx.exe" --create-dirs -o /opt/gams/gams.exe

# Install GAMS
RUN cd /opt/gams &&\
    chmod +x gams.exe; sync &&\
    cp /home/magpie/gamslice.txt . &&\
    ./gams.exe &&\
    rm -rf gams.exe

COPY gamslice.txt /opt/gams/gams${LATEST_SHORT}_linux_${GAMS_BIT_ARC}_sfx/gamslice.txt
# Add GAMS path to user env path
RUN GAMS_PATH=$(dirname $(find / -name gams -type f -executable -print)) &&\
    ln -s $GAMS_PATH /usr/local/bin &&\
    echo "export PATH=\$PATH:$GAMS_PATH" >> ~/.bashrc &&\
    echo "export GAMS_PATH=$GAMS_PATH" >> ~/.bashrc &&\
    cd $GAMS_PATH &&\
    ./gamsinst -a

RUN R -e "options(repos = \
  list(CRAN = 'https://cran.rstudio.com/',pik='https://rse.pik-potsdam.de/r/packages'),timeout=1e100); \
  install.packages(c('gdxrrw', \
           'citation', \
           'gdx', \
           'gms', \
           'magclass', \
           'madrat', \
           'mip', \
           'lucode2', \
           'magpie4', \
           'goxygen')"
```

# Install and set up podman

Podman is an alternative to docker. You may check the document here.

After installing podman, set the proxy

```bash
export http_proxy='http://192.168.2.104:7890'
export http_proxys='http://192.168.2.104:7890'
```

change the default number of CPU and size of memory
```bash
podman machine init --cpus 2 --memory 4096
```

# Install mapgie and related packages

```
sudo podman build -t magpie .
podman exec -it magpie /bin/bash
```
