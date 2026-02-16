# PSO Linear Regression Optimizer

A Particle Swarm Optimization (PSO) implementation for training linear regression models on the California Housing dataset, with comparison against the closed-form analytical solution.


This project demonstrates the application of Particle Swarm Optimization (PSO)—a bio-inspired metaheuristic algorithm—for optimizing the weights of a linear regression model. PSO performs derivative-free optimization by simulating the social behavior of bird flocking or fish schooling to navigate the solution space efficiently.
The implementation minimizes the Mean Squared Error (MSE) loss function and achieves performance comparable to the closed-form normal equation solution, validating PSO's effectiveness for convex optimization problems.

## Dataset

#### California Housing Dataset


+ Source: Original dataset from Kaggle/Scikit-learn


+ Features used: 8 numeric predictors (longitude, latitude, housing_median_age, total_rooms, total_bedrooms, population, households, median_income)


+ Target: median_house_value


+ Preprocessing: Removed 207 samples with missing values → 20,433 clean samples


## PSO Configuration

```
| Parameter           | Value        | Description                                |
|---------------------|-----------   |--------------------------------------------|
| Swarm size          | 30           | Number of particles in the swarm           |
| Dimensions          | 9            | 8 feature weights + 1 bias term            |
| Max iterations      | 100          | Termination criterion                      |
| Inertia weight      | 0.7          | Balances exploration vs. exploitation      |
| Cognitive           | 1.5          | Personal best influence (self-confidence)  |
| Social              | 1.5          | Global best influence (swarm intelligence) |
| Position bounds     | [-1e6, 1e6]  | Clipped to prevent numerical instability   |
| Position init.      | U[-1, 1]     | Uniform random initialization              |
| Velocity init.      | U[-0.1, 0.1] | Small random velocities                    |
| Random seed         | 42           | Ensures reproducible results               |
| Objective           | Minimize MSE | Mean Squared Error loss function           |
```

## Project Structure

```
PSO/
├── code.ipynb          # Main implementation (Jupyter notebook)
├── dataset/
│   └── housing.csv     # California Housing dataset
├── README.md           # This file

```
## Results
```
Cleaned data: 20433 samples, 8 features

Starting PSO optimization...
  Iteration   1: Best MSE = 0.594380
  Iteration  20: Best MSE = 0.378266
  Iteration  40: Best MSE = 0.369039
  Iteration  60: Best MSE = 0.364272
  Iteration  80: Best MSE = 0.364184
  Iteration 100: Best MSE = 0.364143

Computing closed-form solution...
  Closed-form MSE: 0.363088

Final Results:
  PSO MSE       : 0.364143
  Closed-form MSE: 0.363088
```

## References
1. Kennedy, J., & Eberhart, R. (1995). Particle swarm optimization. Proceedings of ICNN'95.
2. California Housing Dataset: Pace, R.K. & Barry, R. (1997). Journal of Geographical Systems.
3. Engelbrecht, A.P. (2006). Fundamentals of Computational Swarm Intelligence. Wiley.


Note: Developed for academic research in optimization algorithms and machine learning.
