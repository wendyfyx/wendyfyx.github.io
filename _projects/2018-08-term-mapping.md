---
title: Evaluating MedDRA-ICD mapping using UMLS and OHDSI
layout: project
date: 2018-08-10
tagline: Advised by Dr. Cui Tao @ UTHealth School of Biomedical Informatics (2018-2021)
description: We conducted qualitative and quantitative analysis on mapping status between MedDRA and ICD in existing
                terminology libraries, UMLS and OHDSI in the recent years.
---

I was a research intern [^1] at [Dr. Cui Tao](https://sbmi.uth.edu/faculty-and-staff/cui-tao.htm)'s lab UTHealth School of Biomedical Informatics (SBMI). My project was on evaluating the mapping status of two commonly used medical terminologies - the International Classification of Diseases (ICD) and the Medical Dictionary for Regulatory Activities ([MedDRA](https://www.meddra.org/)). 

Heterogeneous data sources in the biomedical and clinial domain are often represented using different terminologies. To faciliate data integration tasks, a reliable mapping between such terminologies is essential.

We investigated MedDRA and ICD mappings in existing terminology services - Unified Medical Language System ([UMLS](https://www.nlm.nih.gov/research/umls/index.html)) and Observational Health Data Sciences and Informatics ([OHDSI](https://ohdsi.org/)). We extracted ICD-MedDRA mappings using UMLS Metathesaurus and the Common Data Model (CDM) from OHDSI's Observational Medical Outcomes Partnership (OMOP). After cross referencing mapped MedDRA terms in both UMLS and OHDSI with the official MedDRA data (version 22.1), we found that 27.31% of MedDRA Preferred Terms (PTs) are mapped with ICD terms.

To suggest potential mapping candidates, we created a ranking algorithm using Apache Lucene using Term Frequency - Inverse Document Frequency (TF-IDF) index to extract top scoring ICD terms for MedDRA terms. Using existing mappings as the gold standard, 74.29% of terms are correctly mapped (amongs the top 5 scoring terms) by our ranking algorithm. Check out our poster [here](/assets/projects/cprit-poster.pdf)!

Currently, we are investigating ICD-MedDRA mappings in UMLS version through out the years from 2009 up to the latest 2020AB version. In addition, we are also conducting qualitative analysis of existing mappings with the help of 4 annotators with clinical background. Stay tuned for more updates!
  

<sup>[^1]: This work was supported by the UTHealth Innovation for Cancer Prevention Research Summer Undergraduate Fellowship.</sup>

