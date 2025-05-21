
# (PART\*) Testing Ideas {-}

# Taxonomy Profiling

## Lecture: Taxonomy Profiling

![](resources/images/taxonomy-profiling_files/figure-docx//10P4ktKWSrRpM1YAWYW31tLly_jf1rcfgCMbzZ9Tx9xY_g35f391192_00.png)

[Slides: Taxonomy Profiling](https://docs.google.com/presentation/d/10P4ktKWSrRpM1YAWYW31tLly_jf1rcfgCMbzZ9Tx9xY/edit?usp=sharing)


## Homework: Taxonomy Profiling Prelab

### Purpose

To use a variety of Galaxy tools to perform Quality Control (QC), taxonomy profiling, and visualization of a metagenomics sample.

### Learning Objectives

Use Galaxy tools to:

1. Perform Quality Control (QC) on your raw data by checking the quality of your raw reads
2. Assign taxonomy labels to your reads
3. Visualize the classified metagenome

In this exercise, using Galaxy, you will be:

1. Using NanoPlot tool to examine the quality of your sequencing reads
2. Running a workflow to perform taxonomy profiling and visualization in a single step

### Introduction

To find out which microorganisms are present in the sample, it is important to have high-quality DNA sequences. To ensure high-quality sequence input, QC (and in many cases also read trimming and filtering) are routinely performed on raw sequences. The reads can then be used to determine which species, genera, families, and other taxonomic ranks are present in the sample. To assign taxonomy, we can compare the reads of the sample to a reference database, i.e. sequences of known microorganisms stored in a database, using Kraken2, which is a k-mer based taxonomic assignment tool. We can then use a tool like Krona to interactively visualize and explore the composition of a metagenome.  

### Activity 1 – QC Reads

*Estimated time: 50 min*

#### Activity 1 - Part I: Import dataset into Galaxy

*Estimated time: 15 min*

#### Instructions

1. Import dataset into Galaxy. 

a. Open the zymo-gut-standard public history [https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1](https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1) 

b. Click on **Import this history**, select Copy only the active, non-deleted datasets and then Copy History. 

c. Confirm <mark style="background color:green">Zymo_Gut_Standard_D6331_subset</mark> exists in your history by clicking on the Home button "Galaxy" on top left ().

d. Click on Zymo_Gut_Standard_D6331_subset to explore content.


#### Questions

|1. What is the size of this downloaded dataset subset?|
|:--|
| |
<break>

|2. What is the format/extension of the downloaded file?|
|:--|
| |
<break>

|3. Click on the Display (eyeball) icon and describe what you see in the 4 lines of the fastq file?| 
|:--|
|Line 1:| 
|Line 2:| 
|Line 3:| 
|Line 4:| 
<break>

#### Activity 1 - Part II: Run Nanoplot in Galaxy to assess sequence quality

*Estimated time: 15 min*

#### Instructions

1. Run Nanoplot in Galaxy. 

a) Explore NanoPlot tool parameters - click on the Tools icon on the left of the page. Then, in the search bar enter ‘NanoPlot’ and select the **NanoPlot** tool. Explore NanoPlot functionality via examining **Tool Parameters**.

b) Run NanoPlot using default settings. Under Tool Parameters, **check the following settings**:

- Under **files** there are 4 options to select a fastq dataset: Single dataset, Multiple datasets, Dataset collection or option '...' which is Browse or Upload Datasets. Browse to select your fastq dataset. **Note**, Galaxy tool may pre-select the correct dataset already for you so just make sure that the file is correct. 

- Click on Run Tool and wait ~5-10 minutes as the NanoPlot job is scheduled, run, and complete.

#### Questions

|1. Under **Type of file(s) to work on**, check to see which input files are compatible with NanoPlot and name 2 file extension options listed.|
|:--|
|File extension name 1:| 
|File extension name 2:| 
<br>

|2. Click to expand *Options for filtering or transforming input prior to plotting* and name 3 options you could use to filter your sequencing data.|
|:--|
|1.| 
|2.| 
|3.| 
<br> 

| 3. <mark style="background color:yellow">**Run Nanoplot**</mark> using default tool settings and record how many output files you obtained after running NanoPlot and list their names.| 
|:--|
| # of output files|
| Names of output files|
<br>  


#### Activity 1 - Part III: View NanoPlot Results in Galaxy

*Estimated time: 15 min*

#### Instructions 

1. View and examine NanoPlot Results in Galaxy. 

- By clicking on the Display icon (eyeball) next to the NanoPlot output.

#### Questions

1. Click on the Display icon (eyeball) next to the NanoPlot output files to view results.

| A. How many bases were sequenced?| 
|:--|
| |
<br>

| B. Why is mean read length longer than the median read length? - Hint: think skewness https://wikipedia.org/wiki/Skewness|
|:--|
| |
<br>

| C. Record Reads >Q20 metric value. Given that Q20 quality (Phred) score corresponds to read accuracy of 99% (or 1 in 100 errors), do you think this dataset is of a good sequence quality?|
|:--|
| |
<br>

2. Click on the Display icon (eyeball) next to the NanoPlot output HTML report. 

| A. Scroll down to view the ‘Weighted histogram of read lengths’ histogram. From this plot estimate the range of read lengths obtained| 
|:--|
| |
<br>

| B. Scroll down to view the ‘Yield by length’ cumulative plot which shows sequencing yield based on read length. From this plot do shorter (10kb or less) or longer sequences produce more data?| 
|:--|
| |
<br>


### Activity 2 – Taxonomy Profiling in Galaxy

*Estimated time: 50 min*

#### Activity 2 - Part I: Run ‘Taxonomy Profiling’ workflow in Galaxy

*Estimated time: 15 min*

#### Instructions

1.  Run ‘Taxonomy Profiling’ public workflow.

a. Open the taxonomy-profiling public workflow [https://usegalaxy.org/u/cutsort/w/taxonomy-profiling](https://usegalaxy.org/u/cutsort/w/taxonomy-profiling) and click on **Run**. 

b. Browse to select your fastq dataset by clicking on the ‘...’ tab.

c. Under **kraken_database** select <mark style="background color: green">‘Prebuilt Refseq indexes: PlusPF(Standard plus protozoa and fungi)(Version:2022-06-07 - Downloaded: 2022-09-04T165121Z).

d. Click **Run Workflow** with the following parameters:

e. Wait ~15-30 minutes as the Kraken2, KrakenTools, and Krona jobs are scheduled, run, and complete.

2. Examine select aspects of Kraken2 tool. 

a) While the Taxonomy Workflow is running, click on the Tools icon on the left of the page. 

b) Then, in the search bar enter ‘Kraken2’’ and select the **Kraken2** tool. 

#### Questions

| A. How  does Galaxy describe the Kraken2 tool in its descriptor on top of the page?| 
|:--|
| |
<br>

| B. Scroll down to **Help/What it does** section, and in your own words paraphrase the paragraph describing how Kraken 2 works.| 
|:--|
| |
<br>

| C. Record how many output files you obtained from the Taxonomy Workflow and list their names.| 
|:--|
| |
<br>


#### Activity 2 - Part II: View Kraken2 results

*Estimated time: 15 min*

#### Instructions

1. <mark style="background color: grey">Examine **converted_kraken_report**.

- Click on the Display icon (eyeball) next to the output file with **converted_kraken_report**. This report should look familiar from week 1 taxonomy-profiling-spreadsheet activity. 


#### Questions

1. Open and scroll through the **converted_kraken_report** report to answer the following questions: 

| A. How many Unclassified reads are there?| 
|:--|
| |
<br>

| B. How many Kingdoms are there and what are they?| 
|:--|
| |
<br>

| C. How many Phyla are there and what are they?| 
|:--|
| |
<br>

| D. Using the total *number_of_reads* you obtained from the **NanoStats** (NanoPlot) metrics, and the value of *Unclassified* reads from the **converted_kraken_report**, calculate % unclassified and % classified taxa.| 
|:--|
| |
<br>

| E. Click on the **converted_kraken_report** entry and just below the ‘Add Tags’ to see the number of lines and columns in the file. The number of lines corresponds to the number of taxa detected. Excluding Unclassified subset, how many taxa were identified?| 
|:--|
| |
<br>

2. Examine **kraken2_with_pluspf_database_output_report** by clicking on the Display icon (eyeball) next to the output file.

This output report is an extended version of the converted_kraken_report. The output contains 6 columns. See info for select column headers below:

- Column 1: Percentage (%) of a given taxon
- Column 2: # of reads per given taxon
- Column 4: A rank code, indicating (U)nclassified, (R)oot, (D)omain, (K)ingdom, (P)hylum, (C)lass, (O)rder, (F)amily, (G)enus, or (S)pecies. Note, that in this extended file, some rank codes will have numbers associated with them; Ignore this aspect of the document for the moment.
- Column  6: Identified taxa/scientific name.

| A. What is the percentage of Unclassified taxa listed? Does it match what you calculated in section 2-2.1?| 
|:--|
| |
<br>

| B. What is the percentage of Classified taxa listed? Does it match what you calculated in section 2-2.1?| 
|:--|
| |
<br>

| C. Find and record the 3 most abundant Phyla (p_) by percentages.  As rows are not sorted by abundance, you may find it helpful to search using for “P” using <CTRL>-F to highlight rows corresponding to phyla.| 
|:--|
| |
<br>

3. View Krona Results

Krona pie chart is one of the outputs of the Taxonomy workflow, and it is an interactive visualization tool for exploring the composition of metagenomes. Click on Display icon (eyeball) next to the **Krona_pie_chart** dataset to explore Krona pie chart results. 

![](resources/images/taxonomy-profiling_files/figure-docx//1hYKF7Ss3vJ8rrUIH7ByNh1BUlRa2fhsJhq8MXzEowCc_g336203e918d_0_0.png)

| A. What are the 2 main phyla you observe?| 
|:--|
| |
<br>

| B. What appears to be the more diverse phyla of the two and why?| 
|:--|
| |
<br>

| C. Examine how many reads and percent of reads classified as phylum Firmicutes.| 
|:--|
| |
<br>

| D. What is one of the most abundant Orders in phylum FIrmicutes based on number and % of reads?| 
|:--|
| |
<br>

| E. Within the most abundant Order from your answer above, record one Family member, one genus member and one species member; also include percent abundances.| 
|:--|
| |
<br>

| F. Some potentially pathogenic bacterial species are often present in a healthy gut, but at relatively low amounts. What % of bacteria is represented by *C. difficile* (*Clostridiodes difficile*) in this gut standard sample? How does it compare to the expected proportion in [ZymoBIOMICS® Gut Microbiome Standard](https://files.zymoresearch.com/datasheets/ds1712_zymobiomics_gut_microbiome_standard_data_sheet.pdf?_gl=1*1njkhlx*_gcl_au*MzE1NTQwNzEuMTczODI1OTA5OA..)?| 
|:--|
| |
<br>

### Grading Criteria

Download as Microsoft Word (.docx) and upload on Canvas

### Footnotes

**Resources**

- Google Doc
- Species composition in the Gut Microbiome Standard dataset: [ZymoBIOMICS® Gut Microbiome Standard](https://files.zymoresearch.com/datasheets/ds1712_zymobiomics_gut_microbiome_standard_data_sheet.pdf?_gl=1*1njkhlx*_gcl_au*MzE1NTQwNzEuMTczODI1OTA5OA..)
- If interested reading more about Kraken 2, see [Kraken 2 publication](https://pubmed.gov/31779668)

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Frederick Tan, Johns Hopkins University

Last Revised: February 2025


## Lecture: Possible Datasets

![](resources/images/taxonomy-profiling_files/figure-docx//1VxwSmAY8BUs3EfVcxPm3I8kNYJWjVqoHJrGOX3X3sog_g35f391192_00.png)

[Slides: Possible Datasets](https://docs.google.com/presentation/d/1VxwSmAY8BUs3EfVcxPm3I8kNYJWjVqoHJrGOX3X3sog/edit?usp=sharing)


## Homework: Possible Datasets Activity

### Activity

*Estimated time: 50 min*

#### Instructions

1. Skim three abstracts

2. Pick one and answer the following questions

a) Notice – What about this abstract most interests you?

b) Dataset – Summarize at a high level where the samples came from, how many there are, and what technology was used for sequencing.

c) Wonder – Two or three questions you would like to ask using this (and any other) datasets.

3. Post your answers by replying to the “Project Work: Possible Datasets” topic in the Discussion Forum

|Possible Datasets (Long-read PacBio)|
|:--|:--|:--|:--|
|**Soil**| | | |
| |Antarctic |PRJNA1126331 | pubmed.gov/39300163| 
| |Biocrust |PRJNA691698 | pubmed.gov/34795375| 
|**Water**| | | |
| |Fresh Water |PRJNA924152 | pubmed.gov/36823661| 

## Homework: Using dataset collections


## Discussion: Taxonomy Profiling Prelab


## Homework: Taxonomy Profiling Project

## Activity: Meet R!

## Presentation: Taxonomy Profiling Project

