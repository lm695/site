---
title: EBOV-seqSOP-v1.0.0 Ebola Sequencing, Amplicon, native barcoding
keywords: protocol
last_updated: May 17, 2018
tags: [protocol]
summary:
sidebar: artic_sidebar
permalink: ebov-seq-sop-1.0.0.html
toc: true
folder: artic
---

## Overview:
The following protocol is adapted from the methods of Quick et al. (Nature Protocols volume 12, pages 1261–1276 (2017), [doi:10.1038/nprot.2017.066](http://doi.org/10.1038/nprot.2017.066) and covers primers, amplicon preparation and clean-up, then uses a single-tube protocol to barcode and adaptor ligate the library, before running minION. 

### Equipment required:
2 Portable nucleic acid preparation hood or equivalent

1 12V vortex

1 Sprout® portable centrifuge

1 1mL Eppendorf pipette

1 0.1mL Eppendorf pipette

1 0.01L Eppendorf pipette

1 1.5mL/0.6mL convertible tube rack

1 Qubit 4 Fluorometer (ThermoFisher™)

1 miniPCR machine.

1 Heat block
 
1 magnetic rack

### Consumables required:
 
Vilo SSIV RT 2x MasterMix

Q5 Hotstart HF polymerase 2x Mastermix

Ebola Zaire Primers V1

NEBNext UltraII End-prep module

NEBNext UltraII Ligase module

NEBNext FFPE Repair module

Agencourt AMPureXP Beads

Nanopore Ligation Sequencing Kit 1D

Nanopore Native Barcoding Expansion Kit

Nanopore R9.4.1 Flow cells

1.5mL eppendorf tubes

0.2mL 8-strip tubes

50mL transfer tubes

Qubit Reaction Tubes

Qubit 1x dsDNA HS Assay kit

Nuclease-free water

70% Ethanol

1mL pipette tips

0.1mL pipette tips

0.01mL pipette tips

Paper towelling 

Clinical waste sharps containers

### Safety, containment and contamination recommendations
Back-tie hydrophobic lab gown
Gloves
UV light sterilizers
MediPal Decontamination wipes
DNAway and RNAse Zap® reagent 


## cDNA synthesis with Superscript IV Vilo cDNA kit
**NOTE ON HOOD PREPARATION:** To prevent cross contamination of both the sample and other reagents, this should be carried out in the SAMPLE PREPARATION HOOD, which is pre-sterilised with UV and treated with MediPal wipes, DNAway and RNAseZap reagent. Wipe down the hood with each sequentially, allowing 5 minutes for drying between each. Pipettes should also be treated in the same way, and UV treated for 30 mins between library preparations. 

1. Recommend aliquoting the Vilo mastermix, to prevent cross contamination and to reduce potential freeze/thaw cycles.
2. Set up the following reaction:

   2x Vilo Master Mix	5L
   
   viral RNA		5L
   
   TOTAL			10L
   
3. Gently mix (avoid vortexing) then pulse spin the tube to ensure maximum contact with the thermal cycler.
4. Incubate the reaction as follows:

   Primer annealing	25oC		20 mins
   
   Extension		50oC		30 mins
   
   Inactivation		85oC		10 mins
   
5. cDNA is now ready for amplicon generation.

## Ebola Amplicon Preparation
**NOTE ON HOOD PREPARATION:** To prevent cross contamination of both the sample and other reagents, this should be carried out in the MASTERMIX HOOD, which is pre-sterilised with UV and treated with MediPal wipes, DNAway and RNAseZap reagent. Wipe down the hood with each sequentially, allowing 5 minutes for drying between each. Pipettes should also be treated in the same way, and UV treated for 30 mins between library preparations.

1. Primer dilution and preparation

   1. Ebola primers for this protocol were designed using Primal and generate a 400nt amplicon with a 75nt overlap. Primer names and dilutions are listed in the table below. 
   
   2. Primers should be prepped and aliquoted PRIOR TO DEPARTURE in a STERILE PCR CABINET. At NO stage should primers or PCR reagents be anywhere near the template or amplicons until use. 
   
   3. Generate primer pool stocks by adding 20uL of each primer pair to a 1.5mL Eppendorf labelled “Pool 1, 100M” or “Pool 2, 100M”. Total volume should be 460uL of each pool. This is a 10x stock of each primer pool. 
   
   4. Dilute this primer pool 1:10 in molecular grade water, to generate 10uM primer stocks. Recommend that at least 1mL of each primer pool is taken in 100L aliquots, to account for any risks of degradation of contamination. 
   
   5. Primers need to be used at a final concentration of 0.015M per primer. In this case, each pool has 23 primers in it, so the requirement is 0.8625L of 10M primer pool per 25L reaction.
    
   6. Set up the amplicon PCR reactions as follows:

      |Reagent |POOL 1 |POOL 2 |
      |--------|-------|-------|
      |NEB Q5® Polymerase 2X MasterMix |12.5L |12.5L |
      |Primer Pool 1 or 2 (10uM) |0.9L |0.9L |
      |Water |7.5L |7.5L |
      |TOTAL |25L |25L |
      
      *NOTE:  THIS SHOULD BE CARRIED OUT IN THE MASTERMIX HOOD AND cDNA SHOULD NOT BE TAKEN ANYWHERE NEAR THE MASTERMIX HOOD AT ANY STAGE.



   7. In the TEMPLATE HOOD add 4.1uL of cDNA to each Pool1 and Pool2 reaction mix. 
   
   8. Set up the cycling conditions as follows:
   
      |                |Temperature |Time        |Cycles |
      |----------------|------------|------------|-------| 
      |Heat Activation |98oC        |30 seconds  |1      |
      |Denaturation    |98oC        |15 seconds  |35     |
      |Annealing       |60oC        |30 seconds  |1      |
      |Extension       |72oC        |120 seconds |1      |
      |Hold            |4oC         |Indefinite  |1      |
				
   9. Clean-up the amplicons using the following protocol in the TEMPLATE HOOD:
   
      1. Transfer the entire contents of “Pool1” and “Pool2” to a single 1.5mL Eppendorf tube. 
      
      2.	Mix sample gently, avoid vortexing.
      
      3.	Ensure AmpureXP beads are well resuspended by thoroughly mixing prior to addition to the sample. Mixture should be a homogenous brown colour. 
      
      4.	Add an equal volume of AmpureXP beads to the tube and mix gently. This should be approximately 50uL, so add 50uL of beads.
      
      5.	Incubate for 2 mins at 25oC.
      
      6.	Place on magnetic rack and incubate for 2 mins or until the beads have pelleted against the magnet and the solution is completely clear. 
      
      7.	Carefully remove and discard the solution, being careful not to displace the bead pellet. 
      
      8.	Add 200uL of 70% ethanol to the pellet. 
      
      9.	Remove from magnet and mix by gently flicking the tube. 
      
      10.	Pulse centrifuge the tube to make sure all the mixture is out of the lid following flicking, then place back onto the magnet. 
      
      11.	Incubate for 2 mins or until the beads have pelleted against the magnet and the solution is completely clear. 
      
      12.	Carefully remove and discard ethanol, being careful not to displace the bead pellet.
       
      13.	Repeat steps (h-l) to wash the pellet again. 
      
      14.	Briefly pulse centrifuge the pellet and carefully remove as much ethanol as possible using a 10uL tip. 
      
      15.	Allow the pellet to dry for 2 mins, being careful not to overdry (if the pellet is cracking, then it is too dry).
      
      16.	Resuspend pellet in 30uL of water, and incubate for 2 mins. 
      
      17.	Place on magnet and CAREFULLY remove water and transfer to a clean 1.5mL Eppendorf tube. MAKE SURE that no beads are transferred into this tube. 
      
      18.	Quantify the amplicon library using Qubit4® following the dsDNA protocol.
