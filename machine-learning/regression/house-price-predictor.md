
<img style="float: left; padding-right: 5px; width: 200px" src="https://eurekalabs.io/wp-content/uploads/2022/05/brand-eurekalabs.svg"> 

<hr style="height:20pt">
<br><br>

Challenge: House Price Predictor
================================

The goal of this exercise is to develop a Python class that is able to fit a model to deliver predictions and recommendations about the prices of houses in the US. In particular, these are the tasks that will be done:

- Load the downloaded dataset and prepare it for the modeling
- Fit a model to predict the prices of the given houses
- Use the model to make single predictions, providing the top important features for each prediction 

The dataset to use contains records from residential homes in the US, having variables to describe the property and the characteristics of the house, including the price to be predicted. The following data dictionary helps to understand the meaning of each column:

| Variable | Description | 
| :------------- | :----------- |
| property_area | Total property size in square feet (numerical)|
| house_age | Age of the property for the date of the record (numerical)|
| house_style | Style of the house in terms of the stories distribution (categorical)|
| neighborhood | Physical locations within city limits (categorical)|
| overall_quality | Overall material and finish quality (numerical, 1: poor - 10: excellent) |
| overall_condition | Overall condition rating (numerical, 1: poor - 10: excellent)|
| spaciousness | Amount of free space in the property in square feet (numerical)|
| liv_lot_ratio | Ratio of ground living area over lot area, in square feet (numerical)|
| remodel_age | Age of the last remodeling done for the date of the record (numerical)|
| bath_area | Size of bathrooms in square feet (numerical)|
| bsmt_area | Size of basements in square feet (numerical)|
| garage_area | Size of garage in square feet (numerical)|
| garage_age | Age of the garage for the date of the record (numerical)|
| has_2ndfloor | Flag indicating if the property has at least a second floor (boolean)|
| has_porch | Flag indicating if the property has a porch included (boolean)|
| has_pool | Flag indicating if the property has a pool included (boolean)|
| has_multiple_kitchen | Flag indicating if the property has more than one kitchen (boolean)|
| sale_price | Property's sale price in dollars (numerical)|

The dataset can be downloaded from [this link](https://drive.google.com/file/d/1b4LZTNCUUyGvssqpRvTzZ5ElmaaaqIjH/view?usp=sharing). The following Python snippet can be used as a reference of the intended usage of the asked class based on the mentioned tasks:

```python
# Ensure the class "HouseScorerModel" is imported

# Create and fit a model using the downloaded dataset
hsm = HouseScorerModel("challenge_houses-prices.csv")
hsm.fit()
# Get the performance of the fitted model
print(hsm.get_model_performance())
# > It should print a dict like {"train": {"rmae": 161.977, "mae": 26236.745}, "test": {...}}

# Get a single prediction with the top of important features for that prediction
data_point = {
    "garage_area": 547,
    "overall_quality": 6,
    "overall_condition": 5,
    "bsmt_area": 621,
    "property_area": 2016,
    "bath_area": 2.5,
    "has_pool": 0,
    "has_porch": 1,
    "has_2ndfloor": 1,
    "has_multiple_kitchen": 0,
    "liv_lot_ratio": 0.0,
    "spaciousness": 245.0,
    "house_age": 14,
    "remodel_age": 11,
    "garage_age": 15.0,
    "neighborhood": "Gilbert",
    "house_style": "2Story",
}
print(hsm.get_prediction(data_point))
# > It should print a dict like {"prediction": 162709.5, "top_features": {"house_age": 0.712, "overall_quality": 0.221, ...}}
```

## Requirements

To accomplish the tasks mentioned, here are some requirements about the expected work to deliver:

- **Development:** Provide scripts / notebooks as desired, as long as the asked Python class can be tested based on the previous code snippet shown. 
- **Data Quality:** Analyze and control the quality of the data to be used to fit and evaluate the model.
- **Machine Learning:** Choose your favorite algorithm to train and validate a predictor model, selecting the metrics you consider appropriate to assess the performance. 
- **Environment:** Ensure you provide enough tools / information to reproduce the results in another machine.


## Extra points

The following aspects are NOT mandatory, but they will give an outstanding score of the work:

- *Model Explainability:* Report some insights about the interpretation of the model obtained and the predictions generated.
- *Code style:* Show good practices on the code developed (e.g. linting, documentation).
- *Testing:* Show at least some unit tests for the functions developed.

## Considerations

Make sure you have the following aspects in mind before starting:

- Feel free to decide the architecture and the way to design and deliver the asked Python class.
- Freedom for technologies, as long as everything is done in Python.
- Data Analysis capabilities will be evaluated, BUT it is not the main goal of the exercise. Make sure you spend more time in the asked tasks rather than in experimentation or deep analysis.
- Getting the best score possible won't be rated, as long as you can assess the performance of the model obtained.

This exercise was designed to be completed in ~3-5 hs, so it is OK to not achieve a perfect result since the idea is just to validate technical skills. If you have doubts, feel free to contact us to make everything clear for your work.

> **Think. Build. Enjoy!**