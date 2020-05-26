---
author: rothmitc
author_profile: true
comments: false
date: 2015-11-12 03:12:48+00:00
layout: single
title: Methylation, Chromatin, and ChIP-seq
---

Reading materials for this topic were provided by Kevin McCormick (Ph.D. student in Dr. Kay Holecamp's lab): [Yamamoto & Yamamoto 2004](http://www.ncbi.nlm.nih.gov/pubmed/15146327), [Furey 2012](http://www.ncbi.nlm.nih.gov/pubmed/23090257), [Yan et al. 2014](http://www.biomedcentral.com/1471-2105/15/280), [Meyer et al. 2015](http://www.nature.com/articles/srep15375), and [Tost and Gut 2007](http://www.nature.com/nprot/journal/v2/n9/full/nprot.2007.314.html).

Also, stay tuned for a special podcast / video presentation from Kevin about this topic as an addition to this summary!

Eukaryotic organisms organize their DNA around histones to form nucleosomes and chromatin.  Chromatin immunoprecipitation (ChIP) is a method molecular biologists use to determine what specific DNA sequences bind to histones.  ChIP-seq then, includes these steps; the DNA is cross linked to the histone, the histones are precipitated out with specific antibodies, the DNA is separated from the histone, and the DNA is sequenced.  Histones can be methylated in different patterns (H3K4, H4K20, etc.) which also change what DNA sequences the histones are associated with, so ChIP-seq is often used in different tissues to determine different chromosome-DNA associations that may be associated with tissue specific phenotypes.  Different methods are used to complement ChIP-seq - notably FAIRE-seq, DNase-seq, and DNase footprinting.

Like histones, DNA is often methylated too.  Methylated DNA typically occurs on cytosine residues next to guanine residues, or at "CpG islands".  DNA methylation is useful for organisms to determine what DNA is their own versus what DNA is foreign.  Therefore, a relatively high level DNA methylation is good at reducing transposable element activity and good at identifying DNA from pathogens.  DNA methylation patterns also impact phenotypes - active genes are often associated with lower amounts of methylation.  Large scale regions of hypermethylation and hypomethylation are often associated with phenotypes as well, even if they are not near a known gene.
It is worth mentioning that these characteristics of DNA methylation refer to those of mammals (which have the greatest amount of work done in them). Invertebrates, especially insects, have very different methylome patterns including:
1) Overall methylation is much lower (sometimes as low as less than 1% of CpG sites are methylated compared to 70-80% in mammals).
2) Methylation occurs mostly in exonic DNA (compared to promoters and non-coding DNA being methylated in mammals).
3) There is an increase of methylation at intron/exon borders (this methylation is thought to regulate alternative splicing) and a bias towards the 5' end of a gene being more highly methylated than the 3' end.
4) More methylation of a gene is indicative of higher transcription (unlike mammals where, generally, methylation reduces transcription).
5) Transposable elements are not methylated yet have little transcription.

Scientists can study these patterns of DNA methylation using Methylation Sensitive Amplified Fragment Length Polymorphism (MS-AFLP).  A recent advancement in this technique (see the Yamamoto paper) has allowed MS-AFLP to become more high throughput using methylation sensitive restriction enzymes and fluorescent probes.

Methylation can occur on both histones and DNA simultaneously.  However, methylation patterns of DNA are easier to study due to the longer lasting nature of the methylation.  Histone modifications seem to occur MUCH faster than DNA modifications. Overall, it seems that organisms that inherit DNA that is lower in methylation have a higher fitness because the lower methylation allows for more flexibility in gene transcription, or a more responsive phenotype when exposed to various environments.  Different epigenetic inheritance patterns of methylated DNA is also believed to play a role in behavior and personalities of various animals.
