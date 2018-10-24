# challenge2012
Python code parsing data from PhysioNet Challenge 2012.

The PhysioNet 2012 challenge, [described here](https://physionet.org/challenge/2012/), focused on encouraging development of mortality prediction models for intensive care unit patients. Time-stamped observations for a number of measurements were made available, with the goal to predict in-hospital mortality.

A big part of any machine learning project is data preprocessing. The notebook prep-data.ipynb transforms the original PhysioNet 2012 data to have one row per patient. This is done by applying a number of simple feature extraction steps to each measurement time-series independently, e.g. extracting the first heart rate, first blood pressure, and so on. The code also pre-processes the data to remove outliers based on physiologic limits (you cannot have a negative blood pressure, you cannot have an oxygen saturation above 100%, and so on).

The logic used here was applied in our conference paper: [Patient specific predictions in the intensive care unit using a Bayesian ensemble](https://ieeexplore.ieee.org/abstract/document/6420377). Our entry had the highest score 1 in the competition, where score 1 was defined as the minimum of the sensitivity/positive predictive value.

The code was originally written in MATLAB but with any luck this Python code is a faithful reproduction.

## Downloading the data

For convenience, the already processed datasets are made available in the [data subfolder](/data).

If you use this data in your research or otherwise, please do acknowledge the organizers of the PhysioNet 2012 Challenge:

```
@article{silva2012predicting,
  title={Predicting in-hospital mortality of icu patients: The physionet/computing in cardiology challenge 2012},
  author={Silva, Ikaro and Moody, George and Scott, Daniel J and Celi, Leo A and Mark, Roger G},
  journal={Computing in cardiology},
  volume={39},
  pages={245},
  year={2012},
  publisher={NIH Public Access}
}
```

We would also appreciate acknowledgement:

```
@inproceedings{johnson2012patient,
  title={Patient specific predictions in the intensive care unit using a Bayesian ensemble},
  author={Johnson, Alistair EW and Dunkley, Nic and Mayaud, Louis and Tsanas, Athanasios and Kramer, Andrew A and Clifford, Gari D},
  booktitle={Computing in Cardiology (CinC), 2012},
  pages={249--252},
  year={2012},
  organization={IEEE}
}
```
