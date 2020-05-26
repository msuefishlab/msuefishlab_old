---
author: parigiab
author_profile: true
comments: false
date: 2015-10-25 20:59:43+00:00
layout: single
title: An introduction to RNA seq and transcriptome assembly
---

RNA seq uses next-generation sequencing technologies for discovering and quantifying the complete set of transcripts in a given population of cells. The applications of RNA seq include: transcriptome assembly, quantifying gene expression, identifying gene structure, gene annotation, detection of alternative and trans-spliced genes, identification of post translational modifications, and the quantification of other non-coding RNA molecules. Unlike older high-throughput technologies (e.g. microarrays), the main advantages of RNA seq are that good quality results can be obtained with relatively small amounts of total RNA, and an _a priori_ knowledge of the genome or RNA sequence is unnecessary.

**Experimental design for RNA seq experiments**: Just like any biological experiment that deals with variation, RNA seq experiments require careful experimental design. In general, the parameters we would choose depend on our biological question. Additionally, RNA seq often requires proper consideration of technical variables that could bias the representation of reads. Although increasing the number of biological replicates can deal with a number of technical biases, it is important to understand the sequencing process in order to minimize location or cycle related biases that may arise. Finally, because RNA seq is expensive, the best strategy would be to first invest in more biological replicates. If sequencing depth becomes an issue, we can always go back to the previous library and re-sequence, to get greater coverage. While looking for rare splices variant or transcripts, increasing depth may result in the detection of stochastically produced transcripts (i.e., not biologically relevant).

** ****Transcriptome assembly**: transcriptome assembly is a lot like genome assembly, but biological differences between DNA and RNA directly translate to differences in how the assemblers work. Before assembly, tRNA and rRNA must be removed from samples (either by poly A selection or rRNA depletion) (A newer option, Probe-Directed Degradation, is discussed in reference 3). Careful consideration of strategies (based on how much money we can spend) is essential: for example, we should decide on the platform to use, we may want to use paired end sequencing to get a better idea of exon connectivity, and may need to use a strand specific protocol to get information about individual strands.

There are three different strategies for transcriptome assembly:

1) **Reference based assembly**: where reads are aligned to a reference genome. First, reads are aligned to the genome using a splice-aware aligner . Then the assembly software determines connectivity between exons to find different isoforms. Advantages of reference based assembly are that it requires less computational power, can align low abundance transcripts better, efficiently filters out transcripts from contaminants, and facilitates novel transcript discovery. Main disadvantage is that assembly depends on the quality of the reference genome. It also incorporates errors from splice -aware aligners, and must deal with reads aligned to multiple loci.

2**) _de novo_ assembly**: uses redundancy in short read sequences to find overlapping regions, then joins the overlapping regions to form full length transcript (De Bruijn graph approach, see video at reference 4 for a more detailed explanation of De Bruijn graphs). Its main advantage is that no reference genome is required. Disadvantages of _de novo_ assembly are that it needs more computational resources, greater coverage than reference based strategies, and is more difficult to distinguish highly similar transcripts. Finally, de novo assembly is more sensitive to sequencing errors.

**3)** **Combined strategy**: if a reference genome is available, we can combine both _de novo _and reference based strategies. By doing so, we can minimize the disadvantages that are inherent to each type of assembly. The PASA pipeline offers this option (reference 5).

Lastly, reference 6 offers a great example of how transcriptome assembly can be combined with other NGS techniques to tackle interesting biological questions.

These links provide more information on these topics:




  1. [Next-generation transcriptome assembly ](http://www.nature.com/nrg/journal/v12/n10/full/nrg3068.html%3Fwt.ec_id%3Dnrg-201110)


  2. [Design and validation issues in RNA-seq experiments](http://bib.oxfordjournals.org/content/early/2011/04/15/bib.bbr004)


  3. [Probe-Directed Degradation](http://www.biomedcentral.com/1471-2164/15/401)


  4. [De Bruijn graphs](https://www.youtube.com/watch?v=q_9v_cWZcec)


  5. [Combined strategy using PASA](http://pasapipeline.github.io/#A_ComprehensiveTranscriptome)


  6. [The octopus genome and the evolution of cephalopod neural and morphological novelties](http://www.nature.com/nature/journal/v524/n7564/abs/nature14668.html)
