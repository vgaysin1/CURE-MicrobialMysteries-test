

# Finding AMRs

## Lecture: Finding AMRs

<img src="resources/images/finding-AMRs_files/figure-html//165OHha9IYOctuyzg1CG0LwGxNnbC85JyJfMZT6xnYHw_g35f391192_00.png" width="480" />

[Slides: Finding AMRs](https://docs.google.com/presentation/d/165OHha9IYOctuyzg1CG0LwGxNnbC85JyJfMZT6xnYHw/edit?usp=sharing)

## Homework: Finding AMRs Prelab

### Purpose

To use a Galaxy tools to perform de novo genome assembly of sequencing reads into contigs, visualize the contigs and find antimicrobial resistance (AMR) genes.

### Learning Objectives

Use Galaxy tools to:

1. Use Flye tool to perform de novo genome assembly of long reads into ‘contigs’
2. Visualize contigs with Bandage Image tool
3. Use ABRicate tool to find AMRs in contig assemblies

### Introduction

Genome assembly is the process of reconstructing genomes from DNA sequence reads. Accurate and continuous genome assembly from sequenced fragments, even very long fragments, is challenging. Flye, is a long-read assembly algorithm that aims to produce highly contiguous genome assemblies and overcome some of the assembly challenges, like repetitive DNA sequences. Using Flye we will hope to be able to reconstruct bacterial genomes and plasmids and enable detection of important genes like AMRs. Ideally, after assembly we want to get back circular contigs as that would typically indicate an entire microbial genome(s) or plasmid(s). 

<br>

Antimicrobial resistance is the ability of microbes to evade one or more antibiotics, leading to multidrug resistance and ability to survive and even thrive in the presence of antibiotics. Detecting and studying antibiotic-resistant pathogens is therefore extremely important to human health. However, the environmental reservoirs of resistance determinants are poorly understood. Certainly the indiscriminate and sometimes inappropriate use of antibiotics by humans (e.g. in the hospitals, in food production) has contributed to the emergence of resistant bacterial strains, but there are many other ways microbes can acquire AMR. For example, the environment like soil is emerging as a key reservoir of these antibiotic resistance genes. For more information on AMRs see the following review articles: [10.1038/nrmicro2312](https://doi.org/10.1038/nrmicro2312) and [10.3390/antibiotics13121112](https://doi.org/10.3390/antibiotics13121112).

<br>

**Table of approximate minimum times for a job to be completed on Galaxy using specified tools.**
- Note, these times apply only to the specific input file we will be using in this activity, the Zymo_Gut_Standard_D6331_subset that is ~340MB, and will take longer (or much longer) for larger (or much larger) input files.

| Flye | Bandage Image | ABRicate |
| :--| :--| :--|
| 5 min | < 5 min | < 5 min |


### Activity 1 – Flye assembly

*Estimated time: 45 min*

#### Instructions

**1. Run Flye in Galaxy using Zymo Gut Standard D6331 subset to assemble gut microbial genomes.**

a. Obtain .fastq file from `Zymo_Gut_Standard_D6331_subset`.
[https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1](https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1)

b. Name your new history **“Finding gut AMRs”**.

c. Run Flye  tool to assess sequence quality using the following Tool Parameters:

- Under **Input Reads**: select your `Zymo_Gut_Standard_D6331` **.fastq** dataset.
- Under Mode: select `PacBio HiFi (--pacbio-hifi)` option, since the sequences were obtained using PacBio HiFi sequencing technology.
- Under **Perform metagenomic assembly**: select `Yes`
- Under **Generate a log file**: select `Yes`

**2. View Flye results**
- Explore Flye output files and answer questions below

#### Questions

**1. Explore Flye tool purpose and output**

|A. In your own words describe the purpose of Flye based on the Introduction section, and from the `Purpose` section of Flye tool description.|
|:--|
|  |
<br>


|B. How many Flye output files did you get back, and what are they?|
|:--|
|  |
<br>

|C. What are the file extensions (formats) for the following Flye output files?|
|:--|
| consensus |
| graphical fragment assembly | 
<br>

**2. Explore Flye log report file.**

A. Based on your Flye output `log report file`: At the very bottom of the very long file find how many bases were assembled. What is the `Total length`?|
|:--|
| |
<br>

|B. Based on your Flye output `log report file`: At the very bottom of the file find the length of the longest assembled fragment? Look for `Largest frg`?|
|:--|
| |
<br>

|C. What proportion of input was assembled into contigs?|
|:--|
| - At the very top of the log file you will find that the input number of bases was 177,760,975 (Look for Total read length)
- Compare to the total length after assembly from your answer to question 4 above) |
| |
<br>

**3. Explore Flye assembly info file.**

|A. Based on your Flye output `assembly info file`[which is sorted by length (in base pairs, bp) of the contig (high to low). 
]: What is the longest `contig size?|
|:--|
| |
<br>

|B. Based on your Flye output `assembly info file`[which is sorted by length (in base pairs, bp) of the contig (high to low). 
]: What is the shortest contig size?|
|:--|
| |
<br>

**4. Explore Flye output consensus file (in FASTA format).**

|A. What is the beginning line of the FASTA format?|
|:--|
| |
<br>

|B. How does FASTA sequence format differ from FASTQ sequence format?|
|:--|
|See this link for a quick summary comparison of the 2 formats [https://compgenomr.github.io/book/fasta-and-fastq-formats.html](https://compgenomr.github.io/book/fasta-and-fastq-formats.html)
 |
| |
<br>

**5. Test your general understanding of genome assembly.

|A. Summarize your experience with assembling a genome with Flye.|
|:--|
| E.g., were you surprised at the percentage of assembled input, at the length of the largest contig, at the abundance of linear contigs, or anything else?|
| |
<br>

|B.  What would you want the ideal genome assembly tool to do?|
|:--|
| |
<br>

### Activity 2 – Visualizing contigs



## Lecture: Scientific Posters

<img src="resources/images/finding-AMRs_files/figure-html//1-orSi8DpN22hMt9-6p_rHZnte1YXXLe-a132HDSyd0U_g35f391192_00.png" width="480" />

[Slides: Finding AMRs](https://docs.google.com/presentation/d/1-orSi8DpN22hMt9-6p_rHZnte1YXXLe-a132HDSyd0U/edit?usp=sharing)

## Homework: Scientific Posters Activity

## Homework: r4ds


## Discussion: Finding AMRs Prelab

## Homework: Finding AMRs Project


## Activity: r4ds2


## Presentation: Finding AMRs Project
