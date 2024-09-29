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

## 5. Plasmid construction.
1. Strains and Plasmids: The strains, plasmids, and primers：  The E. coli strains S1030 (#105063), MP4 (#69652), and pJC175e (#79219) were purchased from Addgene. The E. coli BL21(DE3) and DH5α strains were purchased from TransGene, and the M13 phage was obtained from Zymostar.
2. Gene Synthesis: The target genes, including psiR, PSPpsiO, gIII, GFP11-gIII, DPEases, α-amylases, GFP1-10, and T7 RNAP
3. Gene Amplification:The genes were amplified using Hieff Canace® Plus High-Fidelity DNA Polymerase.
4. Plasmid Construction: The amplified genes were inserted into the appropriate plasmids  using the Hieff Clone® Plus One Step Cloning Kit. This kit facilitated the seamless cloning of the target DNA fragments into the desired plasmids.


## 6. Construction of primary M13 phage. 
The recombinant M13 bacteriophages were constructed as previous reported. Gene Amplification: DNA fragments of Clo-DPEase were amplified using synthesized genes as templates.

M13 Genome Preparation: The M13 genome without the gIII gene was amplified using the M13 phage as a template.
Cloning: The Clo-DPEase fragments were cloned into the M13 genome using the Multi One Step Cloning Kit (Yeasen Biotechnology).

Transformation and Packaging: The cloned M13 phage genome was transformed into E. coli S1030 containing the pJC175e plasmid to package the recombinant M13 phages.
Phage Titer Measurement: The phage titer was determined using the bilayer agarose plate method.

## 7. Mutagenesis
The enzymatic mutagenesis was performed according to previous report. For ARTP mutagenesis, a condition of 120 W and 45 s was utilized; for microwave mutagenesis, a condition of 400 W and 60 s on ice was utilized; for UV mutagenesis, a 254 nm condition of 30 W and 300 s was utilized. The phages were infected the E. coli S1030 containing the pJC175e plasmid and restored in 2 × YT medium (20 g/L tryptone, 10 g/L yeast extract and 10 g/L NaCl) at 37 °C for 6 h. After centrifuge at the speed of 3000 × g for 5 min, the supernatant was collected and used to determine the titer of phage.


