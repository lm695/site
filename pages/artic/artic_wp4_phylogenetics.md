---
title: "Work Package 4: Real-time phylodynamic analysis"
keywords: about
last_updated: October 5, 2017
tags: [wp4]
summary:
sidebar: artic_sidebar
permalink: wp4-phylogenetics.html
toc: false
folder: artic
---

### Generating a real-time temporal and evolutionary overview of the epidemic

We are developing efficient ‘real-time’ approach that can automatically update the time-measured phylogeny of an outbreak as sequence data is generated. 
In addition to the approach implemented in [nextstrain](www.nextstrain.org/), we are extending the [BEAST](http://beast.community) framework to allow a rapid convergence to the posterior distribution of phylogenies for an expanded sequence data set.

{% include image.html file="real-time-trees.png" caption="" %}

This dynamically updating phylogeny provides an overview of the developing outbreak or epidemic, and provides a framework for downstream analyses.

### Spatial phylogenetic reconstruction and molecular epidemiology

We use [phylogeographic models]() to reconstruct the geographical dissemination of viruses as the epidemic progresses. 
To date, these analyses have generally been addressed using continuous or discrete diffusion processes on a tree but efficient implementations of 'population structure' models, based on coalescent or birth-death process, will allow more flexible integration of other sources of epidemiological data and direct estimation of key epidemiological parameters.

{% include image.html file="phylogeography.png" caption="" %}

These analyses will be used to provide detailed, practical and interpretable visualizations of the spread of the outbreak as well as detailed information about the overall process (i.e., numbers of movements, distances travelled, locations that are hubs of viral migration). 

### Testing hypotheses of epidemiological linkages between cases


### [Presentations on workpackages are available here](presentations)

{% include links.html %}

