# quality-prediction-mining-process

# Motivation
- Ores usually contain impurities such as silicates, removing the impurities is considered a fundamental step during mining process.
- This is done using Froth Flotation
- Impurity concentration is measured at 2 hour intervals
- Goal: predict silica % using available readings
- Accurate prediction gives operators information in advance, so they could alter operating conditions to achieve more favorable results.

# Dataset
- Dataset with 22 input variables and 1 output
- Time-series data with 737,453 points, collected over 6 months
- Include input and output iron ore and impurity %, pH, flow rates, etc.
- Some readings taken at 20s intervals, others at 1 hr intervals

# Why Random Forest Regression?
- Strong predictive performance
- Average of multiple models
- Less impacted by noise
- Easy to determine feature importance

# Bootstrap Aggregation
- Bootstrap aggregation (Bagging):
- Bootstrap is a technique that helps randomly replace the sampling of dataset.
- Train the observation into several decision trees, each of them have its own output and accuracy, the trees give maximum number of output will be selected as the output of the model.
- Helps avoid overfitting

# Random Forest Regression
- Feature bagging: to increase the accuracy and explain the model as much as possible. Selecting a subset P by randomly picking from each trained set. 
- This is for avoiding the features with outstanding predictive ability to affect the result, and by doing this, the correlation get increased as well.
- Managed to achieve 99.8% accuracy while using iron ore concentration, and 96.3% accuracy without it

# Random Forest Limitations
- Less interpretable than an individual decision tree
- Black box vs white box models
- High computational cost for larger datasets 
- Slower predictions

# One step further: 
- Drop first 534 y values and last 534 X rows
- 736,919 points (Down from 737,453)
- Now we’ve matched each X row with the output 3 hours in advance


# Next Steps
- Create a monitoring software using PCA based on the results
- Used by operators to minimize impurity %
