# Polynomial Curve Fitting

## Concept
Polynomial Curve Fitting is an extension of linear regression where we fit a polynomial function to data:

\[
y(x, w) = w_0 + w_1 x + w_2 x^2 + \dots + w_M x^M
\]

Although the model is polynomial in \( x \), it is **linear in the parameters** \( w \), so it can still be solved using linear algebra.

## Data
A standard teaching example uses synthetic data from a sine function with noise:

\[
t = \sin(2\pi x) + \epsilon
\]
- \( x \) is uniformly spaced in \([0, 1]\).
- \( \epsilon \) is Gaussian noise.

## Learning Process
We build a **design matrix** \(\Phi\) with columns:
\[
[1, x, x^2, \dots, x^M]
\]

The parameters are found by minimizing the **sum of squared errors**:

\[
E(w) = \frac{1}{2} \sum_{n=1}^N \left( y(x_n, w) - t_n \right)^2
\]

Closed-form solution:
\[
w = (\Phi^T \Phi)^{-1} \Phi^T t
\]

## Model Complexity
- **Low degree (M small)** → Underfitting: Model too simple, misses important structure.
- **Moderate degree** → Good fit, balances bias and variance.
- **High degree (M large)** → Overfitting: Fits noise, poor generalization.

## Generalization
We evaluate performance using a separate **test set**:
- Training error always decreases as \( M \) increases.
- Test error decreases up to an optimal \( M \) and then increases due to overfitting.

## RMS Error
Instead of raw squared error, we often report **Root Mean Square (RMS)** error:
\[
E_{\text{RMS}} = \sqrt{ \frac{ 2 E(w) }{ N } }
\]
which has the same units as \( t \).

## Key Takeaways
- Polynomial fitting is a direct way to illustrate bias–variance tradeoff.
- Using training and test sets helps us select a model that generalizes well.
- Regularization (adding a penalty term to \( E(w) \)) can reduce overfitting in high-degree polynomials.
