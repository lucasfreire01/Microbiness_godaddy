# Microbiness_godaddy
This project will predict potential cities that can use the Godaddy as the last project made before I started to do a preprocess using pandas, numpy, KNN(for outliers), label encoder to transform categorical values in numeric values, then concatenate this dataset with train dataset and, of course, did again the preprocess in order to deliver the data in the best possible way to the model.
I have these dataset: Train(Train dataset for model), Test(test dataset for model), reveled(this dataset I decided concat with train dataset because have values seen the train dataset and I believe this values add can help the model) and submission_format(the format for submission) this code I don’t make the submission because the time’s up. The first think I did was make the preprocess changing the missing values for median next to identify the outlier with KNN and take these values median. This dataset have a lot of columns  working this way each acronym have 5 years and each variation means a column for exemple pct_bb_2017, 18, 19, 20,21 each year mean a column. Then I grouped this column in 5 brig columns each column with the mean between the 5 years. the census Dataset have this column
  
  pct_bb_2017, pct_bb_2018, pct_bb_2019, pct_bb_2020,<br>
  pct_bb_2021, cfips, pct_college_2017, pct_college_2018,<br>
  pct_college_2019, pct_college_2020, pct_college_2021,<br>
  pct_foreign_born_2017, pct_foreign_born_201',pct_foreign_born_2019,<br>
  pct_foreign_born_2020,pct_foreign_born_2021, pct_it_workers_2017, <br>
  pct_it_workers_2018,pct_it_workers_2019, pct_it_workers_2020, pct_it_workers_2021,<br>
  median_hh_inc_2017, median_hh_inc_2018, median_hh_inc_2019,median_hh_inc_2020, median_hh_inc_2021
  
The census_dataset in the final has this co0lumns:<br>
  cfips, pct_bb_mean, pct_college_mean, mean_hh_inc,<br>
  pct_foreign_born_mean, pct_mean_worked.<br>

Next, We started treating the train dataset first we took the reveled_dataset had additional data integrated with the train dataset, and then built a strategy for the census dataset to join with the train dataset, The census got almost 3200 rows and the training dataset got almost 122000 as we know if we put the mean or median or content imputation is unfeasible because the distribution will be so affected, using KNN or nearest neighborhood get the same problem because the amount missing value quickly the nearest is the seen the before nearest, model predictions to predict missing values will be the same problem, the strategy used was to do a kind of oversampling doing a lot of copies of the dataset solve the missing values and keep the distribution.<br>

Finally, the train dataset has 14 columns the columns of the dataset before and others columns  CFIPS(A unique identifier for each county using the Federal Information Processing System. The first two digits correspond to the state FIPS code, while the following 3 represent the county.), county_name, State_name, first_day_fo_moth(this column I split into 3 columns day, year and month) microbusiness_density (Microbusinesses per 100 people over the age of 18 in the given county. This is the target variable. The population figures used to calculate the density are on a two-year lag due to the pace of updates provided by the U.S. Census Bureau, which provides the underlying population data annually. 2021 density figures are calculated using 2019 population figures, etc. [This is the column target]), active(The raw count of micro-businesses in the county. Not provided for the test set). If you’d a description the project description at GitHub can help you.
To build the model we trained with XGBosstRegressor and we had an accuracy of 96.74% tried RandomFlorestRegressor the accuracy got 98.62%. I decided to use the RandomFlorestRegressor the MAE was 0.09.
