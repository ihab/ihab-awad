---
layout: page
title: Caryoscope
---

Caryoscope was a project I worked on while at the Department of Genetics at Stanford University, creating a task specific user interface for genetics research.

## The problem

The genes of an organism are physically represented on strands of DNA, called chromosomes. In some organisms, including humans, these come in matched pairs. The description of an organism's chromosomes is called its _karyotype_. The following shows the chromosomes of a human:

{% include gallery.md imgs="karyotype.png" %}

A gene is _expressed_ when the cellular machinery uses that gene to manufacture the protein that the gene describes. Gene expression data -- the extent to which certain genes are being expressed under given circumstances -- is important in understanding how a cell is using its genes, or conversely, how a gene functions within the cell.

A particular assay, ArrayCGH, is able to determine whole genome _comparative_ gene expression data. Relative to a baseline, the assay determines which genes are more or less strongly expressed. The problem we faced was to show this massive amount of data in a relatively compact way, using the karyotype as a source of physical coordinates.

## The application

We built an interface showing increases and decreases of expression as colored bars, anchored to a simple graphical representation of the karyotpe:

{% include gallery.md imgs="caryoscope_basic.webp" %}

Technically, I built the work as a series of graphical widgets which other Java applications could embed based on a data model, where the data model was represented as Java `interface`s. Using these widgets, I also built an application, which could be invoked from the command line, which accepted CSV files in commonly used formats.

I built the graphical interactions using [Piccolo2D](https://piccolo2d.org/), a zooming user interface library. In so doing, I constructed novel interactors to control smooth, live panning and zooming, including an interactor allowing simultaneous different zooming scales along the X and Y axes.

{% include gallery.md imgs="pan-zoom.webp" %}

## Citation

Awad, I.A., Rees, C.A., Hernandez-Boussard, T. et al. Caryoscope: An Open Source Java application for viewing microarray data in a genomic context. BMC Bioinformatics 5, 151 (2004). [https://doi.org/10.1186/1471-2105-5-151](https://doi.org/10.1186/1471-2105-5-151)

