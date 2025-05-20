
# (PART\*) Testing Ideas {-}

# Taxonomy Profiling

## Lecture: Taxonomy Profiling

<img src="resources/images/taxonomy-profiling_files/figure-html//10P4ktKWSrRpM1YAWYW31tLly_jf1rcfgCMbzZ9Tx9xY_g35f391192_00.png" width="480" />

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

Import dataset into Galaxy. 

a. Open the zymo-gut-standard public history [https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1](https://usegalaxy.org/u/valerie-g/h/zymo-gut-standard-d6331-subset-1) 

b. Click on **Import this history**, select Copy only the active, non-deleted datasets and then Copy History. 

c. Confirm <mark style="background color: lightgreen">Zymo_Gut_Standard_D6331_subset</mark> exists in your history by clicking on the Home button "Galaxy" on top left ().

d. Click on Zymo_Gut_Standard_D6331_subset to explore content.


#### Questions

|1. What is the size of this downloaded dataset subset?|
|:--|
|<break>|

|2. What is the format/extension of the downloaded file?|
|:--|
|<break>|

|3. Click on the Display (eyeball) icon and describe what you see in the 4 lines of the fastq file?| 
|:--|
|Line 1:| 
|Line 2:| 
|Line 3:| 
|Line 4:| 
|<break>| 

#### Activity 1 - Part II: Run Nanoplot to assess sequence quality

*Estimated time: 15 min*

#### Instructions

In Galaxy, click on the Tools icon on the left of the page. Then, in the search bar enter ‘NanoPlot’ and select the **NanoPlot** tool. Explore NanoPlot functionality via examining **Tool Parameters**.

#### Questions

|**1. Under **Type of file(s) to work on**, check to see which input files are compatible with NanoPlot and name 2 file extension options listed.**|
|:--|
|File extension name 1:| 
|File extension name 2:| 
<br>

|**2. Click to expand *Options for filtering or transforming input prior to plotting* and name 3 options you could use to filter your sequencing data.**|
|:--|
|1.| 
|2.| 
|3.| 
<br> 

3. <mark style="background color: yellow">**Run Nanoplot**</mark> using default tool settings. Under Tool Parameters, **check the following settings**:

- Under **files** there are 4 options to select a fastq dataset: Single dataset, Multiple datasets, Dataset collection or option '...' which is Browse or Upload Datasets. Browse to select your fastq dataset. **Note**, Galaxy tool may pre-select the correct dataset already for you so just make sure that the file is correct. 
- Click on Run Tool and wait ~5-10 minutes as the NanoPlot job is scheduled, run, and complete.

|**Record how many output files you obtained after running NanoPlot and list their names.**| 
|:--|
<br>  


#### Activity 1 - Part III: View NanoPlot Results

*Estimated time: 15 min*

#### Instructions and Questions

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


### Activity 2 – Taxonomy Profiling

*Estimated time: 50 min*

#### Activity 2 - Part I: Run ‘Taxonomy Profiling’ workflow

*Estimated time: 15 min*

#### Instructions

1. Run ‘Taxonomy Profiling’ public workflow

a. Open the taxonomy-profiling public workflow [https://usegalaxy.org/u/cutsort/w/taxonomy-profiling](https://usegalaxy.org/u/cutsort/w/taxonomy-profiling)

b. Click on **Run** 

c. Browse to select your fastq dataset by clicking on the ‘...’ tab.

d. Under **kraken_database** select <mark style="background color: green">‘Prebuilt Refseq indexes: PlusPF(Standard plus protozoa and fungi)(Version:2022-06-07 - Downloaded: 2022-09-04T165121Z).

e. Click **Run Workflow** with the following parameters

2. Wait ~15-30 minutes as the Kraken2, KrakenTools, and Krona jobs are scheduled, run, and complete.


## Lecture: Possible Datasets

<img src="resources/images/taxonomy-profiling_files/figure-html//1VxwSmAY8BUs3EfVcxPm3I8kNYJWjVqoHJrGOX3X3sog_g35f391192_00.png" width="480" />

[Slides: Possible Datasets](https://docs.google.com/presentation/d/1VxwSmAY8BUs3EfVcxPm3I8kNYJWjVqoHJrGOX3X3sog/edit?usp=sharing)


## Homework: Possible Datasets Activity


## Homework: Using dataset collections


## Discussion: Taxonomy Profiling Prelab


## Homework: Taxonomy Profiling Project

## Activity: Meet R!

## Presentation: Taxonomy Profiling Project

