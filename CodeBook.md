# Code Book

This code book summarizes the resulting data fields in `final_tidy_data.txt`.

## Data Source
The original data was collected from the accelerometers from wearing a smartphone (Samsung Galaxy S II). A full description is available at the site where the data was obtained:
https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones

## Data Cleaning Steps
The script `run_analysis.R` performs the following steps to clean the data:

1.  **Download and Merge:**
    * The training and test datasets were merged to create one data set.
    * Target files: `X_train.txt`, `X_test.txt`, `y_train.txt`, `y_test.txt`, `subject_train.txt`, and `subject_test.txt`.

2.  **Extract Mean and Standard Deviation:**
    * Only the measurements on the mean and standard deviation for each measurement were extracted.
    * Columns were selected if they contained the substrings `mean` or `std`.

3.  **Descriptive Activity Names:**
    * The activity identifiers (integers 1-6) were replaced with descriptive activity names taken from `activity_labels.txt` (e.g., WALKING, SITTING).

4.  **Label Variables:**
    * The following acronyms in variable names were replaced to make them more descriptive:
        * `^t` -> `Time` (Prefix)
        * `^f` -> `Frequency` (Prefix)
        * `Acc` -> `Accelerometer`
        * `Gyro` -> `Gyroscope`
        * `BodyBody` -> `Body`
        * `Mag` -> `Magnitude`
        * `angle` -> `Angle`
        * `gravity` -> `Gravity`
        * `tBody` -> `TimeBody`
        * `mean` -> `Mean`
        * `std` -> `STD`
        * All periods and ellipses were removed from the column names


5.  **Create Tidy Data Set:**
    * From the intermediate dataset, a final tidy dataset was created where the data was grouped by `subject` and `activity`.
    * The final output contains the **average** (mean) of each variable for each activity and each subject.

## Variables

### Identifiers
* **subject**: The ID of the test subject. Integer ranges from 1 to 30.
* **activity**: The type of activity performed when the corresponding measurements were taken. 
    * `WALKING`
    * `WALKING_UPSTAIRS`
    * `WALKING_DOWNSTAIRS`
    * `SITTING`
    * `STANDING`
    * `LAYING`

### Measurements
All measurements are floating-point values. The values in the final dataset represent the **average** of the original readings for that group.

* "TimeBodyAccelerometerMeanX"                     
* "TimeBodyAccelerometerMeanY"                     
* "TimeBodyAccelerometerMeanZ"                     
* "TimeGravityAccelerometerMeanX"                  
* "TimeGravityAccelerometerMeanY"                  
* "TimeGravityAccelerometerMeanZ"                  
* "TimeBodyAccelerometerJerkMeanX"                 
* "TimeBodyAccelerometerJerkMeanY"                 
* "TimeBodyAccelerometerJerkMeanZ"                 
* "TimeBodyGyroscopeMeanX"                         
* "TimeBodyGyroscopeMeanY"                         
* "TimeBodyGyroscopeMeanZ"                         
* "TimeBodyGyroscopeJerkMeanX"                     
* "TimeBodyGyroscopeJerkMeanY"                     
* "TimeBodyGyroscopeJerkMeanZ"                     
* "TimeBodyAccelerometerMagnitudeMean"             
* "TimeGravityAccelerometerMagnitudeMean"          
* "TimeBodyAccelerometerJerkMagnitudeMean"         
* "TimeBodyGyroscopeMagnitudeMean"                 
* "TimeBodyGyroscopeJerkMagnitudeMean"             
* "FrequencyBodyAccelerometerMeanX"                
* "FrequencyBodyAccelerometerMeanY"                
* "FrequencyBodyAccelerometerMeanZ"                
* "FrequencyBodyAccelerometerMeanFreqX"            
* "FrequencyBodyAccelerometerMeanFreqY"            
* "FrequencyBodyAccelerometerMeanFreqZ"            
* "FrequencyBodyAccelerometerJerkMeanX"            
* "FrequencyBodyAccelerometerJerkMeanY"            
* "FrequencyBodyAccelerometerJerkMeanZ"            
* "FrequencyBodyAccelerometerJerkMeanFreqX"        
* "FrequencyBodyAccelerometerJerkMeanFreqY"        
* "FrequencyBodyAccelerometerJerkMeanFreqZ"        
* "FrequencyBodyGyroscopeMeanX"                    
* "FrequencyBodyGyroscopeMeanY"                    
* "FrequencyBodyGyroscopeMeanZ"                    
* "FrequencyBodyGyroscopeMeanFreqX"                
* "FrequencyBodyGyroscopeMeanFreqY"                
* "FrequencyBodyGyroscopeMeanFreqZ"                
* "FrequencyBodyAccelerometerMagnitudeMean"        
* "FrequencyBodyAccelerometerMagnitudeMeanFreq"    
* "FrequencyBodyAccelerometerJerkMagnitudeMean"    
* "FrequencyBodyAccelerometerJerkMagnitudeMeanFreq"
* "FrequencyBodyGyroscopeMagnitudeMean"            
* "FrequencyBodyGyroscopeMagnitudeMeanFreq"        
* "FrequencyBodyGyroscopeJerkMagnitudeMean"        
* "FrequencyBodyGyroscopeJerkMagnitudeMeanFreq"    
* "AngleTimeBodyAccelerometerMeanGravity"          
* "AngleTimeBodyAccelerometerJerkMeanGravityMean"  
* "AngleTimeBodyGyroscopeMeanGravityMean"          
* "AngleTimeBodyGyroscopeJerkMeanGravityMean"      
* "AngleXGravityMean"                              
* "AngleYGravityMean"                              
* "AngleZGravityMean"                              
* "TimeBodyAccelerometerSTDX"                      
* "TimeBodyAccelerometerSTDY"                      
* "TimeBodyAccelerometerSTDZ"                      
* "TimeGravityAccelerometerSTDX"                   
* "TimeGravityAccelerometerSTDY"                   
* "TimeGravityAccelerometerSTDZ"                   
* "TimeBodyAccelerometerJerkSTDX"                  
* "TimeBodyAccelerometerJerkSTDY"                  
* "TimeBodyAccelerometerJerkSTDZ"                  
* "TimeBodyGyroscopeSTDX"                          
* "TimeBodyGyroscopeSTDY"                          
* "TimeBodyGyroscopeSTDZ"                          
* "TimeBodyGyroscopeJerkSTDX"                      
* "TimeBodyGyroscopeJerkSTDY"                      
* "TimeBodyGyroscopeJerkSTDZ"                      
* "TimeBodyAccelerometerMagnitudeSTD"              
* "TimeGravityAccelerometerMagnitudeSTD"           
* "TimeBodyAccelerometerJerkMagnitudeSTD"          
* "TimeBodyGyroscopeMagnitudeSTD"                  
* "TimeBodyGyroscopeJerkMagnitudeSTD"              
* "FrequencyBodyAccelerometerSTDX"                 
* "FrequencyBodyAccelerometerSTDY"                 
* "FrequencyBodyAccelerometerSTDZ"                 
* "FrequencyBodyAccelerometerJerkSTDX"             
* "FrequencyBodyAccelerometerJerkSTDY"             
* "FrequencyBodyAccelerometerJerkSTDZ"             
* "FrequencyBodyGyroscopeSTDX"                     
* "FrequencyBodyGyroscopeSTDY"                     
* "FrequencyBodyGyroscopeSTDZ"                     
* "FrequencyBodyAccelerometerMagnitudeSTD"         
* "FrequencyBodyAccelerometerJerkMagnitudeSTD"     
* "FrequencyBodyGyroscopeMagnitudeSTD"             
* "FrequencyBodyGyroscopeJerkMagnitudeSTD" 