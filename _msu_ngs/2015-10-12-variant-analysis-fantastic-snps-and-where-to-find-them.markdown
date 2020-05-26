---
author: dawsonb5
author_profile: true
comments: false
date: 2015-10-12 13:17:35+00:00
layout: single
title: Variant Analysis – Fantastic SNPs and Where to Find Them
---

This week’s talk was imparted by MSc Dharanya Sampath, Research Consultant at the Institute For Cyber-Enabled Research (iCER), Michigan State University. It was primarily about the process of detecting variants in your next-gen data. Broadly speaking, this process involves the following steps –




  1. Trimming Reads


  2. Read Mapping


  3. Preparation of BAM files


  4. Variant Calling


  5. Variant Filtering


  6. Variant Annotation


The talk summarized what goes on in each of these steps, and what programs are useful for doing them. The bulk of the discussion dealt with how variant calling software actually operates, and the differences between available software packages.


  1. Trimming Reads – Read trimming allows the user to trim their sequence data based on a number of factors, but the most relevant are quality score and adaptor sequence content. The primary programs used for this are trimmomatic and FastQC. I would be remiss if I did not note that FastQC also produces an excellent visual summary of various quality aspects of your data, such as adapter content, G-C distribution, and positional quality score data.


  2. Read Mapping – The actual assembly of your reads into a genome sequence. This can be done as a _de novo _ assembly, which operates by looking strictly at read overlap, or my assembling your reads against a reference genome. Popular programs for read mapping are BWA and Bowtie are the most popular aligners for mapping to a reference genome. These programs use a Burrows-Wheeler transform to create an index for the genome to which your reads can be mapped.


  3. Preparing a BAM file – Using programs like SAMTools and Picard, you can convert the output from your read mapping (a SAM file) into a binary version of the same file, a BAM. At this step, it is also useful to remove duplicated reads and improperly-paired paired-end reads. Programs like Tablet and IGV can be used for visualizing your BAM alignment directly.


  4. Variant calling – In this step, you compare your newly-minted BAM file to the reference version of the genome and look for variations. This, in theory, should allow you to detect a wide variety of variants, including SNPs, insertions, deletions, and substitutions. If you used paired-end reads when doing your sequencing, clusters of broken read-pairs can give you some indication of chromosomal structural variation, although software is less robust in calling these. Popular variant callers include VarScan, FreeBayes, SAMTools, BCFTools, and GATK.


  5. Variant Filtering – There’s not much to say at this stage – variant filtering is often done via unix commands, and what criteria you choose to filter your variants by is usually dependent on the type of study you’re performing.


  6. Variant Annotation – Programs like SnpEff, SnpSift, and ANNOVAR allow you to compare your variants to a database of previously annotated genes (obtained from Ensemble or a similar source), and attempt to determine what effect the variant will have on the gene.


Most of the class discussion centered on why there is such a large discrepancy in the number and identity of the variants called by the various variant callers. SAMTools and BCFTools, for instance, are known to produce a lot of extraneous data that does not hold up to further scrutiny, whereas GATK and FreeBayes are both relatively well regarded, although even these have a fairly large number of variant calls unique to each caller. The general problem is that these variant callers are generally treated like black boxes by their end users, and careful scouring of the documentation is necessary in order to determine what the various initial assumptions each variant caller is using are. Although differences in the algorithms used will still probably produce slightly different variant lists, the general conclusion seems to be that if you tune all the parameters the same way, variant callers will produce approximately the same list of variants regardless of caller. It is therefore essential to be familiar with the default parameters of whichever one you choose to use, even those that may be hidden. But hey, a little digging around in the documentation never hurt anybody.

The references for this talk were:


  1. [Validation and assessment of variant calling pipelines for next-generation sequencing](http://humgenomics.biomedcentral.com/articles/10.1186/1479-7364-8-14)


  2. [A survey of tools for variant analysis of next-generation genome sequencing data](http://bib.oxfordjournals.org/content/15/2/256.long)
