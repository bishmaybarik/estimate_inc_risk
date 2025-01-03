# Decomposing Total Income into Persistent and Transitory Components

This document explains the econometric methodology for decomposing total income into its persistent and transitory components. The decomposition follows a structured regression-based approach. Below, we outline the fundamental concepts, the step-by-step process, and the mathematical equations behind the decomposition.

---

## **1. The Basics: Total Income Decomposition**

We start with the assumption that total income \( y_{it} \) consists of two main components:

\[
y_{it} = \mu_{it} + \epsilon_{it}
\]

where:
- \( \mu_{it} \): The **deterministic part*
*, capturing predictable income variations due to factors like age, region, education, etc.
- \( \epsilon_{it} \): The **stochastic part** (unexplained residuals), which is further decomposed into:
  \[
  \epsilon_{it} = \alpha_i + \eta_{it}
  \]
  - \( \alpha_i \): **Persistent shocks** (e.g., long-term characteristics like skills or structural inequality).
  - \( \eta_{it} \): **Transitory shocks** (e.g., temporary job loss, bonuses).

The goal is to estimate the persistent and transitory components of the stochastic part \( \epsilon_{it} \).

---

## **2. Step-by-Step Econometric Decomposition**

### **Step 1: Regress Total Income on Deterministic Factors**

We first isolate the residuals \( \epsilon_{it} \) by running a regression:
\[
y_{it} = \beta_0 + \beta_1 X_{it} + \epsilon_{it}
\]

where:
- \( y_{it} \): Log of total income for individual \( i \) at time \( t \).
- \( X_{it} \): Covariates (e.g., age, region type) explaining systematic variations in income.
- \( \beta \): Coefficients to be estimated.
- \( \epsilon_{it} \): Residuals capturing unexplained variations in income.

The residuals are computed as:
\[
\epsilon_{it} = y_{it} - \hat{y}_{it}
\]
These residuals represent the stochastic part of income, which includes both persistent and transitory shocks.

---

### **Step 2: Use Residuals for Variance Decomposition**

The residuals \( \epsilon_{it} \) are assumed to have the structure:
\[
\epsilon_{it} = \alpha_i + \eta_{it}
\]
where:
- \( \alpha_i \): Persistent shocks.
- \( \eta_{it} \): Transitory shocks.

We decompose \( \epsilon_{it} \) into these components by calculating:

#### **1. Persistence (\( \rho \))**
Persistence is the autocorrelation of residuals across time:
\[
\rho = \frac{\text{Cov}(\epsilon_{it}, \epsilon_{it-1})}{\text{Var}(\epsilon_{it-1})}
\]
where:
- \( \text{Cov}(\epsilon_{it}, \epsilon_{it-1}) \): Covariance between residuals and their lagged values.
- \( \text{Var}(\epsilon_{it-1}) \): Variance of lagged residuals.

\( \rho \) measures the degree to which income shocks persist across periods.

#### **2. Variance of Transitory Shocks (\( \sigma_\eta^2 \))**
Using the **variance decomposition formula**:
\[
\sigma_\eta^2 = \sigma_\epsilon^2 - \rho^2 \cdot \sigma_{\epsilon, \text{lagged}}^2
\]
where:
- \( \sigma_\epsilon^2 \): Variance of residuals \( \epsilon_{it} \).
- \( \rho^2 \cdot \sigma_{\epsilon, \text{lagged}}^2 \): Part of residual variance explained by persistence.

This gives the variance of short-term fluctuations (\( \eta_{it} \)).

#### **3. Variance of Persistent Shocks (\( \sigma_\alpha^2 \))**
The persistent variance is computed by subtracting the transitory variance:
\[
\sigma_\alpha^2 = \sigma_\epsilon^2 - \sigma_\eta^2
\]
where:
- \( \sigma_\alpha^2 \): Variance due to long-term structural shocks.

---

## **3. Key Econometric Insights**

1. **Residual-Based Decomposition**:
   - Deterministic factors (age, region) are controlled for through regression.
   - Residuals capture **unexplained variations** in income, including persistent and transitory shocks.

2. **Persistence via Autocorrelation (\( \rho \))**:
   - Persistence is captured by correlating residuals over time.
   - High autocorrelation indicates that shocks persist across periods, implying a larger persistent component.

3. **Variance Decomposition**:
   - Total variance of residuals (\( \sigma_\epsilon^2 \)) is split into:
     - Persistent variance (\( \sigma_\alpha^2 \)).
     - Transitory variance (\( \sigma_\eta^2 \)).

---

## **4. Mathematical Summary**

For the residual component of income \( \epsilon_{it} \):

### **Autocorrelation (\( \rho \))**
\[
\rho = \frac{\text{Cov}(\epsilon_{it}, \epsilon_{it-1})}{\text{Var}(\epsilon_{it-1})}
\]

### **Variance of Transitory Shocks**
\[
\sigma_\eta^2 = \sigma_\epsilon^2 - \rho^2 \cdot \sigma_{\epsilon, \text{lagged}}^2
\]

### **Variance of Persistent Shocks**
\[
\sigma_\alpha^2 = \sigma_\epsilon^2 - \sigma_\eta^2
\]

---

## **5. Intuition**

- **Persistent shocks (\( \alpha_i \))**:
  - Long-lasting effects that influence income across multiple periods.
  - Examples: innate ability, education, structural inequality.

- **Transitory shocks (\( \eta_{it} \))**:
  - Short-term, random deviations from expected income.
  - Examples: temporary job loss, seasonal bonuses.

- By decomposing income variance into these components, we can better understand **income stability** and **inequality dynamics**.
