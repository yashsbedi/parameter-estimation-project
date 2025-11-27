# parameter-estimation-project


## Angular Distribution Parameter Estimation  
### Monte Carlo Simulation, Statistical Fitting, and Bayesian Inference

This project studies how well the parameters a1 and a2 can be measured in the angular model

f(x) = 1 + a1*x + a2*x^2   with   x = cos(theta)

The work brings together Monte Carlo sampling, several estimation methods, detector effects, and Bayesian MCMC.  
It was developed as part of a parameter estimation project and is written fully in Python inside a Jupyter notebook.

---

## Contents

- Monte Carlo event generator for angular distributions  
- Forward-backward asymmetry estimator (AFB)  
- Binned chi-square fitting using exact bin integrals  
- Unbinned maximum-likelihood estimator (MLE)  
- Study of acceptance cuts and angular smearing  
- Fisher information and Cramer-Rao bounds  
- Bayesian MCMC fits using Metropolis-Hastings  
- Likelihood ratio test for the forward-backward asymmetry  
- Full report and code combined in one notebook

---

## Project Goals

1. Generate synthetic angular data that follow a quadratic distribution.  
2. Measure a1 and a2 using different statistical methods.  
3. Compare each method in terms of precision, stability, and scaling with sample size.  
4. Model realistic detector effects such as angular acceptance and finite resolution.  
5. Check the statistical limits using Fisher information and Cramer-Rao bounds.  
6. Perform Bayesian parameter estimation to obtain full posterior shapes.  
7. Test whether a1 is non-zero using a likelihood ratio test.

---

## Main Methods

### 1. Monte Carlo Sampling  
Events are drawn using acceptance-rejection sampling. The generator can include  
- full acceptance (|cos(theta)| < 1),  
- restricted acceptance (e.g. 0.9 or 0.95),  
- angular smearing to mimic detector resolution.

### 2. Forward-Backward Asymmetry  
A simple observable that compares counts with cos(theta) > 0 and cos(theta) < 0.  
Useful as a baseline but less precise than shape-based fits.

### 3. Binned Chi-Square Fit  
Events are placed into fixed bins of cos(theta).  
Exact bin integrals are used so that the prediction is fully analytic.  
This gives fits for a1 and a2 and produces chi-square and deviance diagnostics.

### 4. Unbinned Maximum Likelihood Fit  
Each event is used directly.  
This method retains the most information and gives the smallest spread in a1 and a2.

### 5. Bayesian MCMC  
Metropolis-Hastings sampling is used to build the posterior for  
- a1 (with a2 fixed)  
- (a1, a2) jointly  

The chains show the link between a1 and a2 and match the likelihood-based results.

### 6. Likelihood Ratio Test  
A test is added to check whether a1 is consistent with zero.  
Under Wilks' theorem, the statistic follows a chi-square distribution with one degree of freedom.

---

## Key Findings

- All methods recover the correct parameters.  
- Errors scale as 1/sqrt(N) for all three estimators.  
- The unbinned likelihood fit gives the smallest spread and comes closest to the Cramer-Rao limit.  
- Acceptance cuts (e.g. |cos(theta)| < 0.9) reduce sensitivity by around 5 percent for a1.  
- Angular smearing of a few mrad produces a further loss of precision.  
- Binned and unbinned fits agree closely when enough bins are used.  
- MCMC posteriors match the frequentist fits and show clear a1-a2 correlation.  
- The likelihood ratio test rejects a1 = 0 with strong significance for large samples.

---

## Notebook Structure

The notebook is written in a combined report-and-code format:  
- Report sections explain the physics and statistical reasoning.  
- Code cells contain the event generator, the fitters, and analysis tools.  
- Figures are produced directly inside the notebook.  
- Google-style Python docstrings are used throughout.

---

## Skills Demonstrated

- Statistical modelling  
- Simulation and Monte Carlo methods  
- Parameter estimation  
- Maximum likelihood and chi-square fitting  
- Bayesian inference and MCMC  
- Numerical optimisation  
- Data visualisation with Matplotlib  
- Clean Python design and documentation  
- Understanding detector acceptance and resolution  
- Scientific reporting inside a Jupyter notebook

---

## How To Run

1. Clone the repository  

   git clone https://github.com/USERNAME/REPO-NAME.git

2. Install Python requirements  

   pip install numpy scipy matplotlib

3. Open the notebook  

   jupyter notebook

4. Run the cells from top to bottom.

---

## Possible Extensions

- Likelihood ratio tests for both a1 and a2  
- Systematic bias studies  
- Testing alternative sampling strategies  
- Hamiltonian MCMC or NUTS for faster mixing  
- Applying the framework to real detector data

---

## Contact

Feel free to reach out if you want to discuss the methods or the code.
