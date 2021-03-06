### Automated-Factor-Aanalysis
 - What is Factor Analysis ?
Factor Analysis (FA) is It is a useful tool for studying the variable relationships of complex concepts (such as socio-economic status, eating habits or psychological scales)
 - Why it is used ?
It allows  to study concepts that are difficult to measure directly by combining a large number of variables into several potential interpretable factors.

There are two main forms of FA: Exploratory and confirmatory FA.  
   Exploratory FA is to discover relationships between manifest variables and factors.  
   Confirmatory FA tests if the hypithesis given by Exploratory FA is true or not. 
   
 - Business Problem : If you use in your daily life an amount number of varibles in order to solve a problem, do classification, .... And you don't know yet which varibles are more pertinent in solving that problem, then this solution is for you !! 
###### How does it work ? 

The pipeline steps are as below:

1. Adequacy Checks : 

First of all our FA should be verified, to do so 2 tests are availble : 
   - Bartlett Sphericity Test: A check of intercorrelation between manifest variables.
   - The KMO Test (Kaiser-Meyer-Olkin) : Test if it is appropriate to use the manifest variables for factor analysis
  
Returned result : Returns Valid if the two test are valid, and returns Not Valid if the two tests are not valid or either one of them

2. Apply Exploratory Factor Analysis:

   1. Finds the initial number of factors 
   2. Apply Fcator analysis with the initial number of factors and does iteratations in order to find the final number of factors 
   3. Retur the cumulative variance explained by the factors
   4. Return final results : The final factors and variables + cummilative variance explained
 
3. Apply Exploratory Factor Analysis:

   1. Creates a model with the result of the Exploratory Factor Analysis
   2. Does an Confirmatory Factor Analysis 
   3. Returns the result: Confirmed if the test confirms the results of the Exploratory Factor Analysis or Not Confirmed in the other case

4. Predictions time :

 This part is for classifications problems, if we have already found the most pertinent variables and wants to know their efficiency in classification tasks.
 This part uses AutoML, it takes the varibles that we got from FA and tests the efficny of the factors to predict using a target variable !
   1. Trains the models 
   2. Retunrns a leaderboard with all models sorted, best first 
   3. Runs predictions automatcly with the best model 
   4. You can explore results of the model 

There are three files : 

**config.py**: Contains all the configurations to enter that are used by the functions. 
**preprocessor.py**: Contains all the functions to be executed
**pipeline.py**: The execution file

In ordee to  use the code you just need to download the file "Code", go to your command and type : 
```
python pipeline.py
```
### Deployment of the solution
In this part we used TKinter to transfrom the pipeline to a usable solution.

In ordee to transform the solution to an executable exe file type : 
```
pyinstaller --onefile  pipeline.py
```
Otherwise just use : 
```
python pipeline.py
```
A little sneak peek to the solution : 

The exe file generated : 

![](images/generated_exe_file.png)

Here you will be uploading your excel file for example : 

![](images/upload_data.png)

You will be then directed to the configurations interface when you'll be selctiong variables ypu want to perform FA with, rotation type, .. 

![](images/FA_configurations.png)

Main interface of FA:  

![](images/FA_interface.png)

An example of an output of Adequacy checks : 

![](images/Result_of_adequacy_checks.png)

Configurations of AutoMl :

![](images/AutoMLconfigurations.png)


AutoMl main interface:

![](images/AUTOML_main.png)

AutoMl Results:

- Leadboard :

![](images/leadboard_AutoML.png)

- Model performance on training

![](images/performance_of_the_model_on_training.png)


