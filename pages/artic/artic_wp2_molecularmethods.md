---
title: "Work Package 2: Molecular Methods for Sequencing"
keywords: about
last_updated: October 5, 2017
tags: [wp2]
summary:
sidebar: artic_sidebar
permalink: wp2-sequencing.html
toc: false
folder: artic
---

## Development and testing of pathogen panels for reliably sequencing relevant acute viral pathogens, even at low titre

Recent work has demonstrated the difficulty in sequencing Zika virus directly from clinical samples. Direct sequencing and bait approaches often yield poor results on acute clinical samples. For Zika, this has necessitated the development of highly sensitive multiplex PCR assays to sequence Zika virus even at exceptionally low viral counts (viral copy numbers of <50/ml).

We will adapt our <a href="https://primal.zibraproject.org">Primal Scheme</a> method to develop pathogen multiplex PCR panel assays, focusing on a wide range of acute viruses, including all those on the WHO emerging infectious disease R&D priority list.

<img src="/images/">

We will validate these panels against test material to evaluate sensitivity at different viral copy numbers.

Samples willl be analysed in collaboration with Public Health England’s Rare and Imported Pathogens Laboratory, and the Sierra Leone PHE-MOHS Ebola Biobank.

We will compare these panels for sensitivity and specificity against other methods including total nucleic acid sequencing (metagenomics) and bait capture approaches such as VirCapSeq-VERT. For further sensitivity, physical viral capture methods have been developed over recent years that rely on viruses binding to immobilised ligands (e.g. HBGA and lectins) or immobilised pathogen-specific antisera. The ability to enrich biological samples, removing large particles as well as free nucleic acids and subsequently concentrating viral particles prior to nucleic acid extraction, will be explored ensure compatibility with the workflow established as part of <a href="/wp1-fieldlab.html">Work Package 1</a>.

## Serial copy method for very high accuracy single molecular reads

We have developed methods to robustly identify consensus genotypes using noisy single molecule data alone. Lower frequency, intra-host single nucleotide variants (iSNVs) occurring at lower frequency may enhance our ability to reconstruct chains of transmission by increasing the information in a single clinical sample (see <a href="/wp4-phylogenetics.html">Work Package 4</a>). However, sequencing and PCR errors may confound such methods, particularly single molecule sequences with high intrinsic error rate (~5% for ONT).

We have been evaluating a novel serial copy tandem repeat method, developed for nanopore sequencing, that is able to reconstruct individual single molecule sequences with very high accuracy.

This approach is conceptually similar to unique molecule tagging or CirSeq.

This method involves ligating a hairpin to individual molecules, and using a proofreading strand- displacement polymerase to copy it. This process is repeated to make around 20 copies of the starting molecule in a single long template, sufficient for accurate SNV detection on a single molecule basis. The ability to link variants into haplotypes by varying the amplicon length will be explored. This template is read in its entirety using nanopore sequencing which does not require fragmentation, before a consensus sequence is generated from the average of each copy. We will adapt this for compatibility with WP2.i for sequencing viral pathogens in the field.

## Reduce complexity of nanopore library preparation workflow

The MinION two-direction library preparation is currently laborious and takes around 2-3 hours to complete with expensive reagents. We have recently explored using the MuA transposome that removes the need for DNA end-repair and A-tailing and means a sequence library can be generated in 10 minutes. This approach generates only “1D” reads, but early experiments suggest these provide accurate variant calling at sufficiently high levels of sequence coverage depth. We will adapt this workflow to amplicons from RT-PCR, using specific sequences as part of a fusion barcode primer, and site-specific transposases to introduce the sequencing adaptor. When available we will adapt this to function on the announced nanofluidic programmable Voltrax, to minimise operator error (see letter of support from ONT). We will also investigate the performance and suitability of direct RNA nanopore (without generation of a cDNA molecule) sequencing directly from clinical samples. Finally we will investigate the ability to generate multiplex PCR products within minutes, by modifying the Extreme PCR protocol[18].

### [Presentations on workpackages are available here](presentations)

{% include links.html %}
