# Microbiness_godaddy
This project will predict potential cities that can use the Godaddy as the last project made before I started to do a preprocess using pandas, numpy, KNN(for outliers), label encoder to transform categorical values in numeric values, then concatenate this dataset with train dataset and, of course, did again the preprocess in order to deliver the data in the best possible way to the model.
I have these dataset: Train(Train dataset for model), Test(test dataset for model), reveled(this dataset I decided concat with train dataset because have values seen the train dataset and I believe this values add can help the model) and submission_format(the format for submission) this code I don’t make the submission because the time’s up. The first think I did was make the preprocess changing the missing values for median next to identify the outlier with KNN and take these values median. This dataset have a lot of columns  working this way each acronym have 5 years and each variation means a column for exemple pct_bb_2017, 18, 19, 20,21 each year mean a column. Then I grouped this column in 5 brig columns each column with the mean between the 5 years. the census Dataset have this column
  
  pct_bb_2017, pct_bb_2018, pct_bb_2019, pct_bb_2020,
  pct_bb_2021, cfips, pct_college_2017, pct_college_2018,
  pct_college_2019, pct_college_2020, pct_college_2021,
  pct_foreign_born_2017, pct_foreign_born_201',pct_foreign_born_2019,
  pct_foreign_born_2020,pct_foreign_born_2021, pct_it_workers_2017, 
  pct_it_workers_2018,pct_it_workers_2019, pct_it_workers_2020, pct_it_workers_2021,
  median_hh_inc_2017, median_hh_inc_2018, median_hh_inc_2019,median_hh_inc_2020, median_hh_inc_2021
  
The census_dataset in the final have this co0lumns:
  cfips, pct_bb_mean, pct_college_mean, mean_hh_inc,
  pct_foreign_born_mean, pct_mean_worked.
Next I concatenated this dataset with the train dataset again doing the preprocess this time just remove missing values and put this places the mean each column. Finally the train dataset have 14 columns the colsumns of the dataset before and others columns  CFIPS(A unique identifier for each county using the Federal Information Processing System. The first two digits correspond to the state FIPS code, while the following 3 represent the county.), county_name, State_name, first_day_fo_moth(this column I split in 3 columns day, year and month) microbusiness_density (Microbusinesses per 100 people over the age of 18 in the given county. This is the target variable. The population figures used to calculate the density are on a two-year lag due to the pace of update provided by the U.S. Census Bureau, which provides the underlying population data annually. 2021 density figures are calculated using 2019 population figures, etc. [This is the column target]), active(The raw count of microbusinesses in the county. Not provided for the test set). If you’d a description biggest the preject description at GitHub can help you.
For build the model we train with XGBosstRegressor and we have a accuracy to 96,10% and try also RandomFlorestRegressor the accuracy got 99,38%. I decided to use the RandomFlorestRegressor the MAE was 0.04.
