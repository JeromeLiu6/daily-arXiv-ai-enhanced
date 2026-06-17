# Daily Research Radar — 2026-06-17

## Today's main topic

**Proteomics, pQTL, multi-omics, and osteoarthritis biology**

Multi-omics and protein genetics can connect epidemiological findings to mechanisms, biomarkers, and therapeutic targets for osteoarthritis and cardiometabolic disease.


- Track pQTL resources, proteomic platforms, and colocalisation evidence.
- Notice work connecting extracellular matrix, inflammation, and cartilage biology.
- Look for multi-omics integration strategies that could be reused in UKB-PPP or OAI.

## Read these first

### Tensor-based second-order causal discovery

- **Authors:** Nathan Ouyang, Kexin Wan, Anna Seigal
- **arXiv:** [2606.18074v1](http://arxiv.org/abs/2606.18074v1)
- **Category:** stat.ML
- **Plain-English summary:** This paper introduces a new algorithm called TSCD that can figure out cause-and-effect relationships between variables by looking at how their covariance matrices change under different conditions (observational data vs. interventional experiments). It works efficiently with hundreds of variables and doesn't require the data to follow a normal distribution.
- **Technical summary:** TSCD takes as input a tensor constructed from covariance matrices of both observational and interventional data. It assumes a linear structural equation model on a DAG with uncorrelated noise, and outputs both the causal DAG and the edge functions. The method leverages second-order statistics (covariance matrices) rather than higher-order moments, which provides statistical and computational efficiency. The authors prove identifiability of causal order and parameters from a logarithmic number of interventions relative to the number of variables. A nonlinear extension is also provided. Experiments demonstrate robustness to noise, competitive performance against existing causal discovery methods, and scalability to hundreds of variables.
- **Why I should read this paper:** Moderately relevant. Causal discovery is a core methodological interest for Weijie (Mendelian randomisation, drug-target MR). However, this paper is purely methodological with synthetic validation, and the requirement for interventional data limits direct application to typical observational epidemiological settings. The tensor/covariance approach is novel but not yet connected to genetics or proteomics.
- **Connection to my work:** Could inform methodological thinking about causal structure learning from multi-omics data (e.g., protein-protein interaction networks, causal ordering of molecular traits). The logarithmic intervention efficiency is theoretically appealing for designing experiments with limited perturbation data (e.g., CRISPR screens in osteoarthritis models).
- **Possible research idea:** Adapt TSCD to work with pQTL data as "natural interventions" (genetic variants as instruments) to infer causal ordering among proteins in osteoarthritis-relevant pathways. Compare with existing MR-based causal network methods (e.g., network MR, bi-directional MR) on UK Biobank or All of Us proteomics data.
- **Priority:** Optional
- **Estimated reading time:** 45 min
- **Scores:** topic 5/10; personal 4/10; novelty 7/10; translational 3/10; idea 5/10; final 5/10

## Other relevant papers

- **[A Quantitative Analysis of Multimodal Biomarkers in Alzheimer's Disease](http://arxiv.org/abs/2606.17867v1)** (cs.CV, 4/10): This paper studies Alzheimer's disease by combining different types of data — brain scans (tau-PET and structural MRI), cognitive tests, and genetic information (APOE4) — from 789 people. The authors analyse how these data types relate to each other, which ones provide unique vs. redundant information, and how they track disease progression. They find that tau protein buildup and brain shrinkage are linked but also have independent effects on cognitive decline.
- **[Proximal Mediation Analysis with Hidden Recanting Witnesses](http://arxiv.org/abs/2606.17600v1)** (stat.ME, 4/10): This paper develops new statistical methods for mediation analysis — figuring out how much of a treatment's effect goes through a specific intermediate variable (mediator) — when there are hidden confounders that affect both the mediator and the outcome. The authors use a technique called "proximal causal inference" to handle these unobserved confounders (called "recanting witnesses") without needing to measure them directly. They propose three identification strategies and a robust estimation method that works well even if some parts of the statistical model are misspecified.
- **[WEQA: Wearable hEalth Question Answering with Query-Adaptive Agentic Reasoning](http://arxiv.org/abs/2606.18147v1)** (cs.AI, 3/10): This paper presents WEQA, a system that uses a large language model (LLM) as a "controller" to answer questions about wearable health data (like step counts, heart rate, sleep). Instead of trying to make one model do everything, WEQA lets the LLM decide which specialized tools and models to call for each question, then checks the answer against external knowledge. The authors built a benchmark from four wearable datasets and showed their system is 24% more accurate than standard LLM approaches, with medical experts rating it higher for usefulness and clinical soundness.
- **[Vision-language models for chest radiography do not always need the image](http://arxiv.org/abs/2606.17710v1)** (cs.CV, 3/10): This paper shows that many vision-language models for chest X-ray analysis appear to perform well not because they actually "see" the image, but because they exploit statistical patterns in the text labels (e.g., knowing which findings commonly co-occur). The authors designed a causal audit that tests whether a model's correct answer depends on the image by occluding relevant/irrelevant regions or swapping in a different patient's scan. They found that a text-only model (no image) performed nearly as well as the best multimodal model, and a huge 119-billion-parameter multimodal model was indistinguishable from a tiny 7-billion text-only baseline. The audit revealed that many models essentially ignore the image. The authors argue that accuracy benchmarks alone are misleading and that grounding audits should be required before clinical deployment.

## Idea generation

1. **Research question:** Can ideas from 'Tensor-based second-order causal discovery' improve multimodal prediction for osteoarthritis or cardiometabolic outcomes?
   - **Possible data source:** UK Biobank, All of Us, OAI, UKB-PPP, public GWAS and pQTL resources
   - **Possible method:** Multimodal deep learning, cross-attention, Coxnet or transformer baselines
   - **Why it could be publishable:** A strong paper is possible if the method is benchmarked against simpler clinical and genetic models.
   - **Difficulty level:** ambitious

2. **Research question:** Which representation-learning features are stable enough for epidemiological interpretation rather than only benchmark performance?
   - **Possible data source:** UK Biobank tabular/EHR data, wearable accelerometry, proteomics
   - **Possible method:** Representation learning, external validation, calibration, subgroup analysis
   - **Why it could be publishable:** It links modern AI methods to reproducibility and clinical utility.
   - **Difficulty level:** medium

3. **Research question:** Can today's proteomics, pqtl, multi-omics, and osteoarthritis biology papers suggest a small, publishable methods note for genetic epidemiology workflows?
   - **Possible data source:** Public GWAS, pQTL, UK Biobank example phenotypes
   - **Possible method:** Benchmarking, sensitivity analysis, transparent reporting checklist
   - **Why it could be publishable:** A focused methods note could be fast to execute and valuable for applied researchers.
   - **Difficulty level:** easy

## Weekly learning trajectory

Yesterday's cycle topic was **Genomic SEM, MR, and causal inference**. Today's focus on **Proteomics, pQTL, multi-omics, and osteoarthritis biology** prepares the next step, **Clinical prediction, survival modelling, and risk-score evaluation**, by connecting methods, datasets, and disease questions across the week.
