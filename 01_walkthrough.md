---
layout: page
title: Openstack
order: 1
---
# Using OpenStack

To complete this workshop we will be using a BIO3092-2020 instance on the University of Exeter's OpenStack. If you have already created an instance as part of another BIO3092 workshop you should log into that instance now and  move onto the workshop [introduction](https://uoe-bio3092.github.io/rna-seq/02_introduction.html). If for any reason you have not created an instance or need to create another see the instructions below.

## Creating an instance on Openstack

A video tutorial to connect to OpenStack and launching an instance is [here](https://youtu.be/JIoFJBWTtlg)

### Log on details

To log into [OpenStack](https://openstack.exeter.ac.uk/dashboard/auth/login/?next=/dashboard/) you will need the following credentials. Please note that you will not be able to access OpenStack or your instance from off campus. If you need off campus access you will need to use a [VPN](http://www.exeter.ac.uk/it/howdoi/vpn/).

* Domain: default
* User name: hubtraining_student
* Password: yTpEMUJsfD7z


### Openstack instance

To successfully create an instance you will need to select the following options. Please name your instance something that you will remember - including your name or university ID is a good idea. Then follow the instructions using the following options:

* Boot source: _Instance Snapshot_
* Name: BIO3092-2020
* Flavour: _u1.xxlarge_

Once the instance has started remember to take note of the IP address (use Edit-Copy).

## Log onto your instance

A video tutorial to connect to your virtual machine using Terminal (mac) or MobaXterm (windows) is [here](https://youtu.be/qPPBjTSppvE)

The log in details are:
* User name: ubuntu
* Password: bio3092

Once you have successfully logged on, its time to begin the workshop!

# Using your own machine

It is strongly recommended that you use the Virtual Machine approach to complete this workshop described above. However, it will also be possible to use your own machine.

To successfully use your own machine you will need to:
* Download the workshop data
* Install all required software

Please ensure all data is downloaded and software is installed and working before our workshop session.

## Downloading workshop data

A substantial amount of raw data is required (a few GB) for this workshop. The easiest way to download these data is from the virtual machine. Follow the instructions above to setup an instance of the BIO3092-2020 virtual machine. Once you have started an instance and have an IP address use `scp` (or another transfer program) to download the data to your local machine. The data is stored at `/home/ubuntu/resources/workshops/ws4-differential-expression/` on the virtual machine. An example command (Linux or Mac Terminal) to download these data would be:

```
scp -r ubuntu@<ip-address>:/home/ubuntu/resources/workshops/ws4-differential-expression ./
```

enter the relevant password when prompted and the command will download the workshop data to the current directory on your local machine. This directory will then become your working directory for the workshop.

The command should result in a directory structure that looks like:

* ws4-differential-expression/
  * fastq/
  * alignments/
  * DE/
  * GO/
  * C.gattii_ref/

with the `fastq/`, `alignments/` and `C.gattii_ref/` directories containing some input files you will use throughout the workshop.

## Required software

We will run the whole workshop in [R](https://www.r-project.org/). I recommend using an Integrated Development Environment (IDE) such as [RStudio](https://rstudio.com/), which has a lot of useful features such as package installation, script editor and panes for visualisation of the environment and images.

To complete the workshop you will need to install several packages:
* [Rsubread](https://bioconductor.org/packages/release/bioc/html/Rsubread.html) for alignment and counting
* [edgeR](https://bioconductor.org/packages/release/bioc/html/edgeR.html) for differential gene expression analysis
* [GOfuncR](https://www.bioconductor.org/packages/release/bioc/html/GOfuncR.html) for Gene Ontology enrichment

Follow the instructions on the above pages to install the packages.
