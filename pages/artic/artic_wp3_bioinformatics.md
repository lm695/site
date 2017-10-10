---
title: "Work Package 3: Bioinformatics"
keywords: about
last_updated: October 5, 2017
tags: [wp3]
summary:
sidebar: artic_sidebar
permalink: wp3-bioinformatics.html
toc: false
folder: artic
---

## Offline bioinformatics methods for sequencing analysis

The overarching aim is to develop robust sequencing pipelines that can be reliably used by non- expert users in a field situation. During the EVD epidemic, the transfer of raw data from NGS installations to computing clusters for processing and assembly was impractical due slow Internet connections. Therefore, we will develop an offline bioinformatics software package for deployment on laptop computers adjacent to sequencing instruments, building on existing pipelines developed by Loman for Zika sequencing in Brazil and a recently released open source basecalling software from ONT. Analysis will begin with real-time base-calling and continue with offline genome assembly and variant calling and genome annotation. We will investigate the use of low power, high-core-count GPU acceleration boards (e.g. NVIDIA Jetson TX1) to offload basecalling. Software will be aware of standardised positive and negative control samples and spike-ins from WP1 to rapidly flag up problematic samples that may need repeating.

## Centralised data processing and virus database.

Assembled genomes, the iSNV frequencies from WP2.ii and associated, de-identified, metadata will be uploaded to the analysis platform described in WP4. These data are orders of magnitude smaller than the raw NGS data and readily transferable through low-bandwidth data connections. The raw data will be kept in case further processing is needed and can be transferred for archiving on the NCBI Sequence Read Archive on a less urgent timescale. We will host a database that collates viral genome data and associated metadata for each sample. The field bioinformatics pipeline will push assembled genomes to this central database. Reception of data to the platform will involve a series of further quality control steps by comparison to existing data. This will include comparison to existing genomes to annotate potential cases of recombination (whether in vivo or mosaics generated in the sequencing process), hypermutation due to host enzymes such as ADAR[5,19,20] or cases where the collection dates conflict with genetic similarity to other viruses indicative of contamination, mislabelling or latent infections[7,21]. Such issues can cause systematic errors in phylodynamic analysis and interpretation.

### Presentations

{% include presentations.html %}

{% include links.html %}
