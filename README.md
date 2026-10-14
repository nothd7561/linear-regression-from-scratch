# Linear Regression From Scratch

A simple linear regression built from scratch in NumPy, validated against scikit-learn.
Built for some foundational practice and to gain a more solidified understanding of linear regression and how to implement in sci-kit.

## Aspects that I implemented

- **Closed-form least squares:** computes slope and intercept from the means, deviations,
  and the covariance/variance ratio
- **Prediction and MSE functions:** reusable on any 1D data
- **Valid Inputs for LR:** raises clear error for different length arrays, same number x-values that cause slope to divide by 0
- **Gradient descent:** (working on it)

## Validation

Results were compared against scikit-learn's `LinearRegression` on three datasets
using `np.isclose` and `np.allclose`:

| Dataset | Description | Matches sklearn? |
|---|---|---|
| Mini Manual | (1,2), (2,4), (3,5), checkable by hand | Yes |
| Synthetic Data | 100 points, y = 3x + 5 + noise (seeded) | Yes |
| Tips from Seaborn | Seaborn `tips` dataset (bill vs. tip, 244 rows) | Yes |

On the synthetic data, the fit recovered a slope of 2.99 (true: 3) and an
intercept of 5.32 (true: 5).
On the tips data, the fit gives tip ≈ 0.92 + 0.105 × total_bill.

## How to run

1. Open `[lin_reg_scratch].ipynb` in Google Colab (or any Jupyter environment)
2. Run all cells in order. Requires `numpy`, `seaborn`, and `scikit-learn`
   (all preinstalled in Colab)
- You can change the mini manual data to whatever you like. Must be same length for x and y value arrays.
- The formula for random data generation can also be tweaked to your liking
  
## Limitations

- Single feature only. Multiple regression requires matrix algebra
- No train/test split. This project is about the fitting math, not generalization
