# CA675-Assignment2
12/12/2020
--> Dao updated cleaned dataset. Source code can be found in GCP_data_cleaning_updated.txt

---Filtered data rows to eliminate rows with at least one meaningless field
filterData_notnull_notblank_na_others = FILTER filterData_notnull_notblank_na  by NOT ((fuel_tank_volume =='--') OR  (listing_color =='UNKNOWN')  OR (maximum_seating =='--')OR (interior_color =='None'));

---New cleaned dataset can be accessed at the bucket namely "bucket_usedcars_updated" (project CA675-A2-2020-new) as well as the public link  https://storage.googleapis.com/bucket_usedcars_updated/hive_usedcars_input.csv

--> Dao uploaded GCP_datacleaning_images_updated.docx
---> Connecting BigQuery to Python.txt
--->usedcars_visualisation_draft_draft_draft.py
