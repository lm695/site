---
title: ARTIC-EBOV-seqSOP-v1.0.0 Ebola Sequencing, Amplicon, native barcoding
keywords: protocol
css: protocol
layout: document
last_updated: May 17, 2018
tags: [protocol]
summary:
sidebar: artic_sidebar
permalink: ebov-seq-sop-1.0.0.html
toc: true
folder: artic
---

# Ebola virus sequencing protocol: amplicon, native barcoding

> Document: ARTIC-EBOV-seqSOP-v1.0.0
> 
> Date: 2018-05-17
>
> Forked from: [doi:10.1038/nprot.2017.066](http://doi.org/10.1038/nprot.2017.066)
>
> Author: Luke Meredith
 
## Overview:
The following protocol is adapted from the methods of [Quick et al. (2017) *Nature Protocols* **12:** 1261–1276 doi:10.1038/nprot.2017.066](http://doi.org/10.1038/nprot.2017.066) and covers primers, amplicon preparation and clean-up, then uses a single-tube protocol to barcode and adaptor ligate the library, before running minION. 

### Equipment required:

   |---:|:---
   |2| Portable nucleic acid preparation hood or equivalent
   |1| 12V vortex
   |1| Sprout® portable centrifuge
   |1| 1mL Eppendorf pipette
   |1| 0.1mL Eppendorf pipette
   |1| 0.01L Eppendorf pipette
   |1| 1.5mL/0.6mL convertible tube rack
   |1| Qubit 4 Fluorometer (ThermoFisher™)
   |1| miniPCR machine.
   |1| Heat block
   |1| magnetic rack

### Consumables required:
 
   |---:|:---
   || Vilo SSIV RT 2x MasterMix
   || Q5 Hotstart HF polymerase 2x Mastermix
   || Ebola Zaire Primers V1
   || NEBNext UltraII End-prep module
   || NEBNext UltraII Ligase module
   || NEBNext FFPE Repair module
   || Agencourt AMPureXP Beads
   || Nanopore Ligation Sequencing Kit 1D
   || Nanopore Native Barcoding Expansion Kit
   || Nanopore R9.4.1 Flow cells
   || 1.5mL eppendorf tubes
   || 0.2mL 8-strip tubes
   || 50mL transfer tubes
   || Qubit Reaction Tubes
   || Qubit 1x dsDNA HS Assay kit
   || Nuclease-free water
   || 70% Ethanol
   || 1mL pipette tips
   || 0.1mL pipette tips
   || 0.01mL pipette tips
   || Paper towelling 
   || Clinical waste sharps containers

### Safety, containment and contamination recommendations

   |---:|:---
   || Back-tie hydrophobic lab gown
   || Gloves
   || UV light sterilizers
   || MediPal Decontamination wipes
   || DNAway and RNAse Zap® reagent

## Protocol

### cDNA synthesis with Superscript IV Vilo cDNA kit

> **NOTE ON HOOD PREPARATION:** To prevent cross contamination of both the sample and other reagents, this should be carried out in the SAMPLE PREPARATION HOOD, which is pre-sterilised with UV and treated with MediPal wipes, DNAway and RNAseZap reagent. Wipe down the hood with each sequentially, allowing 5 minutes for drying between each. Pipettes should also be treated in the same way, and UV treated for 30 mins between library preparations. 

1. Recommend aliquoting the Vilo mastermix, to prevent cross contamination and to reduce potential freeze/thaw cycles.
2. Set up the following reaction:

   |---|--- 
   |2x Vilo Master Mix | 5L   
   |viral RNA | 5L   
   |TOTAL | 10L
   
3. Gently mix (avoid vortexing) then pulse spin the tube to ensure maximum contact with the thermal cycler.
4. Incubate the reaction as follows:

   |---|---|--- 
   | Primer annealing | 25&deg;C | 20 mins   
   | Extension | 50&deg;C | 30 mins   
   | Inactivation | 85&deg;C | 10 mins
   
5. cDNA is now ready for amplicon generation.

### Ebola Amplicon Preparation

> **NOTE ON HOOD PREPARATION:** To prevent cross contamination of both the sample and other reagents, this should be carried out in the MASTERMIX HOOD, which is pre-sterilised with UV and treated with MediPal wipes, DNAway and RNAseZap reagent. Wipe down the hood with each sequentially, allowing 5 minutes for drying between each. Pipettes should also be treated in the same way, and UV treated for 30 mins between library preparations.

#### Primer dilution and preparation

1. Ebola primers for this protocol were designed using Primal and generate a 400nt amplicon with a 75nt overlap. Primer names and dilutions are listed in the table below. 

2. Primers should be prepped and aliquoted PRIOR TO DEPARTURE in a STERILE PCR CABINET. At NO stage should primers or PCR reagents be anywhere near the template or amplicons until use. 

3. Generate primer pool stocks by adding 20uL of each primer pair to a 1.5mL Eppendorf labelled “Pool 1, 100M” or “Pool 2, 100M”. Total volume should be 460uL of each pool. This is a 10x stock of each primer pool. 

4. Dilute this primer pool 1:10 in molecular grade water, to generate 10uM primer stocks. Recommend that at least 1mL of each primer pool is taken in 100L aliquots, to account for any risks of degradation of contamination. 

5. Primers need to be used at a final concentration of 0.015M per primer. In this case, each pool has 23 primers in it, so the requirement is 0.8625L of 10M primer pool per 25L reaction. 

   | NAME         | Sequence                       | NAME          | Sequence               | Pool | [Stock] |
   |-------------:|--------------------------------|--------------:|------------------------|------|---------|
   | Ebov_1_LEFT  | TCTTTTGTGTGCGAATAACTATGAGGA    | Ebov_1_RIGHT  | TGTGTCCTACTGATTGCCAAGC | 1    | 100μM   |
   | Ebov_2_LEFT  | CCGGTCAGTTTCTCTCCTTTGC         | Ebov_2_RIGHT  | ACTCTGGTATTCGCCGTAGCTT | 2    | 100μM   |
   | Ebov_3_LEFT  | CGATGATGATGACGACATTCCCT        | Ebov_3_RIGHT  | TCATCCCATTGTTCCATGCTCA | 1    | 100μM   |
   | Ebov_4_LEFT  | TCCACCATGGCTCACTGAAAAA         | Ebov_4_RIGHT  | GACCGGTTGTCATCACCAGAAG | 2    | 100μM   |
   | Ebov_5_LEFT  | GCAACAACAAACCATCGCATCA         | Ebov_5_RIGHT  | AAAACACTCTCTCAGCCGAGGT | 1    | 100μM   |
   | Ebov_6_LEFT  | CGACCAAGATAAAATTGTTCATATCTCGC  | Ebov_6_RIGHT  | TTCTTACCGGTCAGCTTGTGGA | 2    | 100μM   |
   | Ebov_7_LEFT  | AAGGGGAACAGTGCCGATCTAA         | Ebov_7_RIGHT  | TCCTGTAACGCCCATTGTGTTG | 1    | 100μM   |
   | Ebov_8_LEFT  | GGCGATGAAGATTAAGCCGACA         | Ebov_8_RIGHT  | TGTCTCATTCAGCTGGAGCAGA | 2    | 100μM   |
   | Ebov_9_LEFT  | AGGACCCGTCTAGTGGCTACTA         | Ebov_9_RIGHT  | TGCAGCACCTTCATCCTGAGTA | 1    | 100μM   |
   | Ebov_10_LEFT | ATACCGGAGAAGAGAGTGCCAG         | Ebov_10_RIGHT | ACTCTACCGGTTCGCAGATCTG | 2    | 100μM   |
   | Ebov_11_LEFT | ACAAGGTTTGACATCAATCTAGTTATCTCT | Ebov_11_RIGHT | AACCCTGAAACAACGACAGCAG | 1    | 100μM   |
   | Ebov_12_LEFT | TCAACGATTACACAGTGATAAAGGAGG    | Ebov_12_RIGHT | CTTTTGTGGCGTATCTCAGGGG | 2    | 100μM   |
   | Ebov_13_LEFT | TGCGGAGGTCTGATAAGAATAAACC      | Ebov_13_RIGHT | TGGATCGAATCAACGACAGCAT | 1    | 100μM   |
   | Ebov_14_LEFT | GGACCAGCTGATTGACCAGTCT         | Ebov_14_RIGHT | CCGCAAGCTCTAGTGACTAGGT | 2    | 100μM   |
   | Ebov_15_LEFT | CTGCTTATTGGGTCTTTCCGTGT        | Ebov_15_RIGHT | CCAAGCACAATGGTTCGAGGAA | 1    | 100μM   |
   | Ebov_16_LEFT | CTCAAAAATAGCAGAGATTGAGGATCCA   | Ebov_16_RIGHT | AACATTGCGAGTCGGATAAGGC | 2    | 100μM   |
   | Ebov_17_LEFT | AGAGCAAGAAAACTTTTCTATTGAGAATGT | Ebov_17_RIGHT | AATGGTGCCATTCTTGTAGCCG | 1    | 100μM   |
   | Ebov_18_LEFT | CGCCAGCCTAGCAAAAGTTACA         | Ebov_18_RIGHT | CTCAGTCTGTCCAAAACCGGTG | 2    | 100μM   |
   | Ebov_19_LEFT | CCTGTTATGAGTCGTTTTGCGG         | Ebov_19_RIGHT | TCCCGGGTGCAACACTTAGTTA | 1    | 100μM   |
   | Ebov_20_LEFT | AGTTTTCAGGAGGTGGCCAGTC         | Ebov_20_RIGHT | TGCATGGAAGAAATTGCTGGCT | 2    | 100μM   |
   | Ebov_21_LEFT | AACCCAACACCTGTGAATAATTTTCTC    | Ebov_21_RIGHT | AGGTAGCCTTGCTCTTTGGTCT | 1    | 100μM   |
   | Ebov_22_LEFT | AGTATCAGGAATGACTACTCCTAGGATG   | Ebov_22_RIGHT | TCAGAAGCCCTGTCAGCCTTTC | 2    | 100μM   |
   | Ebov_23_LEFT | AGGACGAATCACAAAACTAGTCAATGA    | Ebov_23_RIGHT | TGTGTGCGACCATTTTTCCAGG | 1    | 100μM   |

6. Set up the amplicon PCR reactions as follows:

   |Reagent |POOL 1 |POOL 2 |
   |--------|-------|-------|
   |NEB Q5® Polymerase 2X MasterMix |12.5L |12.5L |
   |Primer Pool 1 or 2 (10uM) |0.9L |0.9L |
   |Water |7.5L |7.5L |
   |TOTAL |25L |25L |

   > **NOTE:** This should be carried out in the mastermix hood and cdna should not be taken anywhere near the mastermix hood at any stage.

7. In the TEMPLATE HOOD add 4.1&micro;L of cDNA to each Pool1 and Pool2 reaction mix. 

8. Set up the cycling conditions as follows:

   |                |Temperature |Time        |Cycles |
   |----------------|------------|------------|-------| 
   |Heat Activation |98&deg;C        |30 seconds  |1      |
   |Denaturation    |98&deg;C        |15 seconds  |35     |
   |Annealing       |60&deg;C        |30 seconds  |1      |
   |Extension       |72&deg;C        |120 seconds |1      |
   |Hold            |4&deg;C         |Indefinite  |1      |				

9. Clean-up the amplicons using the following protocol in the TEMPLATE HOOD:

   1. Transfer the entire contents of “Pool1” and “Pool2” to a single 1.5mL Eppendorf tube. 
   
   2. Mix sample gently, avoid vortexing.
     
   3. Ensure AmpureXP beads are well resuspended by thoroughly mixing prior to addition to the sample. Mixture should be a homogenous brown colour. 
     
   4. Add an equal volume of AmpureXP beads to the tube and mix gently. This should be approximately 50uL, so add 50uL of beads.
     
   5. Incubate for 2 mins at 25&deg;C.
    
   6. Place on magnetic rack and incubate for 2 mins or until the beads have pelleted against the magnet and the solution is completely clear. 
     
   7. Carefully remove and discard the solution, being careful not to displace the bead pellet. 
   
   8. Add 200 &micro;L of 70% ethanol to the pellet. 
     
   9. Remove from magnet and mix by gently flicking the tube. 
    
   10. Pulse centrifuge the tube to make sure all the mixture is out of the lid following flicking, then place back onto the magnet. 
    
   11. Incubate for 2 mins or until the beads have pelleted against the magnet and the solution is completely clear. 
    
   12. Carefully remove and discard ethanol, being careful not to displace the bead pellet.
     
   13. Repeat steps `h` to `l` to wash the pellet again. 
     
   14. Briefly pulse centrifuge the pellet and carefully remove as much ethanol as possible using a 10uL tip. 
     
   15. Allow the pellet to dry for 2 mins, being careful not to overdry (if the pellet is cracking, then it is too dry).
     
   16. Resuspend pellet in 30μL of water, and incubate for 2 mins. 
     
   17. Place on magnet and CAREFULLY remove water and transfer to a clean 1.5mL Eppendorf tube. MAKE SURE that no beads are transferred into this tube. 
     
   18. Quantify the amplicon library using Qubit4® following the dsDNA protocol.
    
### Qubit Quantification of Nucleic Acid: dsDNA

1. Set up the required number of 0.5mL tubes for standards and samples. The Qubit™ 1X dsDNA HS Assay requires 2 standards. 
   > **NOTE:** Use only thin-wall, clear, 0.5mL PCR tubes. Acceptable tubes include Qubit™ assay tubes (Cat. No. Q32856) 
   
2. Label the tube lids. Do not label the side of the tube as this could interfere with the sample read. Label the lid of each standard tube correctly. Calibration of the Qubit™ Fluorometer requires the standards to be inserted into the instrument in the right order

3. Add 10µL of each Qubit™ standard to the appropriate tube. 

4. Add 1–20µL of each user sample to the appropriate tube. 
   > **NOTE:**  If you are adding 1–2μL of sample, use a P-2 pipette for best results. 1.5 

5. Add the Qubit™ 1X dsDNA 1X buffer to each tube such that the final volume is 200µL. 
   
   > **NOTE:**  The final volume in each tube must be 200µL. Each standard tube requires 190µL of Qubit™ working solution, and each sample tube requires anywhere from 180–199µL. Ensure that you have sufficient Qubit™ working solution to accommodate all standards and samples. 
   
   > **NOTE:**  To avoid any cross-contamination, we recommend that you remove the total amount of working solution required for your samples and standards from the working solution bottle and then add the required volume to the appropriate tubes instead of pipetting directly from the bottle to each tube. 

6. Mix each sample vigorously by vortexing for 3–5 seconds. 

7. Allow all tubes to incubate at room temperature for 2 minutes, then proceed to “Read standards and samples”. 

8. On the Home screen of the Qubit™ 4 Fluorometer, press DNA, then select `1X dsDNA HS` as the assay type. The `Read standards` screen is displayed. Press `Read Standards` to proceed. 
   > **NOTE:** If you have already performed a calibration for the selected assay, the instrument prompts you to choose between reading new standards and running samples using the previous calibration. **If you want to use the previous calibration, skip to step 2.4**. Otherwise, continue with step 9. 

9. Insert the tube containing Standard #1 into the sample chamber, close the lid, then press Read standard. When the reading is complete (~3 seconds), remove Standard #1. 

10. Insert the tube containing Standard #2 into the sample chamber, close the lid, then press Read standard. When the reading is complete, remove Standard #2. 

11. The instrument displays the results on the Read standard screen. For information on interpreting the calibration results, refer to the Qubit™ Fluorometer User Guide, available for download at thermofisher.com/qubit. 

12. Press `Run samples`. 

13. On the assay screen, select the sample volume and units: 

    > a) Press the + or – buttons on the wheel, or anywhere on the wheel itself, to select the sample volume added to the assay tube (from 1–20μL). 
    >
    > b) From the unit dropdown menu, select the units for the output sample concentration. 

14. Insert a sample tube into the sample chamber, close the lid, then press `Read tube`. When the reading is complete (~3 seconds), remove the sample tube. 

15. **The top value (in large font) is the concentration of the original sample and the bottom value is the dilution concentration**. For information on interpreting the sample results, refer to the Qubit™ Fluorometer User Guide. 

16. Repeat step 2.6 until all samples have been read.

17. Carefully **record all results** and store run file from the Qubit on a memory stick. 

### Barocoding and adaptor ligation: One-pot protocol.
 
> **NOTE:** This is a ‘one-pot ligation’ protocol for native barcoded ligation libraries. We have seen no reduction in performance compared to standard libraries, and is made faster by using the Ultra II® ligation module which is compatible with the Ultra II® end repair/dA-tailing module removing a clean-up step. It can be used with or without the optional FFPE DNA repair step. If you have the time I would recommend using the double incubation times in blue, if you are in a hurry the times in red are a good compromise between speed and efficiency.

1. Set up either the following end-prep reaction for each sample:

   | DNA (500 ng) | 25 μl
   | Ultra II End Prep Reaction Buffer | 3.5 μl
   | Ultra II End Prep Enzyme Mix | 1.5 μl
   | Total | 30 μl

   Or to include FFPE DNA repair set up the following combined reaction:

   |DNA (500 ng) | 24 μl
   |Ultra II End Prep Reaction Buffer | 1.75 μl
   |FFPE DNA Repair Buffer | 1.75 μl
   |Ultra II End Prep Enzyme Mix | 1.5 μl
   |FFPE DNA Repair Mix | 1 μl
   |Total | 30 &micro;l

2. Incubate at RT for 5 mins or 10 mins then 65&deg;C for 5 mins or 10 mins

3. Place on ice for 30 secs

4. Add the following directly to the previous reactions:

   | NBXX barcode | 2.5 μl
   | Ultra II Ligation Master Mix | 20 μl 
   | Ligation Enhancer | 1 μl
   | Total | 53.5 μl
   
5. Incubate at RT for 10 mins or 20 mins, 70&deg;C for 5 mins then place on ice.

6. Pool all barcoded fragments together into a clean 1.5 ml Eppendorf tube

7. Add 26.75 μl Ampure XP beads per sample.

8. Incubate for 5 mins or 10 mins.

9. Place on a magnet rack until clear.

10. Remove solution. 

11. Add 200 μl 80% ethanol to the tube still on the magnetic rack.

12. Incubate 30 secs.

13. Remove solution.

14.	Repeat last three steps (12-14).

15.	Spin down and remove residual 70% ethanol and air dry for 1 min.

16.	Resuspend in 31 µl EB.

17.	Incubate off the magnetic rack for 5 mins or 10 mins.

18.	Replace on magnetic rack.

19.	Remove 1 µl and assess concentration by Qubit as described in previous section. 

20. Set up the following adapter ligation reaction:

   | Cleaned-up barcoded fragments (~3 µg) | 30.0 µl
   | BAM 1D | 20.0 µl
   | Ultra II Ligation module | 40.0 µl
   | Ultra II Ligation enhancer | 1.0 µl
   | Total volume | 91.0 µl

21. Incubate at RT for 10 mins or 20 mins

22. Add 45.5 μl Ampure XP beads

23. Incubate for 5 mins or 10 mins mins

24. Place on a magnetic rack until clear

25. Remove supernatant 

26. Add 150 μl ABB and resuspend by flicking 

> **CAUTION:** do not use 80% ethanol

27. Place on magnetic rack until clear

28. Remove supernatant

29. Repeat ABB wash

30. Spin down and remove residual ABB

31. Add 12 μl ELB and resuspend by flicking

32. Incubate at RT for 5 mins or 10 mins

33. Place on magnetic rack

34. Carefully transfer solution to a clean 1.5mL Eppendorf tube. 

35. Remove 1 µl and assess concentration by Qubit (wait until beads have settled before measuring).

> **NOTE:** Library can be now be stored at -20oC if required, but for best results it would be best to proceed immediately to sequencing. 

### Priming and loading the SpotON flow cell 

1. Thaw the following:
   - ABB Buffer (ABB) at RT 
   - Library loading beads (LLB) at RT   
   - Running Buffer with Fuel Mix (RBF) on ice 

2. Thoroughly mix the contents of the RBF and LLB tubes by pipetting.

3. Flip back the MinION lid and slide the priming port cover clockwise so that the priming port is visible.

> **IMPORTANT:** Care must be taken when drawing back buffer from the flow cell. The array of pores must be covered by buffer at all times. Removing more than 20-30 μl risks damaging the pores in the array.

5. After opening the priming port, check for small bubble under the cover. Draw back a small volume to remove any bubble (a few μls):   
   - Set a P1000 pipette to 200 μl   
   - Insert the tip into the priming port   
   - Turn the wheel until the dial shows 220-230 μl, or until you can see a small volume of buffer entering the pipette tip.  
    
6. Prepare the flow cell priming mix in a clean 1.5 ml Eppendorf tube: 

   | RBF | 576 μl 
   | Nuclease-free water | 624 μl 
   
7. Load 800 μl of the priming mix into the flow cell via the priming port, avoiding the introduction of air bubbles. 

8. Wait for 5 minutes.                                            

9. In a new tube prepare the library dilution for sequencing:

   | Reagent | Volume
   |---|--- 
   | RBF | 35 µl
   | Nuclease-free water | 2.5 µl
   | LLB | 25.5 µl
   | Library | 12 µl
   | Total | 75 µl 

10. Gently lift the SpotON sample port cover to make the SpotON sample port accessible.

11. Load 200 μl of the priming mix into the flow cell via the priming port (**NOT** the SpotON sample port), avoiding the introduction of air bubbles.

12.  Mix the prepared library gently by pipetting up and down just prior to loading.

13. Add 75 μl of sample to the flow cell via the SpotON sample port in a dropwise fashion. Ensure each drop flows into the port before adding the next.

14. Gently replace the SpotON sample port cover, making sure the bung enters the SpotON port, close the priming port and replace the MinION lid.

15. Double–click the MinKNOW icon located on the desktop to open the MinKNOW GUI. 

16. If your MinION was disconnected from the computer, plug it back in.

17. Choose the flow cell type from the selector box:
 
   > R9.4.1 flowcells are `FLO-MIN106`
   >
   > R9.5.1 flowcells are `FLO-MIN107`

18. Then mark the flow cell as `Selected`. 

19. Click the `New Experiment` button at the bottom left of the GUI.

20. On the New experiment popup screen, select the running parameters for your experiment from the individual tabs:
   
   > Output settings - FASTQ: The number of basecalls that MinKNOW will write in a single file. By default this is set to 4000
   >
   > Output settings - FAST5: The number of files that MinKNOW will write to a single folder. By default this is set to 4000
   
21. Click `Begin Experiment`.

22. Allow the script to run to completion.

23. The MinKNOW Experiment page will indicate the progression of the script; this can be accessed through the `Experiment` tab that will appear at the top right of the screen

24. Monitor messages in the Message panel in the MinKNOW GUI
