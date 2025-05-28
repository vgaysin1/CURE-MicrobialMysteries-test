
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
| |Antarctic |PRJNA1126331 | https://pubmed.gov/39300163/| 
| |Biocrust |PRJNA691698 | https://pubmed.gov/34795375/| 
|**Water**| | | |
| |Fresh Water |PRJNA924152 | https://pubmed.gov/36823661/|
| |Ocean Water |PRJNA853328 | https://pubmed.gov/36448813/|
|**Human Gut**| | | |
| |Vegan/Omnivore |PRJNA750084 | http://pubmed.gov/36289209|
| |Infant Nutrition |PRJNA1139951 | http://pubmed.gov/31022095|
|**and More!**| | | |
| |Lamb Gut |PRJNA595610 |http://pubmed.gov/34980911|
| |Deadwood |PRJNA603240 | http://pubmed.gov/39627869|
| |Cheese |PRJNA778418 | http://pubmed.gov/9948695|
| |Whey |PRJNA454439, PRJNA477604 | http://pubmed.gov/6593500 |
<br>

### Grading Criteria

- Submit URL to your reply on Canvas

### Footnotes

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Frederick Tan, Johns Hopkins University

Last Revised: May 2022

## Homework: Galaxy data collections

### Introduction

Collections in Galaxy can be useful when you have to deal with large numbers of datasets.  Examples of when you might use collections include when you have many DNA sequencing samples (e.g. .fastq files) or when you have many genome assembly contigs (e.g. .fasta files).  Dataset collections allow you to not only organize these datasets but they also allow you to manipulate them in a single batch operation.

### Activity

*Estimated time: 45 min*

#### Instructions

1. Review the “Datasets versus collections” FAQ

- [training.galaxyproject.org/training-material/faqs/galaxy/histories_datasets_vs_collections.html](http://training.galaxyproject.org/training-material/faqs/galaxy/histories_datasets_vs_collections.html)

2. Complete the “Using dataset collections” hands-on tutorial

- [training.galaxyproject.org/training-material/topics/galaxy-interface/tutorials/collections/tutorial.html](http://training.galaxyproject.org/training-material/topics/galaxy-interface/tutorials/collections/tutorial.html)

### Grading Criteria

- <mark style="background color: yellow">Submit URL to your shared Galaxy history on Canvas

### Footnotes

**Resources**

- Using Galaxy and Managing your Data [topic]

**Contributions and Affiliations**

- Frederick Tan, Johns Hopkins University

Last Revised: January 2025



## Discussion: Taxonomy Profiling Prelab

### Activity

*Estimated time: 25 min*

#### Instructions

1. Form new groups of four
- [https://docs.google.com/spreadsheets/d/11eoJgm9mehxGWWzh8IZYDCDmnCmSyshopPYHewvpC8c/edit?usp=sharing](https://docs.google.com/spreadsheets/d/11eoJgm9mehxGWWzh8IZYDCDmnCmSyshopPYHewvpC8c/edit?usp=sharing)

2. Pair up into groups (10 min)

a. Discuss -- Each group member briefly describes answers to prelab assignment

b. Summarize -- Identify best answer and add to slidedeck

- [https://docs.google.com/presentation/d/16cRBFzezun6MGXcJEm5uP2KercIccO-dFvVx58_ClNo/edit?usp=sharing](https://docs.google.com/presentation/d/16cRBFzezun6MGXcJEm5uP2KercIccO-dFvVx58_ClNo/edit?usp=sharing)

3. Share group discussion (2 min each group)

### Footnotes

**Contributions and Affiliations**

- Valeriya Gaysinskaya, Johns Hopkins University
- Frederick Tan, Johns Hopkins University

Last Revised: February 2025



## Homework: Taxonomy Profiling Project

### Purpose

To use a variety of Galaxy tools to perform Quality Control (QC), sequence quality filtering, taxonomy profiling, and visualization of a metagenomics soil sample sequenced with long-read Nanopore technology.

### Learning Objectives

In this exercise, using Galaxy tools you will be
1. Performing QC and quality filtering of your soil metagenomics data with NanoPlot and fastp tools.
2. Running a workflow to perform taxonomy profiling and visualization of a soil metagenome.

Throughout these objectives you will be comparing soil and gut metagenomes.

###Introduction 

The total time for a Galaxy step to complete depends on and will increase based on multiple factors such as large input file size, long queue when many other people are analyzing data, the complexity of the job itself, or an error. See table below for the minimum time a step will take for this assignment – be sure to start early as when Galaxy is busy each step can take 2-to-10 times longer to complete. 
<br>

Note, that you can save time by 1) submitting multiple jobs that use the same input (NanoPlot and fastp) and 2) submitting a job like the taxonomy workflow that uses the fastp output as input as soon as the output appears in your history even before the fastp job finishes.

Table of approximate minimum times for a job to be completed on Galaxy using specified tools.

|Nanoplot| fastp | taxonomy workflow |
|:--|:--|:--|
|15 min| 15 min | 30 min | 
<br>

### Activity 1 – QC and quality-filter reads

*Estimated time: 50 min*

#### Activity 1 - Part I: Import data and run NanoPlot in Galaxy

#### Instructions

1. Import dataset into Galaxy. 

a. Open the nanopore-soil-pilot public history [https://usegalaxy.org/u/valerie-g/h/nanopore-soil-pilot-1](https://usegalaxy.org/u/valerie-g/h/nanopore-soil-pilot-1)

b. Click on `Import this history`, select Copy only the active, non-deleted datasets and then Copy History. 

c. Confirm <mark style="background color: green">Nanopore-soil-pilot-subset</mark> exists in your history by clicking on the Home button on top left ().

2. Run **NanoPlot** tool in Galaxy to assess sequence quality using **default settings**.

a. Click on the Tools icon. Then, in the search bar enter ‘NanoPlot’ and select the NanoPlot tool. 

b. Under **files** browse to select your Nanopore-soil-pilot-subset fastq dataset.

c. Click on **Run Tool** and wait ~10 minutes as the NanoPlot job is scheduled, run, and complete.

#### Questions

|1.  Click on the Display icon (eyeball) next to the NanoPlot output NanoStats report and record:|
|:--|
|Read mean length (mean read length):|
|Read Mean quality (mean_qual):|
|Proportion of reads with quality > Q20 (Reads > Q20):|
<br>

|2.  Compare your NanoPlot results. |
|:---|:---|:---|
| | **Nanopore soil pilot (this activity)** | **Zymo gut standard (taxonomy profiling pre-lab)** |
| mean read length:|  |  |
| mean_qual:|  |  |
| Reads > Q20:|  |  |
<br>

|3. Which dataset has better sequence quality, Zymo-gut-standard (taxonomy profiling pre-lab) or Nanopore-soil pilot (taxonomy profiling project)?Why?|
|:---|
| | 
<br>

#### Activity 1 - Part II: Quality filtering with fastp

#### Instructions

Although the majority of bases in the soil dataset are of high quality ( >Q20, or 1 in 100 base error), we can filter out very low quality reads to further improve dataset quality. In this activity run fastp tool to filter out reads with a high proportion of low quality bases (<Q15) using default settings.

a. Click on the Tools icon. Then, in the search bar enter **fastp** and select the fastp tool. 

b. Click on **Run Tool** and wait ~10 minutes as the fastp job is scheduled, run, and complete. 

#### Questions

|1.  Compare your dataset before and after filtering using fastp: HTML report output.| | |
|:--|:--|:--|
|| **Before** | **After**|
|Mean Length| | |
|total reads| | |
|total bases|  | |
|Q20 bases (%):|  | |
|Q30 bases (%):|  | |
<br>

|2. Compare BEFORE and AFTER quality plots from activity above. What key quality improvement can you observe after fastp quality filtering|
|:--|
|- look at 5’ end, 3’ end and the middle?| 
| - Pay attention to the y-axis|
| | 
<br>

## Activity 2 – Taxonomy Profiling

*Estimated time: 50 min (~35 min computing)*

### Activity 2 - Part I: Run Taxonomy Profiling Workflow

#### Instructions

1. Run ‘Taxonomy Profiling’ workflow on your fastp-filtered data from Activity 1 and view results.

a. Open the taxonomy-profiling public workflow [https://usegalaxy.org/u/cutsort/w/taxonomy-profiling](https://usegalaxy.org/u/cutsort/w/taxonomy-profiling)

b. Click on Run 

c. Browse to select your fastp-filtered fastq dataset <mark style="background color: green">“fastp on data1:Read 1 output”</mark> dataset by clicking on the `‘...’` tab.

d. Under **kraken_database** select <mark style="background color: green">‘Prebuilt Refseq indexes: PlusPF(Standard plus protozoa and fungi)(Version:2022-06-07 - Downloaded: 2022-09-04T165121Z).

d. Click **Run Workflow**

3. Wait ~15-30 minutes as the Kraken2, KrakenTools, and Krona jobs are scheduled, run, and complete.


2. Click on the Display icon (eyeball) next to the output file with converted_kraken_report. Explore metagenomic diversity of soil by performing taxonomy profiling spreadsheet activity you did during week 1. 

a. Click on **converted_kraken_report**, find the download button and **download** the report.

b. <mark style="background color: yellow">Change the extension of your taxonomy file from .tabular to .tsv.

c. Upload your taxonomy .tsv file to Google Drive and open with Google Sheets.

d. Create a header row and enter column Information.

- Col A = Counts
- Cols B-H correspond to taxonomic ranks k(Kingdom), p(Phylum), c(Class), o(Order), f(Family), g(Genus) and s(Species).
- Each row corresponds to a different taxa. 

e. Evaluate what proportion of data was taxonomically classified.
- Insert a new column A; we will use this temporary column for calculations, so you can name this column “Calculations”.
- In e.g. cell A2, calculate the sum of all reads observed in the soil  sample. 

#### Questions

|1. How many total read counts are there?|
|:---|
||
<br>


|2. Determine percentage of reads that are unclassified| 
|:---|
||
<br>

|3. What percentage of reads are classified?| 
|:---|
||
<br>

4. **Identify the most abundant taxa (those at >0.1%).**
Remember, soil is one of the most diverse microbial environments with many more microbial species than in the gut. Therefore, abundant species can still be quite low abundance.

a. Select columns B through I

b. In the Data menu, select “Sort range by column B (Z to A)”

c. Insert a new column C; we will use this temporary column for calculations; you can name this column “% abundance”.

d. In new column C, calculate % abundance for each row by dividing each count value by the total number of reads and multiplying by 100.

|How many ‘abundant ‘taxa (at > 0.1%) do you observe?|
|:---|
||
<br>

|5. What are the taxonomic ranks of most abundant taxa?| 
|:---|
||
<br>

|6. What is the most abundant eukaryote observed and its read count?| 
|:---|
||
<br>


|7. What is the most abundant archaea observed and its read count?| 
|:---|
||
<br>

|8. What is the most abundant virus observed and its read count?| 
|:---|
||
<br>


### Activity 2 - Part II: Analyze Kraken2 results

#### Instructions

Click on the Display icon (eyeball) next to the output file with **kraken2_with_pluspf_database_output_report**. This output report is an extended version of the converted_kraken_report. The output contains 6 columns. See info for select column headers below:

- Column 1: Percentage (%) of a given taxon
- Column 2: # of reads per given taxon
- Column 4: A rank code, indicating (U)nclassified, (R)oot, (D)omain, (K)ingdom, (P)hylum, (C)lass, (O)rder, (F)amily, (G)enus, or (S)pecies. Note, that in this extended file, some rank codes will have numbers associated with them; Ignore this aspect of the document for the moment.
- Column  6: Identified taxa/scientific name.

#### Questions

|1. What is the percentage of Unclassified taxa? Does it match your calculations in Activity 2 - Part I?| 
|:---|
||
<br>

|2. What percentage of bacteria is Proteobacteria, the most abundant Phyla observed?|
|:---|
||
<br>

`Note: The benefit of kraken2_with_pluspf_database_output_report is that it summarizes converted_kraken_report and calculates summary percentages for taxonomic ranks. For example, your converted_kraken_report has 352 lines for phylum Proteobacteria, while kraken2_with_pluspf_database_output_report has 1 line summarizing the percent abundance of all Proteobacteria.` 

|3. What is the most abundant class observed and at what percentage?|
|:---|
||
<br>

### Activity 2 - Part III: Krona Pie Chart

#### Instructions

## Activity: Meet R!

## Presentation: Taxonomy Profiling Project

