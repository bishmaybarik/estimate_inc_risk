# **Income Risk Estimation Across Caste Groups in India**

This repository focuses on the estimation of income risks across heterogeneous caste groups in India, examining disparities and variations within and across these groups. The analysis aims to provide insights into how income risks differ by caste, contributing to the broader understanding of economic inequalities and their implications for policy design.  

Detailed explanations of the methodology, dataset, and results will be added soon.  

---

## **Contents of the Repository**

### 1. **Overview of the Repository**
- Detailed descriptions of all files, scripts, and results in the root directory.  
- A roadmap for navigating the repository and understanding its structure.  

### 2. **Classification of Caste Groups**
- Explanation of the classification methodology for caste groups in India.  
- Data sources and criteria used to create these classifications.  

### 3. **Income Structure and Risk Estimation**
- Overview of the income structure across caste groups.  
- Methodology for estimating income risks using an AR(1) process.  
- Steps for implementing the model, including code snippets and example datasets.  

### 4. **Appendix**
- Additional information and supplementary materials, such as intermediate results, technical notes, and potential extensions of the study.  

### 5. **References**
- Academic papers, datasets, and other resources that informed this project.  

---

## 1. **Overview of the Repository**
Here's a map about what the repository directories look like:
```
estimate_inc_risk/
│
├── 01_data/                             # Data storage (not present in the repository; download data manually)
│
├── 02_code/                             # Code for analysis
│   ├── tot_pop.ipynb                    # Jupyter notebook for total population analysis
│   ├── caste_groups.ipynb               # Jupyter notebook for caste group analysis
│   ├── graphs.ipynb                     # Jupyter notebook for generating graphs
│
├── 03_results/                          # Results and outputs
│   ├── caste_group_results.txt          # Results from caste group analysis
│   ├── population_results.txt           # Results from population analysis
│   ├── caste_results.png                # Visualization of caste group results
│
├── 04_appendix/                         # Additional notes and appendices
│   ├── appendix_notes.pdf               # Handwritten notes (typed version to be uploaded soon)
│
├── .gitignore                           # Files and directories to ignore in version control
├── LICENSE                              # License information for the project
├── README.md                            # Project overview and documentation
```
---

## 2. **Classification of Caste Groups**

The detailed wriiten code is available in `caste_groups.ipynb` in `02_code/` where I have broken down the caste groups systematically. 

### 1. SC (Social Group 1):

- Includes individuals belonging to the "SC" (Scheduled Caste) category.
- Assumes that SCs are only Hindus since there is no explicit condition to include SCs from other religions.

### ST (Social Group 2):

- Includes individuals belonging to the "ST" (Scheduled Tribe) category.
- Unlike SCs, STs are not restricted by religion. Therefore, STs from any religion (Hindu, Muslim, Christian, etc.) are included in this group.

### OBC (Social Group 3):

- Includes individuals belonging to the "OBC" (Other Backward Class) category.
- There is no restriction based on religion, meaning OBCs from all religions are included.

### Muslims (Social Group 4):

- Includes all individuals who identify as Muslim in the religion variable.
- This group encompasses Muslims from all caste categories, including SC, ST, OBC, and others.

### Other Hindus (Social Group 5):

- Includes Hindus belonging to the "Intermediate Caste" and "Upper Caste" categories.
- This group excludes SCs, STs, and OBCs among Hindus, as these categories are assigned to their respective groups (1, 2, and 3).

### Other Religions (Social Group 6):

- Includes individuals whose social group (`interest_soc_group`) is still missing `NaN` after the above classifications.
- Likely includes individuals from minority religions such as Christians, Sikhs, Jains, or those who do not fall into any of the above categories.

---

## 3. **Income Structure and Risk Estimation**

The income structure and the risk estimation strategy has been taken from the methodologies proposed by (Blundell, 2014), (Blundell et. al., 2005) & Chris Tonetti's Lecture Notes from Stanford. 



## References

Blundell, Richard, Hamish Low, and Ian Preston. "Income risk and consumption inequality: a simulation study. 2004a." Ref Type: Report.

Blundell, Richard. "Income dynamics and life‐cycle inequality: mechanisms and controversies." The Economic Journal 124, no. 576 (2014): 28
