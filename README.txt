###############################################################################
README

TNER2: Tri-Nucleotide Error Reducer 2

TNER2 is a novel background error suppression tool that provides a robust 
estimation of background noise to reduce sequencing errors using tri-nucleotide 
context data for better identification of low frequency somatic mutations in
ctDNA (Circulating tumor DNA).

Version: 2.1
Last updated: 08/17/2019
Contact: shibing.deng {at} pfizer.com or tao.xie {at} pfizer.com / xietao2000 {at} gmail.com
Contributed by: Shibing Deng, Joy Hsu, Jadwiga Bienkowska, Paul Rejto and Tao Xie.
Pfizer Early Clinical Development Biostatistics
Pfizer Early Oncology Development and Clinical Research
Copyright (c) 2019 Pfizer Inc.
###############################################################################

Pre-requisites/Installation:
----------------------------
Download and install R (version 3.2 or later)
Download and install PERL (version 5.8 or later)
Download and install the TNER packge and unzip the files

----------------------------
Test the TNER2 function using the demo dataset
----------------------------
"Rscript TNER_main.R TNER_example_input_file.txt hs_ave_bg_error.csv hs_depth.csv hs_adj.csv"

Note: “TNER_example_input_file.txt” is the example input data to be analyzed; the 2nd argument (default:
“hs_ave_bg_error.csv“) is a csv file with the average background error rate from healthy subjects; the
last argument (default: “hs_depth.csv”) is a csv file with the base coverage in healthy subjects.  The 
last input parameter (TNER2 only) is the file with values for threshold adjustment based on known cancer TNC 
data derived from a decay function (described in a manuscript currently under review).

----------------------------
Build background error profile using "Create_background_error_rate.R” 
----------------------------
"Rscript Create_background_error_rate.R"

Note: "Create_background_error_rate.R” creates an average background error rate file from individual healthy 
subject data (should be stored in the subfolder named as "healthy_subjects", file format is as same as 
"TNER_example_input_file.txt". The function outputs “hs_ave_bg_error.csv” and “hs_depth.csv” for the main 
function “TNER_main.R”. 


----------------------------
Process pileup files for TNER using pileup2actg.pl
----------------------------
"perl pileup2actg.pl 

Note: this perl script processes a pileup file to generate a tab-delimated txt file for function
“TNER_main.R”.


----------------------------
Citation
----------------------------
TNER2 (under review)
