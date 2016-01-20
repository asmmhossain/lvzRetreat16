---
title       : A phylodynamics pipeline for pathogen sequence data 
subtitle    : 
author      : Mukarram Hossain, Bethany Dearlove, Fei Xiang and Simon Frost
job         : University of Cambridge
framework   : revealjs        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
revealjs:
  theme: beige
  transition: cube
  center: "false"
knit        : slidify::knit2slides
---

## Annual Virology Immunopath Retreat, 2016
<br></br>
**Mukarram Hossain**  
Department of Veterinary Medicine  
University of Cambridge
  
<br></br>

<img src="assets/img/uc-colour.png" width="30%" style="border: 0px">&nbsp;


---

<br><br><br></br></br></br>

## Works in 2015

---

## Pipelign

<img src="assets/img/metal.png" width="65%" style="margin: 10px 10px">&nbsp;

---

<img src="assets/img/igscueal.png" width="60%" style="margin: 10px 10px">&nbsp;&nbsp;
<img src="assets/img/evidence.png" width="62%" style="margin: 10px 10px">&nbsp;

---

<br><br><br></br></br></br>

## A phylodynamics pipeline

---

## Viral phylodynamics

- How epidemiological, immunological, and evolutionary processes interact
- Potentially shape viral phylogenies
- Time-sampled viral phylogenies can reveal:
  - Viral genetic variation
  - Information of transmission dynamics

---

## Viral phylodynamics

- Viral phylodynamics typically involve:
  - Calculating evolutionary rates
  - Dating viral origins
  - Quantifying epidemic spread
  - Assessing efficacy of viral control effect
  - Estimating the demographic structure
  - Estimating effective viral population size

---

## Phylodynamic analysis

- Make use of serially sampled pathogen sequence data
- Time-stamped phylogeny is generated from temporal sequence data
- Phylodynamic studies often use sophisticated software packages such as ``BEAST``
- ``BEAST`` uses Bayesian phylogenetic analysis of molecular sequences
- Uses Markov Chain Monte Carlo (MCMC) to obtain posterior estimates
- Provides a distribution of estimates for parameters of interest

---

## MCMC - example

<br></br><br></br>

[Linear regression problem](http://twiecki.github.io/blog/2013/08/12/bayesian-glms-1/)

[A simple MCMC animation](http://twiecki.github.io/blog/2014/01/02/visualizing-mcmc/)

---

## BEAST - issues

- MCMC is inherently slow to reach stationary distribution
- Computationally expensive for large datasets

<img src="assets/img/cwseqs_skyride_runtime.png" width="100%" style="margin: 10px 10px">&nbsp;


---

## BEAST - issues

- Dataset may contain heterogeneous samples

<img src="assets/img/root-to-tip_denv1vn.png" width="70%" style="margin: 10px 10px">&nbsp;

---

<br></br><br></br><br></br>

## PhyloPipe

---

## A phylodynamics pipeline

- We have developed a pipeline for phylodynamics studies
- Provides high throughput analysis of time sampled pathogen sequence data
- The pipeline makes use of published computational analysis tools
- Provides rough estimation of the following:
    - Time-stamped phylogeny
    - Evolutionary rates
    - TMRCA
    - Population dynamics
    - Demographic structure
    - and others...
- Can be used to guide initial conditions for ``BEAST`` analysis

---

## PhyloPipe - workflow

<img src="assets/img/phylopipe_1.png" width="70%" style="margin: 10px 10px">&nbsp;

--- 

## PhyloPipe - workflow

<img src="assets/img/phylopipe_2.png" width="70%" style="margin: 10px 10px">&nbsp;

---

## PhyloPipe - workflow

<img src="assets/img/phylopipe_3.png" width="70%" style="margin: 10px 10px">&nbsp;

---

## PhyloPipe - workflow

<img src="assets/img/phylopipe_4.png" width="70%" style="margin: 10px 10px">&nbsp;

---

## PhyloPipe - workflow

<img src="assets/img/phylopipe_5.png" width="70%" style="margin: 10px 10px">&nbsp;

---

## PhyloPipe - workflow

<img src="assets/img/phylopipe.png" width="70%" style="margin: 10px 10px">&nbsp;

---

<br><br><br></br></br></br>

## PhyloPipe Example

---

## Dataset - DENV

- 805 DENV-1 WGS from Viet Nam collected between 2003-2008
- Aligned using ``MUSCLE``
- Phylogeny constructed using ``ExaML``
- Root-to-tip distance revealed clusters
- Subdivided into two smaller datasets
    - *G1* contains 140 sequences
    - *G2* contains 665 sequences 

---

## G1 - phylogeny

<img src="assets/img/denv1_vn_g1_tree.png" width="60%" style="margin: 10px 10px">&nbsp;

---

## G1 - evolutionary rates and TMRCA

                      ----------- ------------- ---------------
                      |          |    TMRCA    |   SubstRate  |
                      |----------|-------------|--------------|
                      | RTT      |   2001.364  |    9.8e-04   |
                      | TREBLE   |   1993.886  |    6.1e-04   |
                      | LSD      |   2000.984  |    7.8e-04   |
                      | BEAST    |   2001.314  |    8.6e-04   |
                      ----------- ------------- ---------------

---

## G1 - Demographic model

                            -------------- --------------
                            |             |     lnL     |
                            |-------------|-------------| 
                            | Constant    |   1244.72   |
                            | Exponential |   1254.89   |
                            | Logistic    |   1265.07   |
                            -------------- --------------

---

## G1 - skyride

<div width="450" style="float: left;">
<img src="assets/img/denv.1.s.skyride.png" width="400px" class="centred" style="margin: 10px 10px" />
<div style="font-size:20px">Skyride: Palacios and Minin (2012)</div>
</div>
<div width="450" style="float: right;">
<img src="assets/img/denv.1.g1.skyride.png" width="400px" class="centred" style="margin: 10px 10px" />
<div style="font-size:20px">Skyride: Drummond, Suchard, Xie and Rambaut (2012)</div>
</div>

---

<br><br><br></br></br></br>

## Estimating initial conditions for MCMC

---

## Future works

- Cluster analysis
- Discrete trait analysis

---

## Acknowledgements

- Simon Frost
- Bethany Dearlove
- Fei Xiang

---

<br><br><br></br></br></br>
## Thank you

---

<br><br></br></br>
<img src="assets/img/questions.jpg" width="400px" class="centred" style="margin: 10px 10px" />
