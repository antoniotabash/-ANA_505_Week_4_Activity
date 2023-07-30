# -ANA_505_Week_4_Activity
ANA_505_Week_4_Activity_With_dplyr_package
#Week 4: dplyr package

#Task: Write the code to get a dataset from Base R: ChickWeight
#and save it as a dataframe with a new name that includes your first name
ChickWeight
antonio_chickweight<-ChickWeight

#See the top rows of the data
#TASK: Write the code to see the top rows of the data
head(antonio_chickweight)

#Install and call the package dplyr
#TASK: Write the code to install and call dplyr
install.packages(pkgs="dplyr")
library("dplyr")

#Let's just see the weight and Time columns
#Task: Write the code to 'select' just the weight and Time columns 
#(hint: use the 'select' function)
antonio_chickweight%>%select(weight,Time)

#Let's name the dataset with just the two columns, weight and Time
#TASK: Write the code to save the two columns as a new dataframe
#and give it a new name
chickweight_weight_time<-antonio_chickweight%>%select(weight,Time)

#Let's get rid of the Time column in the new dataframe created above
#TASK: Write the code that deselects the Time column
#(hint: use the 'select' function to not select a -column)
chickweight_weight_time%>%select(-Time)

#Let's rename a column name
#TASK: Write the code that renames 'weight' to 'ounces'
antonio_chickweight%>%rename(ounces=weight)

#Let's make a new dataframe with the new column name
#TASK: Write the code that names a new dataframe that includes the 'ounces' column
antonio_chick_ounces<-antonio_chickweight%>%rename(ounces=weight)

#Let's 'filter' our dataframe to only those with a 1 in the Chick column
#TASK: Write the code that includes only rows where Chick = 1
antonio_chickweight%>%filter(Chick==1)

#Let's 'group' our data by Diet
#TASK: Write the code to group the data by Diet (hint: group_by)
antonio_chickweight%>%group_by(Diet)

#Task: add one of the other codes (not in the tasks above) 
#you learned about from the dplyr package
#I will create two codes just in case
antonio_chickweight%>%group_by(Diet)%>%summarise(mean_weight=mean(weight))
antonio_chickweight%>%relocate(Time,.before = weight)
