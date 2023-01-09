# tanzania_water_wells
Tanzania_Water_Wells
### README

### Machine Learning Model: Tanzanian Water Wells

#### Problem Description
Water Aid is an NGO based in the United Kingdom that works on access to clean water around the world. They consider 
access to clean water, decent toilets and good hygiene as basic human rights. For over 30 years, they have been 
working in partnership to improve access to these three essentials through a combination of programmatic and policy work.

Water Aid works in several countries around the globe, including Tanzania and surrounding East African countries. 
According to the World Sector Report (2019) around 60% of the population in this area have access to improved water, 
but the degree of water access, and the water quality and quantity, varies. Drought, landscape change, and the 
amplifying effects of climate change are straining existing surface water supplies.

Water Aid is launching a program to repair non-functioning wells in the cross country shared water basins 
of Eastern Africa. The status of the wells is not clearly recorded in countries surrounding Tanzania. Identifying 
non-functioning wells, securing funding, and traveling to these rural locations to repair wells is both time and resource 
intensive. They need a predictive model that accurately identifies which wells are not functioning to reduce cost and 
ensure they are using their resources wisely. They also need to identify a specific water basin to begin their work.

#### Business Problem

Water Aid is launching a groundwater infrastructure initiative to repair wells in the region. They have limited resources and 
don't know how to accurately identify these wells effectively.


### Goals:

    1. Using an iterative process, build a predictive machine learning model based on existing water well data to accurately 
    classify non-functioning wells.

    2. Based on model feature importances develop two targeted recommdendations for model usage.

    

### Data

The Tanzanian Water Wells dataset comes from the Taarifa waterpoints dashboard, which aggregates data from 
the Tanzania Ministry of Water.The dataset is accessible through www.drivendata.org.  The dataset contains over 
50,000 records detailing the functional status of water wells throughout the country. Each record contains data 
in key areas: geographic data, water quality and quantity data, water pump features, and management schemes. The 
data contains both numerical and categorical data. 

### Modeling process

Exploratory Data Analysis --> Split data into test set and training set --> Preprocessing Data --> 
Logistic Regression Initial Model --> Decision Tree Model --> Tuned Random Forest Model.

The target for the model is multiclass: Functioning well, Functioning in need of repair well, and non-Functioning well. 

The predictors for the model includes all the other non-redundant features which describe the well.

### Key Results 

Key model results focus primarily on the precision measurement. Precision is used rather than recall considering 
Water Aid needs to accurately identify functioning and non-functioning wells to decrease cost, maximize use of 
program resources, and deliver mission success metrics to their funders.

#### Initial Model Results using Logistic Regression:

    F1 Score:         Functional Wells        0.83  
                      Functional needs Repair 0.34              
                      NonFunctioning Wells    0.77
                  
    

###Final Model using Random Forest Classifier:

    F1 Score:         Functional Wells        0.84 
                      Functional needs Repair 0.45
                      NonFunctioning Wells    0.81

    


### Data Visuals

![Number of Functioning Wells-Copy1](https://user-images.githubusercontent.com/104652254/211400340-c29d5626-2edd-4fe3-a309-412bea0f6b9b.png)

![Feature Importance-Copy1](https://user-images.githubusercontent.com/104652254/211400377-ff6ef0ca-35ce-423f-a062-12aa26e18b2d.png)

![functioning wells by funder-Copy1](https://user-images.githubusercontent.com/104652254/211400397-cc1e821a-0994-421c-ae73-a34cf3245aae.png)

![World Bank Enough-Copy1](https://user-images.githubusercontent.com/104652254/211400413-fac607d6-707d-4e00-93fc-c0eef0a400c7.png)




### Recommendations

#### 1.  Model Use

Water aid should focus on identifying non-functioning wells rather than wells that are functioning and
in need of repair. Chances are 81% that they will be right which will help in making use of programming 
resources to repair the wells. 

#### 2. Funders

Water Aid should work with the World Bank to repair non-functioning wells. The feature importances from 
the model reveal that funders and installers are important drivers in whether a well is functioning or not.  
The World Bank is one of the top 5 funders, with whom Water Aid already has a working relationship. 
World Bank also installs 20% of the wells they fund. Water Aid should work more closely with World Bank, 
especially considering that 52% of the wells that the World Bank funds are nonfunctional.

#### 3.

Water Aid should focus on wells that are driven by submersible pumps and have 'enough' water. 
Out of wells funded by World Bank that have been labeled with 'enough' water in quantity, 41% are 
not functional. Many of these wells are submersible pumps that draw from deep water wells, these 
pump types require greater investment and maintenance. Many of the other wells are gravity fed pumps, 
which are often simple in design but vary greatly in ability to deliver water due to siting issues 
and basic infrastructure resources.

### Navigating Repository

Data Visuals - Contains three visuals communicating data context and model results.

Job Files - Contains fitted models from initial model to final model

Water Wells.ipnyb - A jupyter notebook containing the worked model code

Test Set Values - A hold out test set for the models

Training Set Values - Features, or predictors, data set

Training Set Labels - Target variable for well functional status.
