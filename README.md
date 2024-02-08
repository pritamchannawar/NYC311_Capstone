# An Analysis of NYC 311 Service Requests 
## Predicting the Responding Government Agency

# Abstract:
Since it started in March 2003, the New York City (NYC) 311 call line (and more recently its website and app) has let people ask for help with non-emergency government services. People in New York can call 311 to ask for information or to let the government know about a problem that needs fixing. Every time someone calls 311 for help, the request is sorted into one of 278 different types of complaints, this helps the city know what kinds of issues people need help with. These NYC311 data is updated daily and contains information about more than 24 million service requests made since 2010. There are different departments to solve the different requests, although these complaints are not necessarily urgent, the large volume of complaints and the sudden increase impact the agency's overall efficiency. This paper discusses my process for exploring trends in a recent subset of the data (March-Oct. 2023), and for building a Machine learning and deep learning model which will help Agencies improve service delivery by allowing them to focus on their core missions and manage their workload efficiently.

## Data
The data used in this project was obtained from two sources:

* [NYC Open Data's 311 Service Requests from 2010 to Present](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2010-to-Present/erm2-nwe9)

This dataset contains information about the location, time, complaint type, and status of more than 24 million 311 service requests made in New York City within the past decade. This project uses a subset of the data from 2020 that was accessed with the Socrata Open Data (SODA) API.

## Results

Every day, an extensive dataset captures information about thousands of 311 calls in New York City, detailing their time, location, and content. Analyzing trends within this data enables government agencies to enhance their responsiveness to non-emergency requests from the community. This project utilizes public data on 311 calls and community districts in NYC to investigate the prevalence of different call types, variations in daily call volume across districts, and the allocation of calls to various government agencies. 

Key Findings:
•	“Illegal Parking” is the most frequent complaint type.
   
•	The Brooklyn is the most affected borough by this complaint type, and it has registered the highest volume of complaints among all the boroughs.
 
•	There is total 14 agencies to handle these calls, the New York Police Department (NYPD) responded to just over 50% of all 311 calls.
•	Most of the calls were made in afternoon.
 
•	Calls to the NYPD, which include all complaints, peak at the earliest and latest hours of the day.
•	Illegal parking and Noise-related complaints comprised the overwhelming majority of calls each month.

We build a model that can accurately predict the type of complaint based on the time of day and the city where the complaint was filed. The XGB classifier (accuracy ~ 72%) performs same as the Logistic regression classifier (accuracy ~ 72%). Another goal of this project is to build a linear model that can accurately predict total time taken to resolve a call based on Hour at which call is received at the Agency, given a set of observations of an independent variable Hour at which call is received and a dependent variable total time. The linear regression model has performed the best with root mean square error (RMSE) 0.25.

Finally, with all the findings and leveraging natural language processing and the Keras library, the project aims to construct a neural network capable of classifying the responding government agency based on the call's description. 
 
Accuracy and loss curves show that the model began to learn at a mostly steady rate after about 50 epochs. The best-performing model had ~92% accuracy on the test data and 67.2% accuracy on the random subset. It performed most successfully on calls assigned to the NYPD, HBD and DPR, although the agency variable exhibited substantial imbalance, with the NYPD responding to slightly over 50% of all 311 calls. The dataset encompassed 14 government agencies assigned to 311 calls, posing challenges in achieving perfect classifier accuracy. Currently, non-emergency service requests predominantly rely on phone calls; however, the development of such a classifier could streamline the automatic assignment of requests to the appropriate agency in an online context where requests generate text descriptions.
![image](https://github.com/pritamchannawar/NYC311_Capstone/assets/3954461/8c036733-18f8-42a8-b3c4-a21f5cd3641f)
