# Clunker-Spotting
Machine Learning Application with R (Random Forest, XGBoost)

Executive Summary (All tables and visualizations are shown in PDF file)
[Clunker Spotting Report.pdf](https://github.com/EvanaZhang/Clunker-Spotting/files/9805210/Clunker.Spotting.Report.pdf)


Business Problem

In today’s society, more and more people have an increasing demand for second-hand cars, and more and more business institution starting focus on selling used cars. The most obvious reason is that it can save you a lot of money instead of buying a new car. However, some merchants have also noticed that although used cars have a wider market in terms of customer demand than new cars, they also need to pay more attention to some details and reduce returns to help customers buy the cars they need faster and more conveniently.
This project will use the construction of a random forest model and XGBoost model to point out the key to the high possibility through identifying used cars that are likely going to be bad purchases or crappy cars before they end up on CarVana’s website for sale. Furthermore, according to the analysis of the data, there’s around 12% of the information in this data set count as bad purchases.


Key Findings

By comparing all the vehicle ages and vehicle years, any used cars with an age larger than 5 and a vehicle buy year that earlier than 2005 has a higher possibility for impacting the target variable more.
• Wheel type ID is a significant variable for predicting the target variable, especially the wheel type ID with “0” has the highest possibility to identify the used cars that are likely going to be bad purchases with a possibility which is higher than 25%.
• Any variables besides ID, Purch date, model and sub-model are all significant for further predicting the target variable with a rate of at least higher than 85%.


Model Performance Summary & Interpretation

This dataset has total 36 variables which includes 19 numeric variables, 16 character variables and 1 datetime variable. The first step is check dataset profile by using skim() function, and then check the percentage of with or without bad purchases by presenting as a target frequency table and classification graph. Next, explore the relationship between each of the categorical variables and numeric variables to see if each of them is being impactful and significant enough for building the models or further predicting. The final step before the partition target variable “is_bad_buy” to and other character variables (auction, make, trim, color, transmission, wheel type, wheel type ID, nationality, size, top three American name, primeunit, aucguart, vnst, quality code) before building the models.
     
     XGBoost Modeling
     
     • Set the number of trees as 20
     • Randomly tuned three parameters (tree depth, min_n, and learning rate) with different  sizes of 10
     • The best and the most reasonable XGBoost model will be the model with 15 tree depth, 22 minimum number of variables and a learning rate of 0.02316152. (See Detailed Analysis & Steps Table 1)
      
      Radom Forest Modeling
      
      • Randomly tuned 2 parameters to a total of 10 different size: tree values with a range of 100 to 200 and min_n with no range.


      Combine & Compare Two Models
      
      • Tree depth determines the depth of the trees; the min_n indicates the minimum number of variables and the learning rate manifests the coefficient when tuning.
      • By comparing the ROC_AUC and the accuracy from both XGBoost and Random Forest models, random forest model will fit the data more. That’s why using the random forest model to do the kaggle prediction with a higher value on both accuracy and roc_auc. (See Detailed Analysis and Steps Table 4 and Figure 1)


Recommendations

• Based on the key findings and the top 10 important predictive variable that impact the target variables in Table 3, the company should consider to focus on the wheel type, wheel type ID, and vehicle cost depends on customer needs to determine whether they make a good or bad purchase.
• The company should also primarily focus on the vehicle age and year that on sale. They might check those used cars whether driving for more than 5 years and bought earlier than 2005 to lower the possibility of customer purchase the car they don’t want to buy.

