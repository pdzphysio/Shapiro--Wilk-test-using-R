# Shapiro--Wilk-test-using-R
# R code and function for applying Shapiro- Wilk test to group A followed by Group B BMI readings to check if data in the groups are normally distributed.
##############################
# Program to Shapiro- Wilk test
# Written by Prajakta Zambare
# Date 04/03/2017
# USAGE: Rscript <ttest.R>
##############################


#### FUNCTIONS #############################
shapiro_test <- function(dataframe) {
	for(i in 1:ncol(df)){
	ans <- shapiro.test(df[ ,i])
	if (ans[2]>0.05) {
		cat("Data in the", i, "is normally distributed \n")
		}
	else {
		cat("Data in the", i, "is not normally distributed")
		quit()
		}
	} 	
	print("Data passes Shapiro Test!!!!!!!!")
}

############## START #######################
# Collect data into dataframe
df <- read.csv("BMI.csv")
# Run shapiro test on two columns
shapiro_test(df)
