# Toy Linear Regression

## Overview
Toy Linear Regression is a simplified supervised learning example where the relationship between an input variable \( x \) and an output variable \( t \) is modeled as a straight line.  
It is used to demonstrate the basics of regression, least squares fitting, and model evaluation.

## Purpose
- Introduce linear regression in the simplest possible form.
- Show how to fit a straight line to data.
- Demonstrate how to compute and interpret regression parameters.

## Data Generation
```python
import numpy as np

# Generate synthetic data
np.random.seed(0)
N = 20
x = np.linspace(0, 1, N)
t = 2.0 * x + 1.0 + 0.1 * np.random.randn(N)  # y = 2x + 1 + noise
