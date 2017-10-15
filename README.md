# pykliep
A density ratio estimator package for python using the KLIEP algorithm.

The DensityRatioEstimator class implements the [Kullback-Leibler Importance Estimation Procedure](http://proceedings.mlr.press/v38/sasaki15.pdf) by Sugiyama et al. Estimator uses likelihood cross validation (LCV) to tune the *num_params* and *sigma* parameters.

## Usage

```python
from pykliep import DensityRatioEstimator 

kliep = DensityRatioEstimator()
kliep.fit(X_train, X_test) # keyword arguments are X_train and X_test
weights = kliep.predict(X_train)

rf = RandomForestRegressor()
rf.fit(X_train, y_train, sample_weight=weights) # Train using the sample weights!

```