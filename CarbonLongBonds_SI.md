# **Supporting Information for CLB18: A New Database for the Assessment of Density Functional Approximations.**

Pierpaolo Morgante, Roberto Peverati

Chemistry Program, Florida Institute of Technology, 150 W. University Blvd., 32901 Melbourne, FL, United States.

Email: [rpeverati@fit.edu](mailto:rpeverati@fit.edu)

## **Summary**

### Section S1: Convergence with respect to the basis set.

### Section S2: Convergence with respect to the integration grid.

### **Section S3:** Computational details.

### Section S4: $\text{A}_{\lambda}$ diagnostic for CLB18.

### Section S5: Bond lengths calculated with PBE and its hybrids.

### Section S6: Choice of the barrier heights subset for comparison with CLB18.

### Section S7: ARMSG and $A_{\lambda}$ values for the BH76 database.

### Section S8: References.
\newpage

## Note.

All optimized geometries (for all methods) can be found in our group's [GitHub page](https://github.com/peverati/CLB18).

For a more comprehensive set of results, we invite the interested reader to check out the associated Excel files, "CLB18_SuppInfo.xlsx", "CLB18_BH76_SuppInfo.xlsx", and "CLB18_BH76_SuppInfo_HFXStudy.xlsx". They can also be found on our group's [GitHub page](https://github.com/peverati/CLB18), together with the output files for all molecules in the BH76 dataset.
\newpage

## Section S1: Convergence with respect to the basis set.

The results reported in **Tables S1** and **S2** detail the basis set study we performed for the CLB18 database. More specifically, we considered the most common double-$\zeta$ basis sets to understand the results' dependence on the basis set size. We calculated the mean unsigned errors (MUEs, **Table S1**) and the mean signed errors (MSEs, **Table S2**). From the analysis of both tables, we see that there is no substantial difference among the results. Excluding basis sets with less than 10,000 basis functions in total (the minimal basis sets STO-3G, SBKJC, 3-21G, and pc-0), the B3LYP and B3LYP-D3(BJ) functionals can achieve a very good performance, with MUE < 0.04 Å, in all cases.

**Table S1** Performance of B3LYP and B3LYP-D3(BJ) with some common basis sets of double-$\zeta$ quality against the CLB18 database. The results are reported in order of increasing basis set size. All values are in Å. MUE = Mean unsigned error.

| Basis set       | Total number of basis functions | MUE (Å), B3LYP | MUE (Å), B3LYP-D3(BJ) |
| --------------- | ------------------------------- | -------------- | --------------------- |
| aug-cc-pVDZ$^a$ | 19,846                          | 0.022          | 0.013                 |
| aug-pc-1$^a$    | 19,846                          | 0.024          | 0.016                 |
| def2-SVPD       | 17,413                          | 0.037          | 0.017                 |
| def2-SVP        | 11,857                          | 0.032          | 0.028                 |
| cc-pVDZ$^b$     | 11,847                          | 0.032          | 0.020                 |
| pc-1$^b$        | 11,847                          | 0.034          | 0.019                 |
| 6-31G*$^a$      | 10,740                          | 0.028          | 0.017                 |
| def2-SV(P)      | 10,144                          | 0.035          | 0.022                 |
| aug-pc-0$^b$    | 10,085                          | 0.039          | 0.036                 |
| 3-21G           | 7,021                           | 0.066          | 0.057                 |
| pc-0$^c$        | 6,984                           | 0.051          | 0.055                 |
| SBKJC           | 6,222                           | 0.096          | 0.073                 |
| STO-3G          | 3,898                           | 0.055          | 0.068                 |

$^a$The def2-SVPD basis set and the associated pseudopotential were used for I.

$^b$The def2-SVP basis set and the associated pseudopotential were used for I.

$^c$The def2-SV(P) basis set and the associated pseudopotential were used for I.

The MSEs reveals the most striking difference in the behavior of the two functionals. In fact, the B3LYP approximation always (slightly) overestimates the bond lengths, as shown by its positive MSE with all basis sets. The addition of the -D3(BJ) empirical correction corrects this trend, most notably for the smallest basis sets considered, and it represents an improvement for most cases. In certain situations, however, the -D3(BJ) scheme overcorrects, thus resulting in a negative MSE, as in the case of the def2-SVP and the cc-pVDZ basis sets. We observed similar trends also for the CLB18_15 structure, as detailed in the main text. 

**Table S2** Performance of B3LYP and B3LYP-D3(BJ) with some common basis sets of double-$\zeta$ quality against the CLB18 database. The results are reported in order of increasing basis set size. All values are in Å. MSE = Mean signed error.

| Basis set        | Total number of basis functions | MSE (Å), B3LYP | MSE (Å), B3LYP-D3(BJ) |
| ---------------- | ------------------------------- | -------------- | --------------------- |
| aug-cc-pVDZ$^a$  | 19,846                          | 0.020          | 0.005                 |
| aug-pc-1$^a$     | 19,846                          | 0.022          | 0.011                 |
| def2-SVPD        | 17,413                          | 0.034          | 0.002                 |
| def2-SVP         | 11,857                          | 0.028          | –0.008                |
| cc-pVDZ$^b$      | 11,847                          | 0.031          | –0.003                |
| pc-1<sup>b</sup> | 11,847                          | 0.030          | 0.001                 |
| 6-31G*$^a$       | 10,740                          | 0.025          | 0.007                 |
| def2-SV(P)       | 10,144                          | 0.032          | 0.000                 |
| aug-pc-0$^b$     | 10,085                          | 0.026          | 0.032                 |
| 3-21G            | 7,021                           | 0.059          | 0.034                 |
| pc-0$^c$         | 6,984                           | 0.043          | 0.018                 |
| SBKJC            | 6,222                           | 0.099          | 0.077                 |
| STO-3G           | 3,898                           | 0.028          | 0.022                 |

$^a$The def2-SVPD basis set and the associated pseudopotential were used for I.

$^b$The def2-SVP basis set and the associated pseudopotential were used for I.

$^c$The def2-SV(P) basis set and the associated pseudopotential were used for I.

We experienced some serious convergence issues (despite multiple attempts with both the Gaussian and Q-Chem programs using different algorithms) when the augmented basis sets were used, most often with the B3LYP-D3(BJ) approximation. The least problematic basis set for both approximations was aug-cc-pVDZ, while the most problematic was aug-pc-1 for B3LYP-D3(BJ), and def2-SVPD for B3LYP (**Table S3**).

**Table S3** Convergence issues with B3LYP and B3LYP-D3(BJ) and the augmented basis sets with 13 structures (out of the 18) in the CLB18 database.

| Structure | def2-SVPD           | aug-cc-pVDZ         | aug-pc-1            |
| --------- | ------------------- | ------------------- | ------------------- |
| CLB18_1   | B3LYP, B3LYP-D3(BJ) | B3LYP, B3LYP-D3(BJ) | B3LYP, B3LYP-D3(BJ) |
| CLB18_2   |                     |                     | B3LYP-D3(BJ)        |
| CLB18_4   | B3LYP, B3LYP-D3(BJ) |                     | B3LYP-D3(BJ)        |
| CLB18_5   | B3LYP, B3LYP-D3(BJ) | B3LYP, B3LYP-D3(BJ) | B3LYP-D3(BJ)        |
| CLB18_6   | B3LYP, B3LYP-D3(BJ) | B3LYP, B3LYP-D3(BJ) | B3LYP-D3(BJ)        |
| CLB18_7   | B3LYP               | B3LYP-D3(BJ)        | B3LYP-D3(BJ)        |
| CLB18_8   | B3LYP, B3LYP-D3(BJ) |                     |                     |
| CLB18_9   | B3LYP-D3(BJ)        |                     | B3LYP-D3(BJ)        |
| CLB18_10  | B3LYP, B3LYP-D3(BJ) |                     |                     |
| CLB18_11  | B3LYP               |                     | B3LYP-D3(BJ)        |
| CLB18_13  |                     |                     | B3LYP-D3(BJ)        |
| CLB18_17  |                     | B3LYP, B3LYP-D3(BJ) | B3LYP-D3(BJ)        |
| CLB18_18  |                     | B3LYP-D3(BJ)        | B3LYP-D3(BJ)        |

## Section 2: Convergence with respect to the integration grid.

In this section, we report the calculated bond lengths (**Table S4**) using the B3LYP and B3LYP-D3(BJ) functionals with the 6-31G\* basis set and a selection of integration grids (Coarse, SG1, Fine, Ultrafine, and Superfine), as detailed in the main text. The same results are also reported in the Excel file called "CLB18_SuppInfo.xlsx" that can be found in our group's GitHub page.

**Table S4** Bond lengths (in Å) calculated with the B3LYP/6-31G\* and B3LYP-D3(BJ)/6-31G\* levels of theory with five popular integration grids. The mean signed error (MSE), and the average computational time (in s) are reported as well for each grid (last two rows).

| Structure                             | B3LYP, Coarse | B3LYP, SG1 | B3LYP, Fine | B3LYP, Ultrafine | B3LYP, Superfine | B3LYP-D3(BJ), Coarse | B3LYP-D3(BJ), SG1 | B3LYP-D3(BJ), Fine | B3LYP-D3(BJ), Ultrafine | B3LYP-D3(BJ), Superfine |
| ------------------------------------- | ------------- | ---------- | ----------- | ---------------- | ---------------- | -------------------- | ----------------- | ------------------ | ----------------------- | ----------------------- |
| CLB18_1                               | 1.699         | 1.709      | 1.710       | 1.710            | 1.711            | 1.647                | 1.659             | 1.660              | 1.660                   | 1.660                   |
| CLB18_2                               | 1.719         | 1.733      | 1.731       | 1.731            | 1.731            | 1.689                | 1.703             | 1.702              | 1.702                   | 1.702                   |
| CLB18_3                               | 1.712         | 1.724      | 1.724       | 1.724            | 1.724            | 1.712                | 1.721             | 1.722              | 1.723                   | 1.723                   |
| CLB18_4                               | 1.7743        | 1.7639     | 1.7673      | 1.7658           | 1.7658           | 1.7307               | 1.7590            | 1.7536             | 1.7511                  | 1.7514                  |
| CLB18_5                               | 1.8087        | 1.8266     | 1.8230      | 1.8247           | 1.8246           | 1.7763               | 1.8235            | 1.8091             | 1.8080                  | 1.8073                  |
| CLB18_6                               | 1.8518        | 1.8358     | 1.8322      | 1.8337           | 1.8335           | 1.7811               | 1.8340            | 1.8168             | 1.8160                  | 1.8156                  |
| CLB18_7                               | 1.7061        | 1.6931     | 1.6986      | 1.6997           | 1.7000           | 1.6824               | 1.6953            | 1.6915             | 1.6895                  | 1.6895                  |
| CLB18_8                               | 1.7462        | 1.7315     | 1.7313      | 1.7312           | 1.7313           | 1.7354               | 1.7307            | 1.7296             | 1.7289                  | 1.7289                  |
| CLB18_9                               | XXX$^a$       | 1.7370     | 1.7295      | 1.7321           | 1.7300           | XXX$^a$              | 1.7244            | 1.7206             | 1.7243                  | 1.7238                  |
| CLB18_10                              | 1.7412        | 1.7304     | 1.7299      | 1.7306           | 1.7306           | 1.7292               | 1.7263            | 1.7258             | 1.7262                  | 1.7263                  |
| CLB18_11                              | 1.7483        | 1.7516     | 1.7497      | 1.7495           | 1.7498           | 1.7309               | 1.7338            | 1.7290             | 1.7292                  | 1.7292                  |
| CLB18_12                              | 1.8316        | 1.8285     | 1.8277      | 1.8278           | 1.8278           | 1.8274               | 1.8246            | 1.8236             | 1.8238                  | 1.8238                  |
| CLB18_13                              | 1.6348        | 1.6215     | 1.6145      | 1.6140           | 1.6141           | 1.6321               | 1.6218            | 1.6128             | 1.6120                  | 1.6119                  |
| CLB18_14                              | 1.7256        | 1.7337     | 1.7320      | 1.7299           | 1.7304           | 1.7107               | 1.7143            | 1.7122             | 1.7104                  | 1.7111                  |
| CLB18_16                              | 1.8842        | 1.9778     | 1.9769      | 1.9732           | 1.9730           | 1.8650               | 1.9310            | 1.9328             | 1.9302                  | 1.9305                  |
| CLB18_17                              | 1.9235        | 2.0139     | 2.0096      | 1.9745           | 1.9743           | 1.8748               | 1.9544            | 1.9478             | 1.9487                  | 1.9484                  |
| CLB18_18                              | 2.0041        | 2.0025     | 2.0203      | 2.0138           | 2.0143           | 1.9277               | 1.9430            | 1.9406             | 1.9434                  | 1.9424                  |
| MSE                                   | 0.016         | 0.029      | 0.028       | 0.025            | 0.025            | –0.009               | 0.012             | 0.008              | 0.007                   | 0.007                   |
| Average time for one SCF cycle, s$^b$ | 252           | 288        | 240         | 540              | 564              | 444                  | 312               | 252                | 492                     | 600                     |

$^a$This structure could not be converged.

$^b$This value is calculated per single thread.

## Section S3: Computational details.

As reported in the main text, we used 24 approximations to perform geometry optimizations for all the structures in the CLB18 database. We tested seven generalized gradient approximation (GGA) functionals, namely BLYP,[@becke1988a;@lee1988] BLYP-D3(BJ),[@becke1988a;@lee1988;@grimme2011] BP86,[@becke1988a;@perdew1986] BP86-D3(BJ),[@becke1988a;@perdew1986;@grimme2011] PBE,[@perdew1996] PBE-D3(BJ),[@perdew1996;@grimme2011] B97-D3(BJ),[@grimme2006c;@grimme2011], one meta-GGA functional (TPSS-D3(BJ),[@tao2003;@grimme2011]), four hybrid GGA functionals, B3LYP,[@becke1988a;@lee1988;@becke1993;@stephens1994] B3LYP-D3(BJ),[@becke1988a;@lee1988;@becke1993;@stephens1994;@grimme2011] PBE0,[@perdew1996;@adamo1999;@ernzerhof1999] PBE0-D3(BJ),[@perdew1996;@adamo1999;@ernzerhof1999;@grimme2011], three hybrid meta-GGA functionals, M06-2X,[@zhao2008] M06-2X-D3(0),[@zhao2008;@goerigk2015] TPSSh-D3(BJ)[@staroverov2003;@grimme2011]), and the Hartree-Fock (HF) method.[@hartree1928;@hartree1928a;@fock1930] In addition, we tested four semi-empirical methods (AM1,[@dewar1985] PM3,[@stewart1989;@stewart1989a] PM6,[@stewart2007] PM7[@stewart2013]). For these approximations, we used the Gaussian program.[@frisch2016] We tested also two low-cost methods (HF-3c[@sure2013] and PBEh-3c[@grimme2015]) using the Q-Chem program,[@shao2015] and two tight-binding approximations (GFN-xTB1[@grimme2017] and GFN-xTB2[@bannwarth2019]) with the xTB program.[@bannwarth2020] For all functionals, we used the 6-31G*[@ditchfield1971;@hehre1972;@hariharan1973;@dill1975;@francl1982;@gordon1982;@rassolov2001] basis set and the fine integration grid (ultrafine for meta-GGA functionals). A visual summary is reported in **Table S5**

**Table S5.** Computational methods used in this study. We listed the functional type (Generalized Gradient Approximation (GGA), meta-GGA, global and range-separated hybrid GGA or meta-GGA) together with the quantum chemistry program used, the percentage of exact exchange included in the approximation, and the respective references.

| Functional/Method | Type                                        | Program  | % Exact Exchange | References                                                  |
| ----------------- | ------------------------------------------- | -------- | ---------------- | ----------------------------------------------------------- |
| HF-3c             | Low cost, corrected HF                      | Q-Chem   | 100              | [@sure2013]                                                 |
| PBEh-3c           | Low cost, hybrid GGA                        | Q-Chem   | 42               | [@grimme2015]                                               |
| AM1               | Semi-empirical                              | Gaussian | N/A              | [@dewar1985]                                                |
| PM3               | Semi-empirical                              | Gaussian | N/A              | [@stewart1989;@stewart1989a]                                |
| PM6               | Semi-empirical                              | Gaussian | N/A              | [@stewart2007]                                              |
| PM7               | Semi-empirical                              | Gaussian | N/A              | [@stewart2013]                                              |
| GFN-xTB1          | Tight-binding                               | xTB      | N/A              | [@grimme2017]                                               |
| GFN-xTB2          | Tight-binding                               | xTB      | N/A              | [@bannwarth2019]                                            |
| HF                | Hartree-Fock                                | Gaussian | 100              | [@hartree1928;@hartree1928a;@fock1930]                      |
| BLYP              | GGA                                         | Gaussian | 0                | [@becke1988a;@lee1988]                                      |
| BLYP-D3(BJ)       | Dispersion-corrected GGA                    | Gaussian | 0                | [@becke1988a;@lee1988;@grimme2011]                          |
| BP86              | GGA                                         | Gaussian | 0                | [@becke1988a;@perdew1986]                                   |
| BP86-D3(BJ)       | Dispersion-corrected GGA                    | Gaussian | 0                | [@becke1988a;@perdew1986;@grimme2011]                       |
| PBE               | GGA                                         | Gaussian | 0                | [@perdew1996]                                               |
| PBE-D3(BJ)        | Dispersion-corrected GGA                    | Gaussian | 0                | [@perdew1996;@grimme2011]                                   |
| B97-D3(BJ)        | Dispersion-corrected GGA                    | Gaussian | 0                | [@grimme2006c;@grimme2011]                                  |
| TPSS-D3(BJ)       | Dispersion-corrected meta-GGA               | Gaussian | 0                | [@tao2003;@grimme2011]                                      |
| B3LYP             | Global hybrid GGA                           | Gaussian | 20               | [@becke1988a;@lee1988;@becke1993;@stephens1994]             |
| B3LYP-D3(BJ)      | Dispersion-corrected global hybrid GGA      | Gaussian | 20               | [@becke1988a;@lee1988;@becke1993;@stephens1994;@grimme2011] |
| PBE0              | Global hybrid GGA                           | Gaussian | 25               | [@perdew1996;@adamo1999;@ernzerhof1999]                     |
| PBE0-D3(BJ)       | Dispersion-corrected global hybrid GGA      | Gaussian | 25               | [@perdew1996;@adamo1999;@ernzerhof1999;@grimme2011]         |
| M06-2X            | Global hybrid meta-GGA                      | Gaussian | 54               | [@zhao2008]                                                 |
| M06-2X-D3(0)      | Dispersion corrected global hybrid meta-GGA | Gaussian | 54               | [@zhao2008;@goerigk2015]                                    |
| TPSSh-D3(BJ)      | Dispersion corrected global hybrid meta-GGA | Gaussian | 10               | [@staroverov2003;@grimme2011]                               |

## Section S4: $\text{A}_{\lambda}$ diagnostic for CLB18.

The $A_\lambda$ diagnostic is a tool to investigate the multi-reference (MR) character of large molecules.[@fogueri2013] The general formula to calculate this parameter is:

$A_{\lambda*100}= \frac{1-\frac{\text{TAE}(\lambda)}{\text{TAE}[0]}}{\lambda}$

where $\text{TAE}[\lambda]$ is the total atomization energy calculated with the hybrid PBE functional having $\lambda$ percent HF exchange, and $\text{TAE}[0]$ is the total atomization energy calculated at the PBE level. According to ref. [fogueri2013], values that are < 0.1 are usually unproblematic. We see that this is the case for almost all the structures in the CLB18 database. The only structure where $A_\lambda$ is larger than 0.1 is CLB18_16. As explained in the main text, we do not know whether the structure is MR or not. We did not experience any convergence issues when using any of the hybrid functionals, and inclusion of HF exchange is not detrimental. All the numerical values used to obtain the $A_\lambda$ parameter are reported in the Excel files called "CLB18_SuppInfo.xlsx" and "CLB18_BH76_SuppInfo.xlsx" that are available on our group's GitHub page.

![**Figure S1** Values of the $A_\lambda$ MR diagnostics for all structures in the CLB18 database. Problematic values according to ref. [fogueri2013] are reported in bold. For the values of the structures in the BH76 database, see **Figure 4** in the main text.](Figures_CLB18/CLB18_MR_Diagnostics-CLB18.jpg)

**Figure S1** Values of the $A_\lambda$ MR diagnostics for all structures in the CLB18 database. Problematic values according to ref. [fogueri2013] are reported in bold. For the values of the structures in the BH76 database, see **Figure 4** in the main text.

## Section S5: Bond lengths calculated with PBE and its hybrids.

We report in this section (**Table S6**) the bond lengths calculated with PBE and all its hybrids we considered here. As explained in the main text, we varied the percentage of HF exchange between 0% (PBE) and 100% (corresponding to using the PBE correlation with the HF method) in increments of 10%. We also included the PBE0 functional in this treatment, as well as the hybrid with 15% HF exchange, for additional comparison.

**Table S6** Calculated bond lengths and mean unsigned errors (MUEs) for the PBE functional and its hybrids, obtained by increasing the percentage of HF exchange from 0% to 100%. The PBE0 functional (25%) and the hybrid with 15% HF exchange are also included.

| Structure      | PBE    | PBE+10%HF | PBE+15%HF | PBE+20%HF | PBE0   | PBE+30%HF | PBE+40%HF | PBE+50%HF | PBE+60%HF | PBE+70%HF | PBE+80%HF | PBE+90%HF | PBE+100%HF |
| -------------- | ------ | --------- | --------- | --------- | ------ | --------- | --------- | --------- | --------- | --------- | --------- | --------- | ---------- |
| CLB18_1        | 1.699  | 1.687     | 1.682     | 1.678     | 1.674  | 1.670     | 1.662     | 1.655     | 1.648     | 1.642     | 1.636     | 1.630     | 1.625      |
| CLB18_2        | 1.724  | 1.712     | 1.706     | 1.701     | 1.696  | 1.692     | 1.683     | 1.674     | 1.666     | 1.659     | 1.652     | 1.645     | 1.639      |
| CLB18_3        | 1.732  | 1.714     | 1.706     | 1.700     | 1.693  | 1.687     | 1.675     | 1.665     | 1.656     | 1.647     | 1.640     | 1.633     | 1.626      |
| CLB18_4        | 1.7683 | 1.7458    | 1.7367    | 1.7284    | 1.7208 | 1.7140    | 1.7018    | 1.6913    | 1.6820    | 1.6736    | 1.6660    | 1.6591    | 1.6527     |
| CLB18_5        | 1.8362 | 1.7977    | 1.7844    | 1.7729    | 1.7626 | 1.7534    | 1.7376    | 1.7244    | 1.7131    | 1.7031    | 1.6942    | 1.6863    | 1.6790     |
| CLB18_6        | 1.8435 | 1.8039    | 1.7891    | 1.7766    | 1.7657 | 1.7562    | 1.7400    | 1.7270    | 1.7155    | 1.7054    | 1.6966    | 1.6885    | 1.6812     |
| CLB18_7        | 1.6951 | 1.6836    | 1.6783    | 1.6734    | 1.6687 | 1.6642    | 1.6556    | 1.6481    | 1.6375    | 1.6307    | 1.6241    | 1.6177    | 1.6117     |
| CLB18_8        | 1.7390 | 1.7199    | 1.7120    | 1.7047    | 1.6977 | 1.6918    | 1.6806    | 1.6708    | 1.6619    | 1.6540    | 1.6467    | 1.6400    | 1.6338     |
| CLB18_9        | 1.7506 | 1.7175    | 1.7051    | 1.6964    | 1.6851 | 1.6770    | 1.6625    | 1.6500    | 1.6392    | 1.6297    | 1.6209    | 1.6131    | 1.6058     |
| CLB18_10       | 1.7391 | 1.7197    | 1.7116    | 1.7043    | 1.6975 | 1.6913    | 1.6802    | 1.6704    | 1.6615    | 1.6535    | 1.6463    | 1.6396    | 1.6333     |
| CLB18_11       | 1.7449 | 1.7296    | 1.7227    | 1.7164    | 1.7105 | 1.7048    | 1.6944    | 1.6851    | 1.6764    | 1.6684    | 1.6609    | 1.6539    | 1.6474     |
| CLB18_12       | 1.8256 | 1.8214    | 1.8194    | 1.8174    | 1.8155 | 1.8136    | 1.8099    | 1.8062    | 1.8027    | 1.7993    | 1.7960    | 1.7927    | 1.7896     |
| CLB18_13       | 1.6294 | 1.6198    | 1.6154    | 1.6113    | 1.6074 | 1.6038    | 1.5969    | 1.5906    | 1.5849    | 1.5795    | 1.5745    | 1.5699    | 1.5656     |
| CLB18_14       | 1.7485 | 1.7238    | 1.7137    | 1.7047    | 1.6966 | 1.6892    | 1.6762    | 1.6650    | 1.6552    | 1.6464    | 1.6385    | 1.6313    | 1.6246     |
| CLB18_15       | 1.9039 | 1.8495    | 1.8265    | 1.8062    | 1.8084 | 1.7732    | 1.7215    | 1.7026    | 1.6874    | 1.6748    | 1.6638    | 1.6545    | 1.6461     |
| CLB18_16       | 2.0181 | 1.9559    | 1.9261    | 1.8971    | 1.8708 | 1.8470    | 1.8067    | 1.7752    | 1.7500    | 1.7291    | 1.7115    | 1.6965    | 1.6836     |
| CLB18_17       | 2.0630 | 1.9908    | 1.9625    | 1.9350    | 1.9084 | 1.8835    | 1.8388    | 1.8027    | 1.7739    | 1.7504    | 1.7313    | 1.7151    | 1.7011     |
| CLB18_18       | 2.0381 | 1.9818    | 1.9540    | 1.9272    | 1.9019 | 1.8782    | 1.8375    | 1.8051    | 1.7792    | 1.7580    | 1.7404    | 1.7254    | 1.7123     |
| Total MUE, Å   | 0.040  | 0.017     | 0.015     | 0.017     | 0.024  | 0.034     | 0.052     | 0.066     | 0.077     | 0.088     | 0.097     | 0.105     | 0.112      |
| Group 1 MUE, Å | 0.035  | 0.013     | 0.010     | 0.010     | 0.013  | 0.020     | 0.032     | 0.042     | 0.052     | 0.060     | 0.068     | 0.075     | 0.081      |
| Group 2 MUE, Å | 0.016  | 0.011     | 0.014     | 0.020     | 0.025  | 0.030     | 0.039     | 0.046     | 0.054     | 0.061     | 0.068     | 0.074     | 0.080      |
| Group 3 MUE, Å | 0.069  | 0.026     | 0.020     | 0.020     | 0.033  | 0.052     | 0.085     | 0.108     | 0.126     | 0.142     | 0.155     | 0.166     | 0.176      |

## Section S6: Choice of the barrier heights subset for comparison with CLB18.

**Table S7** lists the most common approximations used to calculate the geometries of the barrier heights subsets of the two largest computational databases, GMTKN55[@goerigk2017], and MGCDB84[@mardirossian2017]. The BH76 dataset[@zhao2005;@zhao2005b;@zheng2009;@peverati2014a] is the only one that uses a level of theory higher than DFT to obtain the reference structures. For this reason, it is the only viable choice as benchmark dataset for functional approximations.

**Table S7** The level of theory (functional/method and basis set) used to obtain the reference geometries in the BHs subsets of the MGCDB84 and GMTKN55 databases. We reported in bold the non-DFT approaches.

| Dataset         | Origin  | Optimization at         | References                 |
| --------------- | ------- | ----------------------- | -------------------------- |
| BHPERI26$^a$    | MGCDB84 | B3LYP/A’TZVP$^b$        | [@goerigk2010]             |
| CRBH20          | MGCDB84 | B3LYP/A’TZVP$^b$        | [@yu2015]                  |
| DBH24$^c$       | MGCDB84 | **QCISD**/MG3           | [@zhao2007]                |
| HTBH38$^{d,e}$  | MGCDB84 | **QCISD**/MG3           | [@zhao2005b]               |
| NHTBH38$^{d,e}$ | MGCDB84 | **QCISD**/MG3           | [@zhao2005]                |
| PX13$^f$        | MGCDB84 | B3LYP/A’TZVP$^b$        | [@karton2012b]             |
| WCPT27$^g$      | MGCDB84 | B3LYP/A’TZVP$^b$        | [@karton2012]              |
| BH76$^d$        | GMTKN55 | **QCISD**/MG3           | [@zhao2005;@zhao2005b]     |
| BHPERI$^a$      | GMTKN55 | B3LYP/A’TZVP$^b$        | [@goerigk2010;@karton2015] |
| BHDIV10         | GMTKN55 | PBEh-3c                 | [@goerigk2017]             |
| INV24           | GMTKN55 | B3LYP-D3(BJ)/def2-TZVPP | [@goerigk2016]             |
| BHROT27         | GMTKN55 | TPSS-D3(BJ)/def2-TZVP   | [@goerigk2017]             |
| PX13$^f$        | GMTKN55 | B3LYP/A’TZVP$^b$        | [@karton2012b]             |
| WCPT18$^g$      | GMTKN55 | B3LYP/A’TZVP$^b$        | [@karton2012]              |

$^{a,f,g}$These two datasets are the same. The values in GMTKN55 have been updated according to ref. [@karton2015].

$^b$The A'TZVP basis set corresponds to the cc-pVTZ basis set on H, aug-cc-pVTZ basis set for first-row atoms (Li–Ne), and the aug-cc-pV(n+d)Z basis set for second-row atoms (Na–Ar)

$^c$DBH24 is a dataset curated from HTBH38 and NHTBH38

$^d$These datasets are the same. In GMTKN55, the reference values have been recalculated.

$^e$These subsets are taken from the Minnesota 2015B database, and they are used in this work.

## Section S7: ARMSG and $A_{\lambda}$ values for the BH76 database.

In this section, we repot the values used to generate **Figure 4** of the main text (**Table S8**). All values for the average root-mean square gradient (ARMSG) are in Hartrees for the PBE functional and its hybrids. In **Figure S2** we report the $A_{\lambda}$ values for the BH76 dataset, calculated in the same way as for the CLB18 database (see Secion S4 above).

**Table S8** Average root-mean square gradient (ARMSG, Hartrees) for the BH76 database calculated with the PBE functional and its hybrids.  

| **Functional**       | **ARMSG** | **$A_{\lambda}$** % |
|:-------------------- |:---------:|:-------------------:|
| PBE                  | 0.0095    | 0                   |
| PBE+10% HF exchange  | 0.0074    | 10                  |
| PBE+20% HF exchange  | 0.0054    | 20                  |
| PBE0                 | 0.0047    | 25                  |
| PBE+30% HF exchange  | 0.0039    | 30                  |
| PBE+40% HF exchange  | 0.0032    | 40                  |
| PBE+50% HF exchange  | 0.0043    | 50                  |
| PBE+60% HF exchange  | 0.0058    | 60                  |
| PBE+70% HF exchange  | 0.0075    | 70                  |
| PBE+80% HF exchange  | 0.0092    | 80                  |
| PBE+90% HF exchange  | 0.0109    | 90                  |
| PBE+100% HF exchange | 0.0125    | 100                 |

![Figure_3-MR-BH76](Figures_CLB18/CLB18_MR_Diagnostics-BH76.jpg)

**Figure S2** Values of the $A_\lambda$ MR diagnostics for all transition structures in the BH76 database. Problematic values according to ref. [fogueri2013] are reported in bold, while the highest value is reported in red. The transition structures nomenclature (first column) is based on the names used by [@zhao2005] and reported in our ACCDB database.[@morgante2019a]

## Section S8: References.
