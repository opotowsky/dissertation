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
**Methodology and Implementation**

- Training Data Simulations
   - FC Sim / Simulation Fidelity
   - Labels
   - Features
- Information Reduction 
   - Nuclide Masses : randomly applied uniform error
   - Gamma Spectra (GADRAS) : covers all info reduc steps + counting error implementation
- ML Implementation (?CHTC?, ?testing?)
   - Scikit Learn
   - Max Likelihood Calcs
- Performance Evaluation 
   - Error metrics choices (move discussion of Ch 2 metrics choices to here)
      - Rxtr type discussion
      - Regression: metrics choices informed by results (distribution of absolute error), but chronologically makes sense here. 
   - SFCOMPO (details of the testing set, missing values, etc)
   - Maybe: Diagnostic Curves
   - Discussion of features distributions here? or above? or below in alg performance discussion? 

---------
Chapter 4
---------
**Experimental Results**

- Experiment 1 : Scikit + MLL on isotopics; SFCOMPO comparison
   - Quick overview (essentially outline relevant processes from Ch 3)
   - Prediction Error WRT Random Injected Error
      - dicuss alg performance. Include mean and median absolute errors (forthcoming in next batch of results)
      - might want to show learning curves to discuss generalizability of traditional ML methods versus MLL
      - would a full likelihood calc w predictions be a good addition to the story or a distraction?
   - SFCOMPO Results
      - MLL does better with null (0) values, Scikit does better with imputed null values.
      - Rxtr type prediction is quite poor: investigate? 
      - Is there any utility in discussing a few cases in detail?
- Experiment 2 : Scikit + MLL on processed spectra
   - Quick overview (essentially outline relevant processes from Ch 3)
   - Explanation of plots 
      - esp the x-axis
      - "baselines" and "goal lines"
   - Prediction Error WRT Detector
      - 
      - check on variation in decision tree performance among pred types. this is likely from the alg hyperparameters. 

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


