# Acute-Kidney-Injury-Research

## MIMIC-III Database Introduction
MIMIC is an openly available dataset developed by the MIT Lab for Computational Physiology, comprising deidentified health data associated with ~60,000 intensive care unit admissions. It includes demographics, vital signs, laboratory tests, medications, and more.

## Mini Batch K-Means
The MiniBatchKmeans is a variant of the Keans algorithm which uses mini-batches to reduce the computation time, while still attempting to optimize the same objective function. Mini-batches are subsets of the input data, randomly sampled in each training iteration. These mini-batches drastically reduce the amount of computation required to converage to a local solution. In contrast to other algorithms that reduce the convergence time of k-means, mini-batch k-means produces results that are generally only slightly worse than the standard algorithm.

The algorithm iterates between two major steps, similar to vanilla k-means. In the first step, b samples are drawn randomly from the dataset, toform a mini-batch. These are then assigned to the nearest centroid. In the second step, the centroids are updated. In contrast to k-means, this is done on a per-sample basis. For each sample in the mini-batch, the assigned centroid is updated by taking the streaming average of the sample and all precious samples assigned to that centroid. This has the effect of decreasing the rate of change for a centroid over time. These steps are performed until convergence or a prederermined nbumber of iterations is reached.

MiniBatchKMeans converges faster than KMeans, but the quality of the results is reduced. In practice, this difference in quality can be quite small.

## Background
Acute Kidney Injury (AKI) is a clinical syndrome characterized by the rapid (hours to days) loss of the kidney excretory function, and it is associated with mortality greater than 50%. However, the best treatment strategy remains uncertain. In particular, evidence suggests that current practices in the administration of nephrotoxic medications are likely induce harm in a proportion of patients. 

## Purpose
Develop a reinforcement learning agent, the Artificial Intelligence (AI) Clinician, which extracted implicit knowledge from an amount of patient data that exceeds by many-fold the life-time experience of human clinicians and learned optimal treatment by analyzing a myriad of treatment decisions.

## Data
The Medical Information Mart for Intensive Care version III (MIMIC-III). We are going to include adult patients fulfilling KDIGO-SCr criteria for Acute Kidney Injury. The variables will include demographics, Elixhauser premorbid status, vital signs, laboratory values, Comorbidities, and Medication.

## Methods
Patients' data could be coded as multidimensional discrete time series with 12-h time steps. The total amount of the nephrotoxic medications administered over each 12-h period defined the medical treatment of interest. The model aims at optimizing patient AKI-status, so a reward was associated to not getting AKI and a penalty to getting AKI. A Markov Decision Process is going to be used to model the patient environment and trajectories.

## Bibliography
Goswami, E. et al. *Evidence-based development of a nephrotoxic medication list to screen for acute kidney injury risk in hospitalized children. AM J HEALTH-SYST PHARM*, Volume 76, Number 22 (2019)

Komorowski, M. et al *The Artificial Intelligence Clinician learns optimal treatment strategies for sepsis in intensive care. Nature Medicine*, VOL 24, 1716-1720 (2018)
