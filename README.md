# challenge2012
Python code parsing data from PhysioNet Challenge 2012.

The PhysioNet 2012 challenge, [described here](https://physionet.org/challenge/2012/), focused on encouraging development of mortality prediction models for intensive care unit patients. Time-stamped observations for a number of measurements were made available, with the goal to predict in-hospital mortality.

A big part of any machine learning project is data preprocessing. The notebook prep-data.ipynb transforms the original PhysioNet 2012 data to have one row per patient. This is done by applying a number of simple feature extraction steps to each measurement time-series independently, e.g. extracting the first heart rate, first blood pressure, and so on. The code also pre-processes the data to remove outliers based on physiologic limits (you cannot have a negative blood pressure, you cannot have an oxygen saturation above 100%, and so on).

The logic used here was applied in our conference paper: (Patient specific predictions in the intensive care unit using a Bayesian ensemble)[https://ieeexplore.ieee.org/abstract/document/6420377]. Our entry had the highest score 1 in the competition, where score 1 was defined as the minimum of the sensitivity/positive predictive value.

The code was originally written in MATLAB but with any luck this Python code is a faithful reproduction.
