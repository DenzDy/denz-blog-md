- refers to the transformation of data before feeding it into the model
- deals with the techniques that are used to convert **unusable raw data** into **clean reliable data**
## Four Components of Data Preprocessing
- the raw data
- a tidy data set (processed data)
- code book describing each variable and its values in the tidy data set
- An explicit and exact recipe that you used
### Raw Data
- original data source
- often difficult to use for data analyses
- Examples:
	- binary file
	- JSON data
- Raw data is in the right format if you:
	- ran no software on the data
	- did not manipulate any of the numbers in the data
	- did not remove any data from the dataset
	- did not summarize the data in any way
### The Tidy Data
- data that is ready for analysis
- each variable you measure should be in one column
- each different observation of that variable should be in a different row
- There should be one table for each "kind" of variable (e.g., 1 table for data from Twitter, another for Facebook)
- If you have multiple tables, they should include a column in the table that allows them to be linked
- Other tips:
	- Include a row at the top of each file with variable names
	- Make variable names human readable (e.g., AgeAtDiagnosis instead of AgeDx)
	- Data should be saved in one file per table
### The Code Book
- information about the variables (including units) in the dataset not contained in the tidy data
- information about the summary choices you made
- information about the experimental study design you used
- Other tips:
	- A common format for this document is a word/text file
	- there should be a section called "study design" that has a thorough description of how you collected the data
	- There must be a section called "code book" that describes each variable and its units
### The Instruction List
- ideally a computer script (in R or Python)
- the input for the script is the raw data
- the output is the processed, tidy data
- there are no parameters to the script
- in some cases when it will not be possible to script every step, provide step-by-step instructions
