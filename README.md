# NYC-Open-Data-Profiling-and-Cleaning

Created for CSGY 6513 Big Data Final Project Part 2.

---

**Steps to Reproduce:**

1.	Login to Peel and create a new working directory and clone/copy all the project files there.

2.	Run the script *run_part1.sh* by calling `./run_part1.sh` in the shell. This will submit spark job for each of the dataset.

3.	Once all the spark jobs are finished, the Original and Cleaned sample of each Dataset will be available in the current working directory.
	Named as [DatasetID]Original.csv and [DatasetID]Output.csv

4.	To calculate precision and recall of the above sample data, follow the "Steps to calculate accuracy" given below separately.
	
	Improvements were made on the original script based on above results, to run the improved script on all datasets following step 5: 

5.	Run the script *run_part2.sh* by calling `./run_part2.sh` in the shell. This will output entire cleaned datasets to HDFS with filenames as <DatasetID>Cleaned.out 

---

**Steps to calculate accuracy:**

1. Follow steps 1 to 3 in the "Steps to Reproduce"

2. Copy output csv files to local machine and open in spreadsheet software of your choice.

3. Manually inspect and compare the Original and Output file of each dataset to calculate the effectiveness of cleaning approach.
   Use following method to calculate precision and recall:
		Precision = True Positive Count/True Positive Count + False Positive Count
		Recall = True Positive Count/True Positive Count + False Negative Count
---

Team:

Syed Ahmad 				- st4324@nyu.edu

Suyash Soniminde		- sys8910@nyu.edu

Viha Gupta 				- vg2237@nyu.edu
