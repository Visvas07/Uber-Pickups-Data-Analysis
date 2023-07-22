# Uber-Pickups-Data-Analysis
This repository holds the project details about the Uber Pickups dataset analysis. 

## Dataset Description
This is 2014 Uber Pickups dataset that records the pickups done from April to September. There are 5 bases in New York City (Bronnx, Manhattan, Brooklyn, Queens and Staten Island. The data shows records of pickups done from these 5 localities.

Here, the columns defined in the dataset are:
• Date and Time: The date and the time of the pickups
• Lat: The latitude of the pick-up location
• Long: The longitude of the pick-up location
• Base: The base i.e., which part of New York City

## Before execution
Before proceeding with the data analysis, we must first install the following packages:
• ggplot2: This is the main visualization tool for R. This helps us to visualize the plots
• ggthemes: This is an extension to ggplot2 library. It helps to add extra themes to the ggplot2.
• lubridate: This library helps in categorization of time frames. Since the dataset contains different timeframes, this library will help us to manipulate the time frames.
• dplyr: This helps in data manipulation.
• tidyr: This helps to tidy the data in the dataset.
• DT: This library helps to interface with the JavaScript library called DataTables.
• scales: This helps to mark graphical scales, which helps to map the data to those scales to ensure readability.

## Code explanation

![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/b2900b72-39e1-4497-a34f-09412a5448f0)

Here, we initialize an array of hexadecimal color codes to be used for visualization of our graphs.

![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/f0318289-e4b5-473c-89b3-764a48d5fc60)

Here, we read each csv file and store it in corresponding variables. Then we combine all these data into a common variable using the rbind() method. When we run dim(data_2014), we come to know there are 4534327 rows and 4 columns, which is a very large dataset. Next, we format the Date.Time column into the given formats (day,month,year,dayofweek) by splitting them using the POSIXct method.

![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/edf3325d-39b5-4493-9efd-af0c237101c4)

Here, we create factors with the hour, minute and second columns in the dataset using the hms method.

![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/6ac4ee3b-c76e-46fc-a90b-6fbf0c20754e)

Next, we create hour_data by summarizing the hour data and display it using the datatable method. It will show the following:

![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/b3a2d4b0-fdbe-4864-9235-4f3c2e5a9ed6)

Next, we use ggplot to plot the pick-up trips made each hour.

![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/900580a8-40db-4bd5-bb92-9db40ab44122)

The plot generated is:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/2a05d78d-1996-460f-b1f0-6c3fa6dc31e9)
Here, we can see the pick-up trips done by each hour of the day.

Next, we must group the hour by month data where we can see which hour had more pick-up trips in which month.
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/723f8078-eb29-4b35-93dc-6f1ed16927c5)

The plot generated is:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/235426a3-71b9-4c12-a5e3-3104223cb7a4)

Next, we then group the day data where it accounts for how many trips have been made on which day of a month. This is general for all the 6 months.
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/45cfebd8-8e42-4074-aefd-6bd00b8c97bb)

Here, the datatable is:

![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/e0c3f18d-7d61-4e79-b5e2-6056544be89b)

Then, we plot the data in graph. The plot generated is:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/99f2087b-807e-4f52-a564-d6a85908400c)

Now, we plot the number of trips per base. For New York City, there are 5 bases (Bronx, Manhattan, Brooklyn, Staten Island, Queens). These are labelled as B02512, B02598, B02617, B02682, B02764 respectively. The plot generated is:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/ba887f14-c7aa-4f18-9a72-4ae29369abf6)

Next, we plot the number of trips that are made in each month. For that, we must first group the month data.
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/fd6083f7-f4c7-4839-8f2e-f5538329f181)

The data table generated:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/76f66d01-8845-4cf8-b6df-5ad0f895eb38)

Then, we plot the graph using the above data table. The plot generated is:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/e5414365-b902-4b07-9406-fabcbedd145a)

Next, we are going to see the number of pick-up trips being made in each month and base. The plot generated for that is:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/a37f0ba6-ceb4-4608-bf9d-d4c4e824045c)

Lastly, we will focus on how many trips were made on each day in each month. The code and plot for that is:
![image](https://github.com/Visvas07/Uber-Pickups-Data-Analysis/assets/69456725/fff14e4b-fb48-4d26-8471-b116cac56e9d)

## Inference:
From this project, we can analyze that the time that had the most pick-ups were made at 5 pm and the time that had the least number of pick-ups were at 3 a.m. The 5 p.m. hike is actually for those who are leaving their workplaces for their home. Hence, they have a greater number of pick-ups. However, if we check it by month, we get that the month April have more pick-ups whereas September had the least number of pick-ups at that time. It is also the same for 3 a.m. too. Also, judging by the analysis made, September had the highest number of trips in the year whereas April had the lowest number of trips. While judging by day and month, it has many variations.
• April:
  o Most number of trips: Wednesday
  o Least number of trips: Sunday
• May:
  o Most number of trips: Friday
  o Least number of trips: Sunday
• June:
  o Most number of trips: Thursday
  o Least number of trips: Sunday
• July:
  o Most number of trips: Thursday
  o Least number of trips: Sunday
• August:
  o Most number of trips: Friday
  o Least number of trips: Monday
• September:
  o Most number of trips: Tuesday
  o Least number of trips: Sunday
Hence, from this analysis, we can learn that Uber has more pick-ups during week days rather than week-ends. There are more customers in working sector who avail this service in the week-days.




















