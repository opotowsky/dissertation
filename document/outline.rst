====================
Dissertation Outline
====================

---------
Chapter 1
---------
**Introduction**

- Motivation
- Methodology
- Goals

---------
Chapter 2
---------
**Literature Review**

- Nuclear Forensics
   - Pre and Post detonation
   - Inverse Problem
- Machine Learning
   - Algs
      - kNN
      - Decision Trees
      - Maximum Log Likelihood Calculations
   - Alg Performance
      - Testing Error
      - Model Complexity (regularization, diagnostic plots intro)
- Applications of Statistical Methods to Nuclear Forensics
   - Dayman work, Others (Robel, Nicolaou, etc?)
   - Needs updates

---------
Chapter 3
---------
**Experiment 1 : on direct isotopics**

- Training Data Simulations
   - FC Sim / Simulation Fidelity
   - Labels
   - Features
- Information Reduction: Nuclide Masses
   - Randomly applied uniform error
   - Diff btw implementation for scikit and mll
- ML Implementation (?CHTC?, ?testing?)
   - Scikit Learn (incl hyperparam optimization)
   - Max Likelihood Calcs
- Performance Evaluation 
   - Error metrics choices (move discussion of Ch 2 metrics choices to here)
      - Rxtr type discussion. Acc, BalAcc, Conf Matrix. ROC TBD.
      - Regression: metrics choices informed by results (distribution of absolute error), 
        but chronologically makes sense here. Include mean/median absolute and relative errors
   - SFCOMPO 
      - details (spread of params) of the testing set
      - 2 treatments of missing values
   - Maybe: Diagnostic Curves
   - Discussion of features distributions here? or above? or below in alg performance discussion? 
- Results
   - Prediction Error WRT Random Injected Error
      - Discuss alg performance, and different conclusions from different error metrics 
      - Look at regression performance wrt rxtr type, and compare with results where rxtr type is already known
      - MAPE wrt true Y
      - Maybe: show learning curves to discuss generalizability of traditional ML methods versus MLL
      - Would a full likelihood calc w predictions be a good addition to the story or a distraction? (I think the latter)
   - SFCOMPO Results
      - MLL does better with null (0) values, Scikit does better with imputed null values.
      - Rxtr type prediction is quite poor: investigate? 
      - Is there any utility in discussing a few cases in detail?

---------
Chapter 4
---------
**Experiment 2 : on processed gamma spectra**

- Training Data Simulations
   - Reference back to labels
   - Features
- Information Reduction: Gamma Spectra (GADRAS) 
   - Info reduc steps: acts -> gammas -> drf/spectra -> choose energy windows -> processed spectra
   - Counting error implementation (same diff as above between mll and scikit)
- ML Implementation (Reference back, no differences here?) 
- Performance Evaluation 
   - Reference back
   - Hyperparam optimization (slight diff)
   - Explanation of plots 
      - esp the x-axis
      - "baselines" and "goal lines"
- Results
   - Prediction Error WRT Detector
      - Discuss alg performance, and different conclusions from different error metrics 
      - MAPE wrt true Y
      - Options that depend on choices from above, and can't be carried out for every data point: 
         - Could look at a few cases of performance wrt rxtr type, and maybe could run regression cases on known rxtr type 
         - Could run a few learning curves
      - (note to self) check on variation in decision tree performance among pred types after updating alg hyperparams

---------
Chapter 5
---------
**Conclusion**

- Conclusion
- Future Work
   - Filtering out problematic nuclides
   - Increase simulation fidelity
   - Algorithm optimization 
   - Feature set study; iso ratios
   - Serial Prediction (rxtr type first, then burnup, etc)


