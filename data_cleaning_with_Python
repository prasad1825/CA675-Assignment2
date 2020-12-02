# CA675_A2
## PRE-PROCESSING DATASET

***********************************PROCEESSED***************************************************************
### Collected original dataset is  at https://www.kaggle.com/ananaymital/us-used-cars-dataset
### Generated new dataset at the first stage through Python (after defining neccessary columns)

import pandas as pd

import numpy as np

car_df = pd.read_csv('E:\\Dao\\used_cars_data.csv')

--- filtered neccessary columns

car_df_filtered = car_df.loc[:,[ 'model_name', 'franchise_make', 'make_name', 'is_new',  'listed_date', 'daysonmarket','year', 'price', 'savings_amount', 
                                  'engine_type','body_type','city', 'city_fuel_economy', 'highway_fuel_economy',  'fuel_type', 'fuel_tank_volume', 
                                    'interior_color', 'listing_color', 'description' , 'maximum_seating', 'mileage', 'transmission', 'transmission_display', 
                                      'wheel_system_display',  'latitude', 'longitude' ]]

--- deleted rows with null field(s)

car_df_filtered_remove_na = car_df_filtered.dropna()


----exported to csv file

car_df_filtered_remove_na.to_csv('E:\\Dao\\used_cars_data_26columns_removeNan.csv')

# Output is a csv file with 1.832.571 rows and 26 columns.

---That can be downloaded at: https://drive.google.com/file/d/1p7PJh28Cv7nxN0mX8jlqEUL0zJZLpIPZ/view?usp=sharing (csv file)

                              https://drive.google.com/file/d/1nwm0HyH8tBKeq9tAvGZNLlCN-HmluF-c/view?usp=sharing (zip file)


******************TO BE CONSIDERED FOR LATER PRE-PROCESSING****************************************************


-----it is quite dangerous to change the original data values by forcing data type like this.

car_df_filtered_remove_na = car_df_filtered_remove_na.astype({"city_fuel_economy":'int64',
                                                                "highway_fuel_economy":'int64',
                                                                 "mileage":'int64',
                                                                   "price":'int64'})



-----pre-process columns including numbers and units --> split objects into numbers and units

car_df_filtered_remove_na[['fuel_tank_volume','fuel_tank_volume_unit']] = car_df_filtered_remove_na.fuel_tank_volume.str.split(" ",expand=True)

car_df_filtered_remove_na[['maximum_seating','maximum_seating_unit']] = car_df_filtered_remove_na.maximum_seating.str.split(" ",expand=True)

car_df_filtered_remove_na = car_df_filtered_remove_na.astype({"fuel_tank_volume":'float64',
                                                             "maximum_seating":'int64'})



-----find incorrect fuel tank value and max seating and drop them

nan_fuel_tank_value = car_df_filtered_remove_na.loc[car_df_filtered_remove_na.fuel_tank_volume == '--']

car_df_filtered_remove_na = car_df_filtered_remove_na.drop(nan_fuel_tank_value.index)

nan_max_seating_value = car_df_filtered_remove_na.loc[car_df_filtered_remove_na.maximum_seating == '--']

car_df_filtered_remove_na = car_df_filtered_remove_na.drop(nan_max_seating_value.index)



-----view the dataset info

a = car_df_filtered_remove_na.head(10000)

car_df_filtered_remove_na.info()

*********************************************************************************************************
