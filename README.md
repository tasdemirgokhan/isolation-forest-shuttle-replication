How the experiment was reproduced
Data. The UCI training and test files are pooled (58,000 rows). Classes 2, 3, 5, 6, 7 are the anomalies, as in the paper's Table 2. Class 4 is removed because it is the only class whose removal gives the paper's n = 49,097. Result: 3,511 anomalies (7.15 %), checked against Table 2 by assertions.
iForest is implemented from the paper's Algorithms 1–3 and Equations 1–2 and cross-checked against scikit-learn (0.9970 ± 0.0005).
ORCA follows its own paper (Bay & Schwabacher, 2003) for the details the iForest paper leaves out: the score is the average distance to the k nearest neighbours, attributes are scaled to [0,1], and it runs a randomised scan with cutoff pruning in blocks of 1,000. The AUC is computed from ORCA's top-N output.
LOF is scikit-learn's, with k = 10.
Protocol. All n points are used for fitting and scoring; labels are used only to compute AUC. Randomised methods are run with 10 seeds. Timings are CPU time on one thread, as in the paper.
Every setting is tagged in the notebook (Step 14) as coming from the paper, from ORCA's paper, or as our own choice where the paper leaves it open


requirements
numpy>=2.5
scikit-learn>=1.9
matplotlib>=3.11
notebook
 
