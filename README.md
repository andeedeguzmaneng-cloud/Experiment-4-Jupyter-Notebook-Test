# Experiment-4-Jupyter-Notebook-Test

This repository contains a Jupyter Notebook with one solved Python experiment:

	1. ECE BOARD EXAM PROBLEM (Data Wrangling and Visualization)

The notebook demonstrates how to load a dataset (`board.csv`), clean and process the data using Pandas, create filtered DataFrames, and visualize results with Matplotlib and Seaborn. 

Each part is explained with code, outputs, and syntax definitions. It also includes step-by-step instructions on how to get started with Jupyter Notebook in Anaconda and how to upload your completed work to GitHub.

_____________________________________

Getting Started with Jupyter Noteboook

To begin creating your Python code using Jupyter Notebook:

1. Open **Anaconda Navigator** on your computer.  
2. Look for **Jupyter Notebook** and open it.  
3. Once Jupyter Notebook launches in your browser, you can create a folder to keep all your Jupyter files organized.  
4. Open the folder where you want to save your work.  
5. Click the **New** button (top-right).  
6. From the dropdown, select **Python 3 (ipykernel)**.  

A new Jupyter Notebook will open and now you can start writing and running your Python code!

_____________________________________


IMPORTING THE LIBRARY

Before starting with the experiment, the following Python libraries must be imported:

	1. Pandas → for reading CSV files and creating/manipulating DataFrames.  
 	2. Matplotlib → for generating plots.  
  	3. Seaborn → for creating styled visualizations. 

--- CODE ---

	[]: import pandas as pd    #
	[]: import matplotlib.pyplot as plt
	[]: import seaborn as sns

Problem: ECE BOARD EXAM PROBLEM
                         - This program loads board.csv, calculates the Average grade, creates three filtered DataFrames (Vis, Instru, Mindy), and generates a barplot showing subject contributions to the average.

---- CODE ---

1. Load dataset and compute Average
   
		ECE BOARD EXAM PROBLEM                                                                                   # Markdown heading for the problem
		[]: df = pd.read_csv("board.csv")                                                                        # Read the CSV file (board.csv) into a DataFrame
	 	[]: df["Average"] = df[["Math", "Electronics", "GEAS", "Communication"]].mean(axis=1)                    # Create a new column "Average" which is the mean of Math, Electronics, GEAS, and Communication per student
		[]: print("=== NEW ROW OUTPUT: First 5 rows of dataset after preprocessing ===")display(df.head())       # Show the first 5 rows of the dataset after preprocessing

2. Create DataFrames
   
		# --- Vis DataFrame ---
		# Condition: Students with Math < 70
		# Columns: student name and Math
 
	 	[]: Vis = df[df["Math"] < 70][["student name", "Math"]] 
  
		# --- Instru DataFrame ---
		# Condition: Students with Electronics > 70
		# Columns: student name, GEAS, Electronics
 
  		[]: Instru = df[df["Electronics"] > 70][["student name", "GEAS", "Electronics"]] 
   
		# --- Mindy DataFrame ---
		# Condition: Students with Average >= 55
		# Columns: student name, Electronics, Average  
 
   		[]: Mindy = df[df["Average"] >= 55][["student name", "Electronics", "Average"]]
   
3. Visualization 

		# Create a barplot showing how each subject contributes to the Average
		[]: print("\n=== NEW ROW OUTPUT: Barplot - Contribution of Subjects to Average ===")

		[]: plt.figure(figsize=(10,6))                                                             # Set figure size
		[]: subject_means = df[["Math", "Electronics", "GEAS", "Communication"]].mean()            # Calculate mean score of each subject
		[]: sns.barplot(x=subject_means.index, y=subject_means.values)                             # Crtitleeate barplot with subject means
		[]: plt.ylabel("Average Score")                                                            # Add labels
		[]: plt.title("Contribution of Each Subject to Overall Average")                           # Add title
		[]: plt.show()                                                                             # Display the plot


--- EXECUTION / RUNNING THE CODE ---

To execute a code cell in Jupyter Notebook:

	1. Click inside the cell.
 	2. Press Shift + Enter or click the Run button in the toolbar.
 	3. The output (table or plot) will appear directly below the cell.

Types of outputs you may see:

	1. Normal Output (table) → when a DataFrame is printed.
 	2. Graphical Output (plot) → when a barplot or chart is displayed.
  	3.Error Message → a red message shown when the code has a mistake or a variable is undefined.


--- OUTPUT ---

The notebook produces the following outputs:

	1. Preview → First 5 rows of dataset with the computed Average.
	2. Vis DataFrame → Displays students with Math < 70.
	3. Instru DataFrame → Displays students with Electronics > 70.
	4. Mindy DataFrame → Displays students with Average ≥ 55.
	5. Barplot → Shows how Math, Electronics, GEAS, and Communication contribute to the overall average score.

--- DEFINITON OF SYNTAX USED ---

	1. pd.read_csv("filename") → loads data from a CSV file into a DataFrame.
	2..mean(axis=1) → computes the row-wise average across selected columns.
	3.df[condition] → filters rows that satisfy a condition.
	4. [["col1", "col2"]] → selects specific columns from the DataFrame.
	5. sns.barplot() → creates a bar plot of averages.
	6. plt.ylabel() → labels the y-axis.
	7. plt.title() → sets the title for the plot.
	8. plt.show() → displays the plot.
 
Now that you’re done with all the problems, the next step is to upload your Jupyter Notebook file to GitHub so it can be saved, shared, and accessed easily.

--- PROCEDURE FOR UPLOADING TO GITHUB ---

        1. After finishing all problems in the Jupyter Notebook, click File → Download as → Notebook (.ipynb) to save the file on your computer.
        2. Open your web browser and go to GitHub.
        3. Sign in to your GitHub account.
        4. On the top-right, click the + (plus) button and choose New repository.
        5. Enter a Repository Name (for example: Experiment-1-Jupyter-Notebook-Test).
        6. Turn on "Add a README file" so the repository starts with a description.
        7. Click Create repository.
        8. Once inside the repository, click Add file → Upload files.
        9. Click Choose your files and select the Jupyter Notebook file (.ipynb) you downloaded.
        10. Scroll down and click Commit changes to upload it.

Now your Jupyter Notebook is saved and viewable in your GitHub repository. 
