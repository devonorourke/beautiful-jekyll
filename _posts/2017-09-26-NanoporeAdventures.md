---
layout: post
title:  "Nanopore Adventures"
date:   2017-09-27
categories: posts
author: devonorourke
tags: 'classroom'
---

 # Overview
So you've decided you want to use a Nanopore device? Maybe you geeked out when you first saw [this video](https://nanoporetech.com/how-it-works) describing how it works. Maybe your mind was blown when folks started [posting announcements](http://lab.loman.net/2017/03/09/ultrareads-for-nanopore/) about how they could get nearly an entire bacterial genome with aboug 4x coverage using the same number of reads than there are words in this sentence (hint: there are a just 43). Whatever your source of inspiration (or need), long read sequencing was critical for one of my projects so I dove in with both feet. Unfortunately I found the process a little less straightforward than Illumina largely because it's such a newer platform. This guide was put together to help myself keep track of the things I went through in starting from scratch, having never ordered the product, used the product, or analyzed the products products. In creating this in September 2017, I'm not sure how long any of this will remain helpful, but hopefully you can find something in here that is useful.  


 # Getting started
## What to buy?
While my experience in using Nanopore is to generate long sequence reads of DNA, Nanopore has myriad applications for DNA, RNA, and protein (and blobs) - see an [extended review/sales pitch here](https://www.youtube.com/watch?v=7pIpf-jj-7w). Keep this in mind with any of the info below, as my guide reflects the needs and nature of my project which invovled sequencing a single large mammalian genome from just one individual. Maybe you're doing something with a [huge ocean fish](https://blog.nature.org/science/2014/04/02/mola-mola-the-weirdest-fish-in-the-ocean/) or our [national mammal](https://www.doi.gov/blog/15-facts-about-our-national-mammal-american-bison), or some other tautonym. Whatever you're project, you probably want to begin by answering the following questions:
1. What Nanopore device am I going to use (I bought a MinIon)?
2. What sequencing kit was appropriate for my study (I'm ultimately siding with a 1d^2 kit)
3. Which starter back should I buy?  

Let's tackle each of those in order:  
1. PromethIon, GridIon, or MinIon - [which device](https://store.nanoporetech.com/devices.html)? Depends on who you are and what your throughput needs are. And budget. You can get started with a MinIon for a little over $1,000; you can get started with GridIon for about $50,000; PromethIon is more - you get the idea. Most of us will end up with a MinIon and hope that we make friends with a sequencing center willing to buy one of the bigger Grid/PromethIon setups. Note for you early adopters there is also a [SmidgIon](https://nanoporetech.com/products/smidgion) in development, but that's not currently available to everyone.  

 2. There are many [sequencing kits](https://store.nanoporetech.com/kits-208.html) for the various types of projects you might be interested in completing. Some questions to consider here:
- Input material DNA or RNA? 
- Are you Multiplexing? 
- Do you want long reads (> 10kb) or *ultra long* reads (>100 kb)... note those definitions are not precise?
- How much starting material do you have (aka. will you need PCR to amplify your signal or not)?  

For my purposes, I will be using DNA as my input, will *not* be multiplexing, and have lots (micrograms) of DNA. So the only question came down to read length. The choice came down to either the [Rapid kit](https://store.nanoporetech.com/catalog/product/view/id/188/s/rapid-sequencing-kit/category/28/) or the [1d^2 kit](https://store.nanoporetech.com/catalog/product/view/id/175/s/1d-2-sequencing-kit/category/28/). A couple of key differences in features: the Rapid kit requires less input DNA and libraries can be built in as little as 10 minutes; the 1d^2 kit requires more DNA, libraries are trickier and take longer... so why use the 1d^2? Error and read length. The rapid kit will work for long reads, and generally has an accuracy in base calling around 90-95%. The 1d^2 kit allows for *ultra long* reads to be selected and provides base calling accuracy upwards of 99%. Because my first project's goal was to close a genome, longer and more accurate reads were of greatest value, so the 1d^2 was the winner.  

3. Let's assume you're going with a MinIon. Your starter pack (be it [DNA](https://store.nanoporetech.com/minion/sets) or [RNA](https://store.nanoporetech.com/minion/rna/sets)) purchase is really the first decision which takes some financial consideration. While the MinIon device is a captial cost, the flow cells and sequencing prep kits are consumables, and if you remember nothing else from this post remember this: **you can only purchase a starter pack once, and the cost per flow cell is the cheapest when purchasing these starter packs**. In other words, you need to think about how many flow cells and sequencing kits you're likely going to need, and that should help guide which size starter pack you want. For example, if you have a genome that is in the range of 100 Mb, and you want something like 50x coverage, well congrats, you only need a couple of flow cells - buy the Basic MinIon starter pack and you're ready to roll. But what if you're like me and have a 2 Gb sized genome? Throughput varies by experience and by kit type, but let's assume you're a pipette wizard and can crank out 10 Gb per flow cell: 2 Gb genome * 50 x coverage * (flow cell / 10 Gb output) = 10 flow cells! So consider the three Starter Pack routes:  

  
A) **Basic**. If buy the Basic starter pack with 2 flow cells, you're 8 short. If you need just 8 flow cells you can [buy them individually](https://store.nanoporetech.com/flowcells.html) for $900, or an additional $7200. You're going to need a sequencing kit for every 3 flow cells, so with that Basic kit you're only getting 1 sequencing kit, so you're probably 3 short, and will need to [buy them](https://store.nanoporetech.com/catalog/product/view/id/175/s/1d-2-sequencing-kit/category/28/) individually at $600 each for a total of $1800. So with the Basic starter pack you're going to end up with a total cost of $1100 (Starter pack) + $7800 + $1800 = $10,700.  

B) **Enhanced**. You're still getting just 1 MinIon, but you get 4 flow cells and 2 sequencing kits. That puts you 6 flow cells short ($5400) and 2 sequencing kits ($1200). But combined, it's going to cost you $5000 + $5400 + $1200 = $11,600. So strangely, this is more expensive then the Basic option, but you do get 8 weeks of enhanced support. I guess this is a good route if you have no one else to ask question to and think that value is worth $900.  

C) **Development**. You get **2 MinIons** this way. And 16 flow cells. And 4 sequencing kits. But now we're talking about something that is $15,700, or about $5000 more than the Basic starter pack route. The question then becomes are you likely going to want to run more than one MinIon at a time? Each MinIon can only run one flow cell. Each flow cell can run for up to 48 hours. If you're running 10 flow cells for your project, do you want to wait 480 hours, or 240 hours? ... Is that worth $5000? You're also getting 6 more flow cells, which at their most expensive price point would indicate that you've just recouped that extra five grand...  


Take home message: there isn't a clear winner, but the cheapest option isn't necessarily the best, or worst. 

 ## How to buy it?
- we don't have a VAT tax. just click 'no' and 'no.

## Instant support
- chat room support
- community forum resources
- community non-forum resources (Loman, Twitter)

## Things that no one told me
- 10 days or less with flowcell test
 
# Installations
The good news - you can find all three of the major pieces of software required to complete your sequencing run in one place!  
The bad news - if you're not doing this from the command line (and say, for example, you're a Mac user), then you're going to install two of three pieces of software with the disk image file setup you're used to. But that third piece isn't normal...  

Step 1: install all three pieces of software: MinKnow, Epi2ME, Albacore. 
aFirst question - why do you need three pieces of software? Actually you don't! - you only need **MinKnow** for the most basic one-sample, one-run kind of sequencing experiment. As [mentioned here](https://community.nanoporetech.com/protocols/rapid-sequencing-sqk-rad003/v/rse_9040_v1_revb_04jul2017/computer-requirements-and-software-downloads), **MinKnow** software controls the actual MinIon device and performs real-time basecalling, while **EPI2ME** is an optional platform for post-base call analyses (for example, if you barcoded your samples and need to demultiplex), and **Albacore** is an alternative base caller driven by command-line software which lets you integrate real-time data into a more robust pipeline without a GUI.  

-[Click here](https://community.nanoporetech.com/protocols/rapid-sequencing-sqk-rad003/v/rse_9040_v1_revb_04jul2017/computer-requirements-and-software-downloads) to download all three pieces of software appropirate for your system. As a Mac user, you're going to notice that **MinKnow** and **EPI2ME** are familiar disk image file types - just download, click on the icon in your *Downloads* folder, then follow the on-screen install instructions. **Albacore** won't do that. It's a command-line tool, so sensibly you install it with the command line. You won't notice anywhere on that main install page indicating what you're supposed to do with that file or how to install it, but you will find buried in the comments of [this Release Notes](https://community.nanoporetech.com/posts/release-of-albacore-2-01) page that someone has done the good detective work of finding the actual [install instructions here](https://community.nanoporetech.com/protocols/albacore-offline-basecalli/v/abec_2003_v1_revz_29nov2016/linux). I'm going to simplify it for you in two steps here: 
- first, you have to ensure that you have the proper dependencies to run Albacore, which amount to Python3 and pip
 - second, you install Albacore directly with pip. 
Done!
```
## do you have python3 installed?
which python3
  # alternatively, you could be running Python3 as your default version, so you could always just type 'which python'

## do you have pip3 installed?
which pip3
  # as above, if you're default Python is Python3, then just type 'which pip'
  
## assuming you have dependencies installed, download the Albacore program, then install with pip
cd ~/Downloads
wget https://mirror.oxfordnanoportal.com/software/analysis/ont_albacore-2.0.2-cp36-cp36m-macosx_10_11_x86_64.whl
pip3 install ~/Downloads/ont_albacore-2.0.2-cp36-cp36m-macosx_10_11_x86_64.whl 

```

Nanopore has a few pages to running Albacore on [Windows](https://community.nanoporetech.com/protocols/albacore-offline-basecalli/v/abec_2003_v1_revz_29nov2016/run-albacore-on-windows), or [Mac](https://community.nanoporetech.com/protocols/albacore-offline-basecalli/v/abec_2003_v1_revz_29nov2016/run-albacore-on-mac-os-x), or [Linux](https://community.nanoporetech.com/protocols/albacore-offline-basecalli/v/abec_2003_v1_revz_29nov2016/run-albacore-on-linux). For example, if you want to just double check that the install of Albacore was working properly on a Mac you can pull up the help menu from the .py script as follows:
```
read_fast5_basecaller.py --help
```
See **Further Analyses** below for my details on running Albacore.


# Wet bench
- DNA extraction (link to other .md file)
- Library prep
- in case you want to shear your DNA, you could use a syringe [following this protocol](http://www.2einteractive.com/pacbio/Needle-Shearing-DNA-for-PacBio-20kb-Libraries-Sanger.pdf)

# Running MinIon
- testing out of the box
- loading sample
- running considerations
  - Loman start/pause/go vs. just go
- what if you want to change the voltage? see [here](https://community.nanoporetech.com/protocols/experiment-companion-minknow/v/mke_1013_v1_revaf_11apr2016/editing-protocol-scripts)

- washing disaster
  - prime or not?
  - how many times can you wash?
  - when should you wash and when shouldn't you (just load library and no wash)
- what do all the terms on the MinKnow mean - saturate? zero? strand? what do I want?


# About the device
- The layout of the MinIon is [explained in detail here](https://community.nanoporetech.com/technical_documents/hardware/v/hwtd_5000_v1_revh_03may2016/the-minion-mk-i)
