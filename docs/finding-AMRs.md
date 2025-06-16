

# Finding AMRs

## Lecture: Finding AMRs

![](resources/images/finding-AMRs_files/figure-docx//165OHha9IYOctuyzg1CG0LwGxNnbC85JyJfMZT6xnYHw_g35f391192_00.png)

[Slides: Finding AMRs](https://docs.google.com/presentation/d/165OHha9IYOctuyzg1CG0LwGxNnbC85JyJfMZT6xnYHw/edit?usp=sharing)

## Pre-lab: Finding AMRs

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

**1. Run Flye in Galaxy** - using Zymo Gut Standard D6331 subset to assemble gut microbial genomes.

a. Obtain .fastq file from `Zymo_Gut_Standard_D6331_subset`: [https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1](https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1)

b. Name your new history **“Finding gut AMRs”**.

c. Run Flye tool to assess sequence quality using the following Tool Parameters:

- Under **Input Reads**: select your `Zymo_Gut_Standard_D6331` **.fastq** dataset.
- Under Mode: select `PacBio HiFi (--pacbio-hifi)` option, since the sequences were obtained using PacBio HiFi sequencing technology.
- Under **Perform metagenomic assembly**: select `Yes`
- Under **Generate a log file**: select `Yes`

![](resources/images/finding-AMRs_files/figure-docx//1hYKF7Ss3vJ8rrUIH7ByNh1BUlRa2fhsJhq8MXzEowCc_g33689793048_0_0.png)

![](resources/images/finding-AMRs_files/figure-docx//1hYKF7Ss3vJ8rrUIH7ByNh1BUlRa2fhsJhq8MXzEowCc_g33689793048_0_10.png)

**2. View Flye results** - Explore Flye output files and answer questions below.

![](resources/images/finding-AMRs_files/figure-docx//1hYKF7Ss3vJ8rrUIH7ByNh1BUlRa2fhsJhq8MXzEowCc_g33689793048_0_21.png)

#### Questions

**1. Explore Flye tool purpose and output.**

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
| *`At the very top of the log file you will find that the input number of bases was 177,760,975 (Look for Total read length). Compare to the total length after assembly from your answer to question 2A above`* |
|
| |
<br>

**3. Explore Flye assembly info file.**

|A. Based on your Flye output `assembly info file` sorted by contig length (high to low, in base pairs, bp) - What is the longest `contig size?|
|:--|
| |
<br>

|B. Based on your Flye output `assembly info file` sorted by contig length (high to low, in base pairs, bp) - What is the shortest contig size?|
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
|*`See this link for a quick summary comparison of the 2 formats [https://compgenomr.github.io/book/fasta-and-fastq-formats.html](https://compgenomr.github.io/book/fasta-and-fastq-formats.html)`*|
| |
<br>

**5. Test your general understanding of genome assembly.**

|A. Summarize your experience with assembling a genome with Flye.|
|:--|
| *`E.g., were you surprised at the percentage of assembled input, at the length of the largest contig, at the abundance of linear contigs, or anything else?`*|
| |
<br>

|B.  What would you want the ideal genome assembly tool to do?|
|:--|
| |
<br>

### Activity 2 – Visualizing contigs

*Estimated time: 15 min*

#### Instructions

Run **Bandage Image** tool in Galaxy on your Flye: **graphical fragment assembly** output (in gfa1 format) using default parameters.

#### Questions

|1. Paste the resulting image below.|
|:--|
| |
<br>

|2. Describe contig profile based on the Bandage Image.|
|:--|
| |
<br>

|3. Do you expect to obtain more contigs, larger or circular contigs with more sequencing reads? why?|
|:--|
| |
<br>

### Activity 3 – Finding AMRs

*Estimated time: 30 min* 

#### Instructions

1. Run **ABRicate** tool in Galaxy using Flye **consensus** as input using the following `Tool Parameters`:

- Under **Input Reads**: select your Flye: consensus output in FASTA format
- IMPORTANT: Under **Advanced Option**s: select `NCBI Bacterial Antimicrobial Resistance Reference Gene Database` as your database option; the default‘resfinder’ may not work well.

2. Explore **ABRicate report file**.

**Abricate output report** has the following information:

|Column |Description |
|:--| :--|
|FILE | The filename this hit came from |
| SEQUENCE | The sequence in the filename |
| START | Start coordinate in the sequence |
| END | End coordinate in the sequence |
| GENE | ABR gene name |
|COVERAGE | What proportion of the gene is in our sequence |
| COVERAGE_MAP | A visual represenation of coverage map (gaps or no gaps)|
| GAPS | Was there any gaps in the alignment - possible pseudogene? |
| %COVERAGE | Proportion of gene covered |
| %IDENTITY | Proportion of exact nucleotide matches |
| DATABASE | The database this sequence comes from |
| ACCESSION | The genomic source of the sequence |
<br>

3. Answer questions below.

#### Questions

**1. Explore Abricate output report.**

|A. How  many AMR genes were detected? This is the number of rows in your file|
|:--|
||
<br>

|B. How many DIFFERENT AMR genes were detected and what are their GENE names?|
|:--|
||
<br>

|C. What are the different AMR genes resistant to? What is their RESISTANCE? |
|:--|
||
<br>

|D. How many DIFFERENT contigs had AMRs? |
|:--|
||
<br>

**2. Research an AMR gene.**

|A. Research and write a small paragraph report on one of the AMR genes.| 
|:---|
| *`Use any search tools for your research, but we encourage you to use PubMed [https://pubmed.ncbi.nlm.nih.gov/](https://pubmed.ncbi.nlm.nih.gov/) where you can find many scientific articles on the topic if you search for e.g. your AMR gene name, or resistance name or using a sentence as input. Talk about anything of interest, e.g., which microbes have the AMR of interest, what is the substance to which the gene shows resistance to, where could the resistance to this substance come from, what are possible health implications, etc.`*|
| |
<br>

|B. Ask one question you want to know about AMRs?| 
|:---|
| |
<br>

### Grading Criteria

- <mark style="background-color: yellow">Download as Microsoft Word (.docx) and upload on Canvas

### Footnotes

**Resources**
- Google Doc

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Frederick Tan, Johns Hopkins University

Last Revised: May 2025




## Discussion: Finding AMRs

### Activity

*Estimated time: 25 min*

#### Instructions

1. Form new groups of four
- [https://docs.google.com/spreadsheets/d/11eoJgm9mehxGWWzh8IZYDCDmnCmSyshopPYHewvpC8c/edit?usp=sharing](https://docs.google.com/spreadsheets/d/11eoJgm9mehxGWWzh8IZYDCDmnCmSyshopPYHewvpC8c/edit?usp=sharing)

2. Pair up into groups (10 min)

a. Discuss -- Each group member briefly describes answers to prelab assignment

b. Summarize -- Identify best answer and add to slidedeck

- [https://docs.google.com/presentation/d/1ZC8yjuk8V5pt3yh1p4_jkhTw0Pu4mHViAmNF-UPWAHs/edit?usp=sharing](https://docs.google.com/presentation/d/1ZC8yjuk8V5pt3yh1p4_jkhTw0Pu4mHViAmNF-UPWAHs/edit?usp=sharing)

3. Share group discussion (2 min each group)


## Project: Finding AMRs

### Purpose

To explore soil metagenomics using Galaxy tools for de novo genome assembly (Flye), assembled contig visualization (Bandage),  finding antimicrobial resistance (AMR) genes (ABRicate) and binning contigs into larger groups/bins (MetaBAT2). You will also explore information about the taxonomic classifier GTDB-Tk.  This will allow you to compare genomic assemblies and AMRs between soil and Zymo gut standard.


### Learning Objectives

1. Use **Galaxy** tools to
2. Use **Flye** tool to perform de novo genome assembly of long reads into ‘contigs’ 
3. Visualize the contigs with **Bandage** visualization tool
4. Use **ABRicate** tool to find AMRs in contig assemblies
5. Use **MetaBAT2** to bin contigs into larger MAGs
6. Learn about **GTDB-Tk** taxonomy classifier tool

### Introduction

In this activity we will practice de novo genome assembly with Flye, using soil metagenomes from Nanopore sequencing . You will have an opportunity to compare and contrast assembled contigs and antimicrobial resistance profiles of soil and gut and think about the differences and similarities in microbial diversity of the two environments.
<br>
In this project you will also learn about MetaBAT2 and GTDB-Tk. Let's start now. The most up to date long read metagenomics workflow includes contig assembly (e.g. using Flye tool), followed by contig binning into larger metagenome-assembled genomes (MAGs) (with e.g. MetaBAT2 tool) and finally MAG classification (e.g. with GTDB-Tk). MetaBAT2 is an algorithm that bins (or groups) sequence fragments (contigs) into larger MAGs or draft genomes. Subsequently, MAGs can be taxonomically classified by GTDB-Tk.
<br>
`You will not be executing GTDB-Tk in this activity to stay within a reasonable activity time frame.` However, for your project work, you will have a chance to test GTDB-Tk on your genome assemblies and bins. A note to your future self working on a project - as a rule, after genome assembly, if your contigs are 500 kb or above, they will be considered large enough to be passed to GTDB-Tk without the need for binning. Contigs of < 500 kb will be binned and passed on to GTDB-Tk for taxonomy classification as bins.

**Table of approximate minimum times for a job to be completed on Galaxy using specified tools.** 
- Note, these times apply only to the specific input file we will be using in this activity, the nanopore-soil-subset that is 5.4 GB
| Flye | Bandage | ABRicate | MetaBAT2|
| :--|:-- |:--  | :-- | 
|5 hours | < 5 min | < 10 min | < 10 min|
<br>

### Activity 1 – Genome assembly with Flye

*Estimated time: 30 min (activity time DOES NOT include the Flye run time on Galaxy)*

#### Instructions

1. Run Flye in Galaxy on quality filtered (with fastp tool) nanopore soil pilot subset [nanopore-soil-subset-filtered](https://usegalaxy.org/u/valerie-g/h/nanopore-soil-subset-filtered) to de novo assemble soil microbial genomes. 

a. Obtain .fastq file from a subset of Nanopore-sequencing soil study

- [https://usegalaxy.org/u/valerie-g/h/nanopore-soil-subset-filtered]( [https://usegalaxy.org/u/valerie-g/h/nanopore-soil-subset-filtered)

b. Name your new history **“Finding soil AMRs”**

c. Run **Flye** tool to assess sequence quality using the following **Tool Parameters**

- Under **Input Reads**: select your nano `pore-soil-subset-filtered` **.fastq** dataset.
- Under **Mode**: select `--nano-raw` option, since the sequences were obtained using Nanopore sequencing technology.
- Under **Perform metagenomic assembly**: select `Yes`
- Under **Generate a log file**: select `Yes`

2. Explore Flye output **assembly info** file which is sorted by length (in base pairs, bp) of the contig (high to low). 

#### Questions 

| 1. How many contigs were assembled?|
|:-----|
|`Since each contig is represented by a separate row (or line) in the assembly info file, simply clicking on the assembly info file and recording the number of lines listed in the file will correspond to the number of contigs`|
| | 
<br>

| 2. What is the longest contig size?|
|:-----|
| | 
<br>

| 3. What percent of input was assembled into contigs? |
|:-----|
|- `Based on the log file, the input going into flye assembly was 6,103,654,873 bases.` 
- `Based on the log file, the output going of flye assembly was 154,251,885 bases` |
| | 
<br>

| 4. Why do you think only a small fraction of reads was assembled into contigs? |
|:-----|
| | 
<br>

**5. Compare soil assembly to the Zymo gut standard assembly provided the following observations:**

- For this activity you can consult back to your Prelab: Finding AMRs.
- The number of contigs assembled from **339.9 MB** of sequencing data from the Zymo gut standard D6331 subset was **265**, much smaller than for the filtered soil sample of 5.4 GB! Yet, the largest contig size for the Zymo gut standard was **2,158,044** (almost 9 times larger) and circular (while the largest contig for the soil sample was linear).

| 5A. Why do you think the number of contigs in the soil sample was so much higher than the number of contigs in the Zymo gut standard?  |
|:-----|
|- `Hint1 - it is NOT because of the difference in the size of the sequencing file` 
- `Hint2 - Think about possible differences in the microbial diversity of the two samples` |
| | 
<br>

| 5B. Why do you think it was possible to assemble a much larger and circular contig with the Zymo gut standard sample compared to the soil sample? |
|:-----|
| | 
<br>

## Presentation: Finding AMRs
