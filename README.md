In this project, I tried to classify EEG data to positive and negative emotions using MLP and RBF with 2 different feature extraction methods:
1. Manual Feature Extraction
-Statistic features:
   Variance, Max abs, Kurtosis, Skewness
-Features in frequency domain:
   Theta, Alpha, Lbeta, Mbeta, Hbeta, Gamma, Median freq, Mean freq, Entropy, OBW, Max power, Band power
     
2. Evolutionary algorithms/swarm intelligence algorithms

- In phase 1, manual feature extraction methods are used and for feature selection I used Fisher with two views:
1. I used 1D Fisher to extract 60 features.
2. First I extracted 150 features with 1D Fisher, then I passed them to a multidimensional Fisher and got 60 features using calculating trace.

In main function, after getting features, noise is added in order to avoid overfitting.
In the end, features are passed to both MLP and RBF classifiers.
To validate the model, I used 5-fold cross-validation.


- In Phase 2, features are extracted using Evolutionary Algorithm.
Firts, 50 features with best scores are extracted using 1D Fisher, then a population with 50 chromosomes of size 50 is formed whose alleles are random index of features matrix.
To change in every generation, mutation and crossover is used.

In the end, features are passed to both MLP and RBF classifiers.
To validate the model, I used 5-fold cross-validation.

