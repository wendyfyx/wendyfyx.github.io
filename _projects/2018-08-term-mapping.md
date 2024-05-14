---
title: Evaluating MedDRA-ICD mapping in UMLS and OHDSI
layout: post
date: 2018-08-10
tagline: Research project advised by Dr. Cui Tao @UTHealth SBMI (2018-2021)
description: Qualitative and quantitative analysis on mapping status between MedDRA and ICD using 
            exsiting terminology services UMLS and OHDSI
---

I was a research intern [^1] at [Dr. Cui Tao](https://sbmi.uth.edu/faculty-and-staff/cui-tao.htm)'s lab UTHealth School of Biomedical Informatics (SBMI). My project was on evaluating the mapping status of two commonly used medical terminologies - the International Classification of Diseases (ICD) and the Medical Dictionary for Regulatory Activities ([MedDRA](https://www.meddra.org/)). 

<hr class="solid">

Heterogeneous data sources in the biomedical and clinial domain are often represented using different terminologies. To faciliate data integration tasks, a reliable mapping between such terminologies is essential.We investigated MedDRA and ICD mappings in existing terminology services - Unified Medical Language System ([UMLS](https://www.nlm.nih.gov/research/umls/index.html)) and Observational Health Data Sciences and Informatics ([OHDSI](https://ohdsi.org/)). We extracted ICD-MedDRA mappings using UMLS Metathesaurus and the Common Data Model (CDM) from OHDSI's Observational Medical Outcomes Partnership (OMOP). After cross referencing mapped MedDRA terms in both UMLS and OHDSI with the official MedDRA data (version 22.1), we found that 27.31% of MedDRA Preferred Terms (PTs) are mapped with ICD terms.

To suggest potential mapping candidates, we created a ranking algorithm using Apache Lucene using Term Frequency - Inverse Document Frequency (TF-IDF) index to extract top scoring ICD terms for MedDRA terms. Using existing mappings as the gold standard, 74.29% of terms are correctly mapped (amongs the top 5 scoring terms) by our ranking algorithm. Check out our poster below!


Over the following 2 years, We further investigated ICD-MedDRA mappings in UMLS version through out the years from 2009 up to 2020. In addition, we also conducted qualitative analysis of existing mappings with the help of annotators with clinical background. My collaborator Xinyuan Zhang presented our recent findings [*MedDRA-ICD Mapping Evaluation Based on UMLS and OHDSI*](https://www.youtube.com/watch?v=o7syNWwaSoU) at the 10th International Workshop on Vaccine and Drug Ontology Studies (VDOS-2021) in September!
  

<!-- <object data="/files/projects/cprit-poster.pdf" type="application/pdf" width="900px" height="500px">
    <embed src="/files/projects/cprit-poster.pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="/files/projects/cprit-poster.pdf">Download PDF</a>.</p>
    </embed>
</object> -->

<figure style="margin-top:1em; margin-bottom:1em; display: flex; flex-direction: column; align-items: center;">
    <img src="/files/projects/cprit-poster.png" alt="CPRIT-poster" style="width:100%;"/>
    <!-- <figcaption style="font-style: italic;">Poster presentation</figcaption> -->
</figure>


[^1]: This work was supported by the UTHealth Innovation for Cancer Prevention Research Summer Undergraduate Fellowship.

