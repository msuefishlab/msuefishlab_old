---
author: consta64
author_profile: true
comments: false
date: 2015-11-17 21:26:35+00:00
layout: single
title: Genome Annotation
---

Genome Annotation

Broadly, genome annotation is the downstream processing of genome sequencing; now that the sequence is known, relevant information about gene numbers, structure, splice variants, ncRNAs, _etc_, need to be identified. Genome annotation is that process and encompasses two phases, structural and functional annotation.

Structural annotation is the process by which genes are found in genomic DNA, whereas function annotation is the process of naming a gene and describing its role/function. Our discussion, led by Dr. Kevin Childs, focused on structural annotation and its process and will be the focus of this discussion; however, his notes on functional annotation are present on his presentation.
Kevin proposed three resources to help better understand genome annotation and its process: Yandell & Ence- _Nature Reviews Genetics_ **13**, 329-342 (May 2012)
Campbell _et al._- _Plant Physiology_ **164**(2), 513-524 (February 2014)
and an in-depth/”cookbook” text, Campbell _et al._- _Curr. Protol. Bioinform_. **48**, 4.11.1-4.11.39 (2014).

Although in the past genomes were annotated by hand and provided very high quality annotated genomes, this process is very time, cost, and labor intensive. The vast majority of genome annotations are now done using computers with some human input at the end to “clean things up”.
A genome assembly pipeline that is used regularly is MAKER.




  * Maker begins by first performing repeat masking. Repeat masking is an incredibly important step in annotating eukaryotic genomes as many repeat regions are due to transposable elements (TE), which contain genes. Thus if repeats from TE are not screened out of downstream annotation, the genes within TEs will be annotated and would have to be removed later. Repeat masking is often done through RepeatMasker or RepeatRunner.


  * The MAKER pipeline then aligns transcripts and protein sequences from the organism of study to the genome sequence. By providing evidence of gene identities (through RNA and proteins), “hints” are given to the computer to help it better assess genes. Protein sequences from other organisms (with high sequence homology) can also be put in as evidence. RNA evidence seems to be more useful in facilitating genome annotation than protein information. Evidence-based alignment is often a two-step process with a basic alignment carried out by BLAST/BLAT that is then refined using a splice site aware alignment program (like Exonerate).


  * _ab initio _prediction of genes. This process is one where a machine learning program is used to predict genes. We talked mainly about hidden Markov models (HMMs), a program that uses organism specific CG content and codon usage to predict genes. HMMs are a self-learning system that are fed k-mers (usually 5-mer) of known genes (either from the organism of study or from conserved “housekeeping” genes) and use that information to predict gene sequences. The predictions are usually the coding sequence of the gene and lack alternative splice variants and UTRs.
Repeating the _ab initio_ prediction of genes generally improves the predictions.


  * Creation of final gene model. The final step in the pipeline is one where evidence based UTRs and predictions of alternate splice forms (Evidence Modeler, EVM) are added to the predicted genes. The best final prediction is then matched to the evidence and assigned an annotation edit difference (AED) score. The AED score has the general formula: 1-((sensitivity+specificity)/2). Thus a score of 1 is the lowest with no matches and 0 is the best meaning a perfect match. Ideally all the annotations should be towards zero and the % of gene predictions with an AED of 0.5 or less should be high for a well annotated genome.


At the end of the annotation process MAKER provides 3 sets of predicted genes: Max which includes all predicited genes, even those without evidence; default which includes only those genes with direct evidence; and standard which includes all genes with evidence and those that contain a pfam (protein family) domain. The standard set will include any predicted genes that have protein family motifs that may be absent from the evidence. For example, if RNA-seq data from an adult organism is used as transcript evidence for the genome annotation, any genes expressed during development will not be present. The genome will contain those genes expressed only during development and they can be identified by pfam domains like DNA binding sites, zinc-finger domains, _etc _and included in the predicted genes of the standard set.
