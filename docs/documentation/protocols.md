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

## 8.Preparation of microfluidic chips for PANCED. 
The microfluidic chips were designed using AUTOCAD, and built bypoly(dimethylsiloxane) (PDMS, Dow Corning Corp.) using standard soft-lithography methods. UV exposure was utilized to prepare SU8-2015 negative photoresist (MicroChem Corp.) mold a silicon wafer.   A 10% (w/w) curing agent was added and poured onto the mold. The mold cross-linked at 65 °C overnight after degassing under vacuum condition, followed by which PDMS was spalled off and punched with a 1 mm diameter biopsy punch, and then bound to glass microscope slide using oxygen plasma system. The electrode hole of sorting chips were filled with low-temperature solder (Indium Corp.) and incubated at 110 °C for 30 min. Electrical wire were inserted to the hole before the metal solidifies.

## 9.Preparation of droplets for PANCED. 
20 μm dropmaker chip was applied to generate 20 pL droplets at 4000 Hz by flow-focusing of two aqueous streams of host strain (containing 10 μM GFP1-10) and M13 phage (2.5 μL/min each) with two streams of HFE7500 fluorinated oil (3 M) (10 μL min−1) containing 4w/w% FluoSurf surfactant. The generated droplets flowed off-chip through PTEF tubing to a collector, and were incubate at 37 °C for 4 h.

## 10.Droplets sorting for PANCED.
The droplets were reloaded (0.2 μL/min) and spaced-out at a flow-focusing junction with HFE7500 fluorinated oil (3 M) (1 μL/min). The droplets were detected and analyzed by the optical setup (λex = 488 nm; λem = 525 nm) and fluorescent droplets were sorted at 500 Hz by applying an AC field pulse (30 kHz; 700–1000 V; 0.5 ms). The sorted droplets were collected in a collector. After emulsification, phages were collected and amplified using the E. coli S1030 containing the pJC175e plasmid.

## 11.Protein purification and SDS-PAGE.
The E. coli BL21 (DE3) strain containing pET28a-Clo-DPEase was cultured in LB media with 50 mg/L kanamycin at 37 °C and at the rotate speed of 200 rpm. When OD600 value reached 0.6, 1 mM IPTG was added to media and the strain was cultured for overnight. Bacteria was resuspended by PBS. After high-pressure distillation, the supernatant was purified by HisSep Ni-NTA 6FF Chromatography Column according to the instruction manual (Yeasen Biotech). SDS-PAGE was performed according to the instructions of User Manual in the Precast Protein Plus Gel Kit (Yeasen Biotech). 20 μg of total extracted or purified protein was resolved on a 10% denaturing SDS polyacrylamide gel.

## 12.Enzymatic assay.
The activity of amylase was determined using α-amylase (α-AL) Activity Assay Kit (Solarbio) according to the user manual. The enzyme activity of DPEase was measured by determining the D-allulose catalyzed from D-fructose per unit time. The enzyme was incubated at 20°C with 0-1 mM Mn2+ for 4 h at 4°C. This process was crucial for activating the enzyme. The reactions were performed at 30-70 °C for 10-60 min in 50 mM PBS buffer (pH 4.0-10.0) containing 1 g/L 20 mM fructose and 0.2 μg/mL of enzyme. To terminate the enzymatic reaction, the reaction mixture was heated in boiling water for 10 min. The D-allulose production was measured using high-performance liquid chromatography (HPLC). Finally, one unit of DPEase activity was defined as the amount of the enzyme required to produce 1 μmol of D-allulose per min under the optimal reaction conditions. 

## 13.Statistical analysis.
Statistical analyses were performed using the two-tailed Student’s t-test, one-way analysis of variance (ANOVA), or Mann-Whitney nonparametric U-test with the GraphPad Prism 9.0. * indicates that a P value less than 0.01 was considered statistically significant. All experiments were performed with three replicates, and the error bars in the figure legends represent means ± s.e.m values.

