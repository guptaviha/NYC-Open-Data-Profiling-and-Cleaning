# NYC Payroll Data Cleaning Part2

An academic project for Big Data (CS-GY-6513) at NYU Tandon with Prof Juliana Freire.

Objective: To scale profiling and cleaning techniques used from Part1 to handle a large number of files, found using [NYC Open Data](https://opendata.cityofnewyork.us/)

Part 1 of the Project which contains Jupyter Notebooks for Profiling and Cleaning of NYC Citywide Payroll data can be found [here](https://github.com/guptaviha/Data-Cleaning-NYC-Payroll-Part1)

For more details: [Prompt](https://github.com/guptaviha/Data-Cleaning-at-Scale-Part2/blob/main/Project-Prompt.pdf) & [Report](https://github.com/guptaviha/Data-Cleaning-at-Scale-Part2/blob/main/Project_Report.pdf)

---

## Steps to Reproduce

1.	Login to Peel and create a new working directory and clone/copy all the project files there. Then navigate to *code* folder.

2.	Run the script *run_part1.sh* by calling `./run_part1.sh` in the shell. This will submit spark job for each of the dataset.

	NOTE: If facing permission denied error on running above command, run the following - `chmod 777 run_part1.sh`

3.	Once all the spark jobs are finished, the Original and Cleaned sample of each Dataset will be available in the current working directory.
	Named as [DatasetID]Original.csv and [DatasetID]Output.csv

4.	To calculate precision and recall of the above sample data, follow the "Steps to calculate accuracy" given below separately.
	
	Improvements were made on the original script based on above results, to run the improved script on all datasets following step 5: 

5.	To calculate precision and recall of improved script run command `./run_part2subset.sh` This will behave same as run_part1.sh and output both original and cleaned csv of dataset samples. Follow Step 4 to calculate precision and recall using the output.

	NOTE: If facing permission denied error on running above command, run the following - `chmod 777 run_part2subset.sh`

6.	Run the script *run_part2.sh* by calling `./run_part2.sh` in the shell. This will output entire cleaned datasets to HDFS with filenames as [DatasetID]Cleaned.out 

	NOTE: If facing permission denied error on running above command, run the following - `chmod 777 run_part2.sh`


---

## Steps to calculate accuracy

1. 	Follow steps 1 to 3 in the "Steps to Reproduce"

2. 	Copy output csv files to local machine and open in spreadsheet software of your choice.
	You can use WinSCP or SCP command with following syntax -  `scp <netID>@<peelurl>:/file/to/send /where/to/put`

3. 	Manually inspect and compare the Original and Output file of each dataset to calculate the effectiveness of cleaning approach.
	
	Use following method to calculate precision and recall:
		
		Precision = True Positive Count/True Positive Count + False Positive Count
		
		Recall = True Positive Count/True Positive Count + False Negative Count
---

## Reference Data creation

The folder *Reference Data* contains Refrence data for Nonprofit names in NYC as well as PySpark script to create the same.
Steps to create:

1.	Goto *ReferenceData* directory in Peel

2.	Run `spark-submit createReferenceData.py`

3. 	Download result by running `hfs -getmerge NonprofitNameReferenceDataset.csv NonprofitNameReferenceDataset.csv`


## Contributers:

Syed Ahmad - st4324@nyu.edu

Suyash Soniminde - sys8910@nyu.edu

Viha Gupta - vg2237@nyu.edu
