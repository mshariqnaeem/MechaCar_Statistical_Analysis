# MechaCar_Statistical_Analysis Challenge

The purpose of this challenge was to conduct a statistical study using R language through RStudio to compare vehicle performance of MechaCar against the vehicles of other car manufacturers. We performed this analysis through linear regressions, T-tests and other statistical parameters.

Our Analysis can be found in the RStudio file **MechaCarChallenge.R**.

## Overview of MechaCar Analysis

Jeremy was selected as the data analyst for AutosRUs new vehicle prototype named the "MechaCar". Due to production related issues which have slowed the progress of the manufacturing team, Jeremy has been requested to complete further statistical analysis on the production data to help the manufacturing team.

Jeremy was requested to complete the following analysis to help in the making statistical conclusions

- Linear Regression to Predict MPG
- Summary of Statistics on the Suspension Coils
- Complete T-Test on Suspension Coils
- Show an Anallysis of MechaCar compared to competitor vehicles

to begin our analysis we import the dplyr library into R as shown in the image below.

![import library](https://user-images.githubusercontent.com/92459399/154820815-7868c04b-3dd7-4a35-af6d-e00b83fba7b6.PNG)

## Linear Regression to Predict MPG

For our first deliverable we were asked to import the MechaCar_mpg.csv file and generate a linear regression which is shown below.

![Deliverable 1](https://user-images.githubusercontent.com/92459399/154820850-a756bc44-7315-436e-9e3b-f6c52e325890.PNG)

![Coefficients](https://user-images.githubusercontent.com/92459399/154822180-34d1c85f-4dbc-4501-b06a-886bd19643df.PNG)

When we execute the linear regression code shown in the image above we find the following information. the Pr(>|t|) tells us which variable coefficient provides us with a non random variance value to the mpg from the dataset.\

- the lower the Pr value the less likely the variable causing variances in the mpg data
- as the PR(>|t|) value is well below the .05 for vehicle length and the ground clearance we can come to the conclusion that both values are non-random variance o the mpg values

The next question to ask is if there is a significant linear relationship between the vehicle_length, weight, spoiler_angle, ground_clearance, AWD and mpg values in the dataset and their relation to the slope. If any of there is a relationship between these variables and the slope, then the slope cannot equal a value of zero.

We use the p-value and the f-statistic to determine if the Null hypothesis should be rejected  or not.

- the p-value and f-statistic values (5.35e-11 and 22.07 repsectively) tell us that the Null hypotehsis should be rejected
- this is so the slope of the linear model cannot be zero

The results are shown in the image below.

![residual values and standard error](https://user-images.githubusercontent.com/92459399/154822281-9454c7a8-7fab-479c-b174-a3cb5bbfac1a.PNG)

## Summary Statistics on Suspension Coils

For Deliverable #2 we are asked to import the Suspension_Coil.csv file into a dataframe which is shown in the image below.

![Deliverable 2](https://user-images.githubusercontent.com/92459399/154822769-209f7229-06e6-4302-945b-f44b5442ec02.PNG)

We also determines the summary of the suspension coil which is shown in the image below.

![Total_summary](https://user-images.githubusercontent.com/92459399/154822857-7dd9298e-cb97-4039-b899-e26a784f2b36.PNG)

If we make the conclusion that the variance of suspension coils must not exceed 100 pounds per sq. inch then our current design specifications meets this amount as the suspension coils for the total summary of the lots is 62.29 PSI. However if you look at the result for Lot 3 the variance is much higher at 170.286 PSI which is very high and should be looked at closer.

Upon closer examination we notice that in lot_summary Lot1 and Lot2 have a much lower Variance than lot 3 which is the reason why the total variance in total_summary is so low overall.

![Lot_summary](https://user-images.githubusercontent.com/92459399/154823022-9427decc-6704-4a89-992b-dbe1be76e006.PNG)

From this we can conclude that Lot3 must have an issue that requires further attention.

## T-Tests on Suspension Coils

Below we use the following code for Deliverable #3 (T-tests on Suspension coils).

![T-tests on suspension coil](https://user-images.githubusercontent.com/92459399/154824606-015f8658-e27f-41b2-b48c-9095b229707e.PNG)

The T tests are used to compare the mean of each lot individually to the population mean of 1500. When looking at the results of the mean for Lot1 and Lot2, the results from the T-test for the suspension coils is not much different from the population mean which is shown in the images below.

![T-test Lot1](https://user-images.githubusercontent.com/92459399/154824815-38fe7844-cb45-41dd-957c-a27fe9cb6b5d.PNG)
![T-test on suspension coil Lot2](https://user-images.githubusercontent.com/92459399/154824789-f1c19a4e-99c2-4b39-9a8a-fbb23277edad.PNG)

So far so good! However when we look at the T-test for teh suspension coill for lot3 we see that they ARE statistically different from the population mean and the p-value is less than .05 (a value of .04168) so we reject the null hypothesis in this case.

![t-test Lot3](https://user-images.githubusercontent.com/92459399/154824874-91ae1940-400d-4c12-92de-75210eca670f.PNG)

From this test we can conclude that there is definitely an issue in Lot3 which needs to be looked into further and is statistically likely to be the reason that MechaCar is facing issues in comparison to its competitors.

## MechaCar vs Competitors

For our statistical study to see if MechaCar is fairly priced in comparison to its competitors we look at the following metrics of measurement:

- Price of the car (**Dependent variable**)
- Fuel efficiency (**independent variable**) which affects the price
- horsepower of the vehicle (**independent variable**) which affects the price
- maintenance costs (**independent variable**) which affects the price
- Resale value (**independent variable**) which affects the price

Null hypothesis: MechaCar is fairly priced basedd on our dependent variable for the same type of competing vehicle model
Alternative hypothesis: MechaCar is over priced OR under priced based on the dependent variable for the same type of competing vehicle.

For this  analysis to be completed we would need a dataset/random sample of vehicles from MechaCar's competitors for similar model to determine if the data is similar to that of MechaCar or not.
