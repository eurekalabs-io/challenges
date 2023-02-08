Challenge: House Price Service
==============================

The goal of this exercise is to develop a Python service that is able to fit a predictor model and deliver predictions and recommendations about the prices of houses in the US. It is based on the challenge [House Price Predictor](./house-price-predictor.md), but having more engineering flavor.

In particular, these are the tasks that will be done:

- Load the downloaded dataset and prepare it for the modeling
- Fit a model to predict the prices of the given houses
- Run a service that loads the fitted model to make single predictions
- Provide endpoints to get predictions 

The dataset to use contains records from residential homes in the US, having variables to describe the property and the characteristics of the house, including the price to be predicted. There are several columns that can be used, but the main ones are described in the following data dictionary:

| Variable | Description | 
| :------------- | :----------- |
| property_area | Total property size in square feet (numerical)|
| house_age | Age of the property for the date of the record (numerical)|
| overall_quality | Overall material and finish quality (numerical, 1: poor - 10: excellent) |
| overall_condition | Overall condition rating (numerical, 1: poor - 10: excellent)|
| spaciousness | Amount of free space in the property in square feet (numerical)|
| liv_lot_ratio | Ratio of ground living area over lot area, in square feet (numerical)|
| remodel_age | Age of the last remodeling done for the date of the record (numerical)|
| bath_area | Size of bathrooms in square feet (numerical)|
| garage_area | Size of garage in square feet (numerical)|
| garage_age | Age of the garage for the date of the record (numerical)|
| has_2ndfloor | Flag indicating if the property has at least a second floor (boolean)|
| sale_price | Property's sale price in dollars (numerical)|

The dataset can be downloaded from [this link](https://drive.google.com/file/d/1b4LZTNCUUyGvssqpRvTzZ5ElmaaaqIjH/view?usp=sharing). 

## Requirements

To accomplish the tasks mentioned, here are some requirements about the expected work to deliver:

- **Development:** Deliver an app that serves the model through the following required endpoints:
    - `/model_performance`: GET endpoint to retrieve the performance of the trained model (no parameters).
        - Example of response: `{"train": {"rmae": 161.977, "mae": 26236.745}, "test": {"rmae": 166.157, "mae": 27531.892}}`
    - `/predict`: GET endpoint to retrieve a predicted price for a given house (where the parameters are the features used by the model).
        - Example of response: `{"prediction": 162709.5}`

    Feel free to decide about the response for each endpoint, the example is just a reference. Provide scripts / notebooks as desired, as long as the asked service can be tested in a local setup based on the specified examples. 
- **Machine Learning:** Choose your favorite algorithm to train and validate a predictor model, selecting the metrics you consider appropriate to assess the performance. Do some assessment of the quality of the data to be used.
- **Environment:** Ensure you provide enough tools / information to reproduce the results in another machine.

## Extra points

The following aspects are NOT mandatory, but they will give an outstanding score of the work:

- *Design patterns:* Implement a good architecture for the service based on some design patterns.
- *Code style:* Show good practices in the delivered code (e.g. linting, documentation).
- *Testing:* Show at least some unit tests for the functions developed.

## Considerations

Make sure you have the following aspects in mind before starting:

- Feel free to decide the architecture and the way to design and deliver the asked Python class.
- Freedom for technologies, as long as everything is done in Python.
- Data Analysis capabilities will be evaluated, BUT it is not the main goal of the exercise. Make sure you spend more time in the asked tasks rather than in experimentation or deep analysis.
- Getting the best score possible won't be rated, as long as you can assess the performance of the model obtained.

This exercise was designed to be completed in ~4-6 hs, so it is OK to not achieve a perfect result since the idea is just to validate technical skills. If you have doubts, feel free to contact us to make everything clear for your work.

> **Think. Build. Enjoy!**