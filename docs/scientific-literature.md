# (PART\*) Exploration and Discovery {-}

# Scientific Literature

## Lecture: What’s in Your XYZ?

![](scientific-literature_files/figure-docx//1ph3LFw6i_mtv6ZJXssTf0-im7PhgV4FRJslDG0ICCws_g35f391192_00.png)

[Slides: What's in Your XYZ?](https://docs.google.com/presentation/d/1ph3LFw6i_mtv6ZJXssTf0-im7PhgV4FRJslDG0ICCws/edit?usp=sharing)

## Activity: Taxonomy Profiling Spreadsheet

### Purpose

First hands-on experience with real data!  Compare kraken2 output for [Zymo Gut Microbiome Standard](https://www.zymoresearch.com/products/zymobiomics-gut-microbiome-standard?srsltid=AfmBOoqP_zq131c2GTidPCM0j6yA3JFcGQ0haUNu1jAJI9RQ9qsXLYSF) and [Zymo Human Fecal Reference](https://files.zymoresearch.com/protocols/d6323-zymobiomics_fecal_reference_protocol.pdf).  Introduce concepts of taxa and relationships, begin forming data analysis goals like comparing how many species, most abundant species, etc. See accompanying [slides](http://docs.google.com/presentation/d/16lpgWFU6jzh-e7HuwXLHmUFpsnE8NreMzL-nTn8cJVk).

### Learning Objectives

1. Explore taxonomy with Kraken 2 taxonomic assignment output.
2. Compare and contrast taxonomy between Zymo Gut Microbiome Standard and Zymo Human Fecal Reference.

### Introduction

Metagenomics is the direct analysis of the genomes through genome sequencing of an environmental sample (soil, water, gut, etc). The purpose of the taxonomic classification of metagenomic sequences is to catalogue, classify and  identify the species inhabiting a given environment. In the process, new species may get identified! After sampling, DNA extraction, DNA sequencing and genome assembly, genome annotation is used to assign taxonomy to the sequenced sample DNA. Here is where the Kraken 2 tool comes in; Kraken 2 is a taxonomic classification tool which assigns taxonomy to sequencing reads.

### Activity 1 – Explore Zymo Gut Standard Metagenomic Diversity

*Estimated time: 25 min*

#### Instructions

Perform the activity below and answer the embedded **questions**.

1. Access tax-data-gut.tsv and open with Google Sheets [here](http://drive.google.com/file/d/1vL6adVIrqxpONbae8rUsneK3tbdCpmR-)

2. Identify what information is provided in columns of the tax-data-gut taxonomy file.

- Col A = Counts

- Cols B-H correspond to taxonomic ranks k(Kingdom), p(Phylum), c(Class), o(Order), f(Family), g(Genus) and s(Species)

- Each row corresponds to a different taxa. There are 153 taxa that were classified for this sample.

3. Create a header row and enter column information.

#### Questions

1. Evaluate what proportion of data was taxonomically classified.

 a. Insert a new column A; we will use this temporary column for calculations, so you can name this column “Calculations”.

 b. In e.g. cell A2, calculate the sum of all reads observed in the gut std sample.  

| **How many total counts are there?** |
|:--|
| <br> |

c. In e.g. cell A3, determine the percentage of unclassified reads.

| **What percentage of reads are unclassified?** |
|:--|
| <br> |

d. In e.g. cell A4, determine the percentage of classified reads.

| **What percentage of reads are classified?** |
|:--|
|<br>|
<br>

2. Identify abundant taxa (those at >1%).

a. Select columns B through I
b. In the Data menu, select “Sort range by column B (Z to A)”
c. Insert a new column C; we will use this temporary column for calculations; you can name this column “% abundance”.
d. In new column C, calculate % abundance for each row by dividing each count value by the total number of reads and multiplying by 100.
e. Quantify abundant taxa.

| **How many abundant taxa (at >1%) do you observe?** |
|:--|
|<br>|
<br>

3. List abundant taxa you identified in a table below.

- To consolidate the different abundant taxa, in e.g. new column D, copy the lower taxonomic rank identified for the abundant (at >1%) taxa.
- Then, enter the results into a table below.

**What abundant taxa do you observe?**

| **% abundance** | Taxonomy |
|:--|:--|  
| 20.1 | s_Faecalibacterium_prausnitzii |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |
| | |

<br>

4. Compare your results with the expected taxa and abundance for [Zymo gut standard documentation](https://www.zymoresearch.com/products/zymobiomics-gut-microbiome-standard?srsltid=AfmBOor0X27Jf1gfXVmyGu5nZq3M6fx6OJXdEc0t6rqSRBPww2qeY-Yd)?

- Note, the Kraken2 output does not distinguish different *E. coli* strains, so just combine them all into a single *E. coli group*!

| **How do your results overall compare with the expected taxa and % abundance from Zymo gut standard?** |
|:--|
|<br>|
<br>

5. Calculate ‘Low abundance’ for < 1% abundant taxa by adding together taxa at <1%. 

|**What percentage of reads are classified in a low abundance taxa?**|
|:--|
|<br>|
<br>

6. Create a barplot of % abundance for your 12 abundant taxa via Insert Chart. 

|**Paste your barplot of % abundance for the 12 most abundant taxa **|
|:--|
|<br>|
<br>

### Activity 2 (OPTIONAL) – Compare with Zymo Fecal Reference

*Estimated time: 20 min*

#### Instructions

Perform the optional activity below and answer the embedded **questions**.

In this activity, repeat steps of the Activity 1 above, but now using [tax_data_fecal.tsv](http://drive.google.com/file/d/1CLQw9yqoqWl5caLm-ZmiHpLNtUo_Zo4s) dataset corresponding to Zymo fecal reference. The tax_data_fecal.tsv dataset comes from a real human fecal sample, in contrast to the tax_data_gut.tsv sample you explored in the Activity 1, which corresponds to cultured and pooled known species combined at specific proportions to make up a predictable standard population.

- Perform Activity 1 exercises using tax_data_fecal data, then, use questions below to compare the two datasets.
- See D6323 Zymo Fecal Microbiome References documentation (pg. 4) in the Resources section below.

#### Questions

|**1. Which dataset is classified better, gut or fecal??**|
|:--|
|<br>|

|**2. Are there any abundant taxa (at >1%) in common between the gut standard and fecal reference?**|
|:--|
|<br>|

|**3. In your opinion, does the gut standard mimic the fecal reference well or not?**|
|:--|
|<br>|

### Grading Criteria

- Download this assignment as Microsoft Word (.docx) and upload on Canvas
- Download your Google Sheet as Microsoft Excel (.xlsx) and upload on Canvas

### Footnotes

**Resources**

- Google Doc
- [D6331 Zymo Gut Microbiome Standard documentation](https://www.zymoresearch.com/products/zymobiomics-gut-microbiome-standard?srsltid=AfmBOor0X27Jf1gfXVmyGu5nZq3M6fx6OJXdEc0t6rqSRBPww2qeY-Yd)
- [D6323 Zymo Fecal Microbiome References documentation](https://files.zymoresearch.com/protocols/d6323-zymobiomics_fecal_reference_protocol.pdf?_gl=1*cych1b*_gcl_au*MzEzNzgzNjc0LjE3MzQ5NTk3NzY)

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Gauri Paul, Clovis Community College
- Frederick Tan, Johns Hopkins University

Last Revised: January 2025



## Activity: A short introduction to Galaxy

### Introduction

Galaxy [galaxyproject.org](galaxyproject.org) is a free, open-source system for analyzing data, authoring workflows, training and education, publishing tools, managing infrastructure, and more.  Among the notable features:

- [Graphical user interface](https://training.galaxyproject.org/training-material/topics/introduction/tutorials/galaxy-intro-101/tutorial.html) (GUI) for interactively running tools
- [Toolshed](https://toolshed.g2.bx.psu.edu/) with 10,000 tools ready to run
- Full featured [workflow](https://training.galaxyproject.org/training-material/topics/galaxy-interface/tutorials/workflow-editor/tutorial.html) functionality
- Terabytes of the latest, curated [reference data](https://galaxyproject.org/admin/reference-data-repo)
- Extensive training [tutorials](https://training.galaxyproject.org/) and infrastructure
- Large international [community](https://galaxyproject.org/community) of users and developers

### Activity

*Estimated time: 40 min*

#### Instructions

1. Review slides for “A short introduction to Galaxy”
- [training.galaxyproject.org/training-material/topics/introduction/tutorials/galaxy-intro-short/slides.html](training.galaxyproject.org/training-material/topics/introduction/tutorials/galaxy-intro-short/slides.html)
2. Complete the hands-on tutorial
- [training.galaxyproject.org/training-material/topics/introduction/tutorials/galaxy-intro-short/tutorial.html](training.galaxyproject.org/training-material/topics/introduction/tutorials/galaxy-intro-short/tutorial.html)

### Grading Criteria

- Submit URL to your shared Galaxy history on Canvas

### Footnotes

**Resources**

- Introduction to Galaxy Analyses [topic](https://training.galaxyproject.org/training-material/topics/introduction/)

**Contributions and Affiliations**

- Frederick Tan, Johns Hopkins University

Last Revised: January 2025



## Homework: Scientific Literature Prelab

### Purpose 

Obtain a high level overview of metagenomics by reading
R.D. Sleator, C. Shortall, and C. Hill.  Metagenomics.  Letters in Applied Microbiology. 2008 Nov;47(5):361-6. [(pubmed.gov/19146522)](http://pubmed.gov/19146522)

### Learning Objectives 

- Read a review paper that summarizes the field of metagenomics.
- Broadly understand the scope of the review and the gaps in the field. 

### Introduction 

The vast majority of all micro-organisms on Earch remain uncultured [(K.G. Lloyd et al, 2019)](https://journals.asm.org/doi/10.1128/msystems.00055-18). Additionally, in complex environments like soil and water, most micro-organisms remain unidentified [(M. Delgado-Baquerizo, 2019)](https://doi.org/10.1038/s41396-019-0405-0). The field of metagenomics is a culture-independend approach which aims to remedy these gaps in knowledge [(J. Handelsman, 2004)](https://pubmed.ncbi.nlm.nih.gov/15590779/). Metagenomics is the study of genomic (sequencing) data obtained directly from environmental (and other, e.g. clinical) samples and provides new meaningful information on the diversity and function of microorganisms.


### Activity

*Estimated time: 50 min*

#### Instructions

Read the review paper “Metagenomics” by Sleator, Shortall, and Hill, 2008 Lett Appl Microbiol and answer the following questions.

#### Questions

1. What is one thing you learned or find interesting in the paper?

2. Define a term that is new to you (e.g. metagenome, microbiome, 16S rRNA).

3. Ask a question about the review paper.


#### Grading Criteria

Download as Microsoft Word (.docx) and upload on Canvas


### Footnotes

**Resources**

[Google Doc](https://docs.google.com/document/d/1-ruTySaAnSE-_5d6_LTdre4UmmUAx6TxMrTYBW-f3jQ/edit?usp=sharing)

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Frederick Tan, Johns Hopkins University


## Discussion: Scientific Literature Prelab

### Activity

*Estimated time: 25 min*

#### Instructions

1. Form groups of four
- Add names to the "Microbial Mysteries Groups" sheet [https://docs.google.com/spreadsheets/d/11eoJgm9mehxGWWzh8IZYDCDmnCmSyshopPYHewvpC8c/edit?usp=sharing](https://docs.google.com/spreadsheets/d/11eoJgm9mehxGWWzh8IZYDCDmnCmSyshopPYHewvpC8c/edit?usp=sharing)
2. Pair up into groups (10 min)

a. Discuss -- Each group member briefly describes answers to prelab assignment

b. Summarize -- Identify best answer and add to slidedeck
[https://docs.google.com/presentation/d/1nuA_gnL09_BPZVNJy5seL-HWejhMFLqILsmgmQztYKo/edit?usp=sharing](https://docs.google.com/presentation/d/1nuA_gnL09_BPZVNJy5seL-HWejhMFLqILsmgmQztYKo/edit?usp=sharing)

3. Share group discussion (2 min each group)


## Lecture: Scientific Literature

![](scientific-literature_files/figure-docx//1zbjroITjBYmu-oxFT0qmOCx9LeEcSoaYrp_sWuy1OLM_g35f391192_00.png)

[Slides: Scientific Literature](https://docs.google.com/presentation/d/1zbjroITjBYmu-oxFT0qmOCx9LeEcSoaYrp_sWuy1OLM/edit?usp=sharing)

## Homework: Scientific Literature Activity

### Purpose

Examine research on metagenomic diversity by reading Xue, *et al*. Metagenome sequencing and 103 microbial genomes from ballast water and sediments. Scientific Data.2023 Aug 10;10(1):536. [(pubmed.gov/37563185)](https://pubmed.ncbi.nlm.nih.gov/37563185/)

### Learning Objectives
- Understand the purpose and experimental setup of the paper
- Understand the presented evidence (Figures and Tables) of the paper

### Introduction

Understanding microbial composition and diversity in different environments is critical for assessing the benefits and threats of the bacterial community in that environment.  In the publication by [Xue, et al. 2023](https://pubmed.ncbi.nlm.nih.gov/37563185/), the authors study microbial diversity in the ballast-tank water from two ships, with the idea that such a unique and isolated water environment may select for specific microbes.  Luckily in their research they don’t find bacterium *Vibrio cholerae*, but that is exactly what they would find in the ballast water of cargo ships if they did the analysis during the cholera pandemic(s) of the 1800s.

### Activity

*Estimated time: 90 min*

#### Instructions

Based on the study by Xue, et al.2023, answer the following questions.  The main text of the paper and the supplement can be found below, in the  'Resources' section of this assignment.

#### Overview of the Paper (in class)

Determine the main objectives and purpose of the paper. Read the Abstract and the introduction with your group.

1. What is the purpose of this study?

2. What is the hypothesis in this study?

3. Describe the knowledge gap. In essence, what did the scientific community not know that this study was trying to answer?


#### Methods (in class and homework)

1. Discuss how many and what samples were used for this study? Are there any replicates?

2. Discuss some methods used in this paper.

3. Discuss steps authors used to ensure their data is available to the public.

#### Figures (in class and Homework)

**Methods.** How did the researchers test their hypothesis? Explain in your own words the methods in each figure.

| Figure | Methods |
|:-|:-|
| Fig. 1B | in class |
| Fig. 1C | in class |
| Fig. 2 | homework |
| Fig. 3A | homework |
| Fig. 3B | homework |
| Fig. 3C| homework |


### Results (in class and Homework)

**Results.** What are the main findings from each figure?

| Figure | Main Findings |
|:-|:-|
| Fig. 1B | in class |
| Fig. 1C | in class |
| Fig. 2 | homework |
| Fig. 3A | homework |
| Fig. 3B | homework |
| Fig. 3C | homework |

#### Conclusions (Homework)

1. Read the discussion section. What were the main conclusions the authors made in this study?

2. Do the figures agree with their conclusion?

#### Future Directions (Homework)

1. Scientific work builds on previous studies. What do you believe could be the next step to further the work these researchers did? 
 - What follow-up question(s) do you have for the authors?

2. What is the impact of this research area in general (or this study in particular?)
- Do you believe further research in this area may benefit society? Can we build on what this study found?
- Do you think there are risks associated with such studies?

### Grading Criteria

- Download as Microsoft Word (.docx) and upload on Canvas.

### Footnotes

**Resources**

[Google Doc](https://docs.google.com/document/d/1kKnvMGq8jBfwKzC7W5YEJ7CtTgFNahAaDfV3LNknznM/edit?usp=sharing)

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Frederick Tan, Johns Hopkins University

## Presentation: Scientific Literature Activity

### Activity

*Estimated time: 25 min*

#### Instructions

1. Open the “Scientific Literature Presentation” slidedeck [here](https://docs.google.com/presentation/d/1wwfiTSgm0ialrYlBFnA21zdZsw7mVA58YPMiTnDGCrc/edit?usp=sharing)

2. For your assigned figure from Xue, et al., 2023, create two slides to present methods and results

a. Add bullet points on key details you understand (Notice) and questions you have (Wonder)

b. Search for and insert at least one additional image that relates to your figure

c. Update slide title to summarize your main takeaway

3. Present at next class (5 min each group)

### Footnotes

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Frederick Tan, Johns Hopkins University

Last Revised: January 2025

