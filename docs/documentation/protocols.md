# Protocols

## 1. Data Collection
The datasets include fasta files of genome CDS and proteins. And these datasets have annotations for temperature, salinity, or pH. The extreme thermophilic data comes from the following database: JCM , OGT, TEMPURA and ThermoBase. We download extreme halophilic data from JCM and parse the HTML to extract information about strains’ media using Python and calculate the mass content of sodium chloride as salinity. Extreme acidophilic bacteria data from ThermoBase and previous report. A total of 13672, 6987, and 361 data records with temperature, salinity, or pH annotations were collected. 

## 2. Construction of Extreme Microbial Prediction Model iExtreme
Construct three prediction models named iExtreme-T, iExtreme-P and iExtreme-S separately to distinguish between microorganisms with extreme thermophilic (Temp ≥ 70 ℃), extreme acidophilic (pH ≤ 5), and extreme halophilic (salinity ≥ 15%). All models are classification models built using the scikit-learn package (version 1.3.2) and Python (version 3.8.19), and the classification algorithm is SVC (Support Vector Classification). The training process includes building a training dataset, optimizing parameters, and selecting the best model. Firstly, construct training data.

## 3. Evaluation metrics of models
To evaluate the predictive ability of the model, the following metrics are used：accuracy (ACC), precision (Prec), Recall (Rec) and F1 Score (F1) as in Eqs. (1)-(4)


$$
(1)~~ACC = \frac{TP+TN}{TP+TN+FP+FN}
$$

$$
(2)~~Prec = \frac{TP}{TP+FP}
$$

$$
(3)~~Rec = \frac{TP}{TP+FN}
$$

$$
(4)~~F1 = 2 \times \frac{Prec \times Rec}{Prec+Rec}
$$



True positives (TP) represent the number of EMs (Extreme microorganisms) correctly predicted as EMs; false positives (FP) are the number of non-EMs incorrectly predicted as EMs; true negatives (TN) are the number of non-EMs correctly predicted as non-EMs; and false negatives (FN) are the number of EMs incorrectly predicted as non-EMs.

## 4. Extreme Microbial Screening
Using the iExtreme model to predict extreme microorganisms from an public microbial database, a total of 121657 data were collected from NCBI, GOMC, ProPan, Progenome, UBA and P10K Databases. 





