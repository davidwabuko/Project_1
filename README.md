# PROJECT_1
# AIR CRASH INVESTIGATION
**Authored by: DAVID .W. MUKOLWE**
# Air crash investigation: 
will focus on analyzing the accidents from the dataset:
 link to dataset:
https://www.kaggle.com/datasets/khsamaha/aviation-accident-database-synopses

The Dataset contains the following files:

- Aviation.csv
- USState_codes.csv

working with this data will give a great incite and understanding on patterns inloving Airborne accidents.

Aviation.csv' contains relevant 'columns' and 'rows' of elements to help us analyze the data better, 'USState_codes.csv' is a 'list' of states within the UnitedStates as keys and their abbreviations as keyvalues ('say for example,the state 'Arizona is abbreviated 'AZ')
ith the information  available in the files AIR-CRASH INVESTIGATION will clean,model,analyze,visualize and eventually provide solutions for problems in a working business enviroment.

AIR-CRASH INVESTIGATION will look to solve the Business problem:(AVIATION-ACCIDENTS) by use of data recorded from previous similar events over a number of years

The business will have a better view of:- 
- Factors contributing to Airborne accidents
- Type/Nature of most common Airborne accidents
- Location most prone to Airborne accidents
- Rare occurences where it was Incidents and not accidents

# Looking Into The Data
Before we work with data in .csv files we first load it into memory and Read into the data.

read the required csv files and assign the variable df.
To get a preview  run .head( ) , this will display the first 5 rows of the DataFrame.

once the data files are read they are stored in our memory unless the python envitoment is shut down, the data is ready for cleaning,analysis and visualization.The steps of manipulating the data follows the steps as they are stated.

# DATA CLEANING
# sort the data into relevant rows and columns
 - The dataset contains very many irrelevant columns and rows that are not of use, only relant columns and rows are filtered out.

# filtering relevant columns:
 - out of all the columns the system chooses only a few that will be used to analyze our data

Assigning Filtered columns to our DataFrame df.

# 1.Which make has the most damage:-

within the new DataFrame their is a column for 'Make' and 'Aircraft.damage'. Create a variable: 'make_with_most_damage', to this variable assign values of the DataFrame grouped by 'Make' and 'Aircraft.damage'. Carry out this action by running the .groupby( ) and  within the parenthesis of the command add .size( ).reset_index( ), inside the parenthesis of reset_index add the name for a new column that will be created for counting values of damage quoted 'Destroyed'

only colums of  'Make',  'Aircraft.damage'  and a newly created column of  Destroyed.count  is displayed. Prooceed to visualizing the data. First assign the list values under 'Make' column a new variable  'makes',   do same action for list values in column  'Destroyed.count'  and assign a new variable  'destroyed_counts'

# visualization:-
#              #
The most suitable visualization will be a bar graph,

- 'makes'  will be the X values in a bar graph while   'destroyed.counts'  will make the Y values.

- Title for the bar graph is  'Aircraft Damage by Make'

- X and Y labels will be names of the columns we were dealing with initially this is 'Make'  and 'Destroyed.count' respectively
  
![f3e9a5ce-8b42-48e5-a75b-6d16f90f0142](https://github.com/davidwabuko/Project_1/assets/170512794/296b94fa-20f1-4d21-a1df-b0d99e48ac8d)


# 2.Which make has had the most accidents whike which have the least:-

- First check to ensure data to know the values of 'Make' we are working with and their actual count.

- From the .value_counts( ) output we can see our data is not uniform contains both uppercase and lowercase charactersv mixed up therefore some cleaning has to be done to make this uniform, we will make all characters lowercase using the command .lower( )

- Inspect for null values by running command *.isnull( ).sum( )* this will display all null values in the  'Make' column
Once null values are known they must be dropped inorder to make it easier to work with our relevant column['Make']  Values

After cleaning all Null values run *.groupby( )* to group the columns that we are analyzing, adding *.size( ).reset_index* to groupby command will initiate a new column with the specified name in this case we want to know the number of accidents so we will name the column Accident.count

Sorting the values by 'ascending=false' will rearrange them and list the values in order from one with highest count to the lowest count. 
From the cleaned data create new variables for 'Makes' and 'Accident.count' and assign them the  corresponding values from the columns that are in use
the new variable will offer relevant points for plotting.
# Visualizing:-

![7c83de08-b298-4347-943d-472fae50949a](https://github.com/davidwabuko/Project_1/assets/170512794/cd784cd3-94a2-471e-a393-18cc1ac34879)

# 3.Take a look at comparing Make of the Aircraft to Purpose of flight to know which Aircraft were booked more for corporate Trips :

For this relationship columns to be used are 'Purpose.of.flight' and 'Make' for us to know the make of flight that went on more Executive/Corrporate flights

Clean this column first as it contains alot of Null values which will lead to not receiving correct output if used without modifying and getting rid of the null values.

- For this use .isnull( ).sum( ) to view the total number of null values
Now that we know all our null values go ahead to drop them inorder to work with clean data
use .notna( ) or .dropna( ) in their correct parameters to eliminate the null values
 The column we are using in the data frame has been cleaned and null values eliminated
Run  the groupby ( ) function to group the columns that are relevant for this analysis that is 'Make' and 'purpose.of.flight assigning the group to a new variable created called: 'make_with_most_Eflights'

- By adding .size( ).reset_index( ) at the end of groupby the code creates a new column with the name specified, say in this case 'Executive/corporate.count
sort the values to see from top count to the least count
use functon .sort_values specyfying count name and ascending= False

# Vizualize

![da3b240d-3cb3-4852-adff-d5a2e0ac6d6d](https://github.com/davidwabuko/Project_1/assets/170512794/5a119c19-e97e-4315-b4e9-7e9546139dd1)
# THE END.



