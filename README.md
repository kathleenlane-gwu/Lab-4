# Lab-4
Repository for lab 4

```
Lab-4/
├── README.md
├── cohort.db
├── data_dictionary.tsv
├── feature_table.tsv
├── lab-4.ipynb
├── environment.yml
├── .gitignore      
└── AI_USAGE.md
```

## Necessary Tools/Downloads for Repository
* Terminal
* Python -- https://www.python.org/downloads/
* VS Code (optional) -- https://code.visualstudio.com/
* Miniforge for Conda/Mamba -- https://github.com/conda-forge/miniforge/releases

## Getting Started
Open the terminal on your computer and copy/paste the code below into the terminal. The cd ~/Desktop command tells the computer to work within your Desktop folder and will clone the repo there. The git clone command will clone the Lab-4 repository using the GitHub URL. Then cd Lab-4 enters the repository, and ls lets you view the files in the repo. You should see the same files from the project structure above.
```
cd ~/Desktop
git clone https://github.com/kathleenlane-gwu/Lab-4.git
cd Lab-4
ls 
```
## Creating the Environment and Running the Notebook
To run lab-4.ipynb, you must first recreate the necessary environment.

In the terminal, copy/paste the following code. mamba env create recreates the necessary environment from the environment.yml file. We then need to access the Lab-4 environment, which has the necessary Python and packages needed to run our analyses. Once these steps are complete, we can open and run the lab-4.ipynb file.
```
mamba env create -f environment.yml
conda activate Lab-4
```

## Explore the Schema

The `cohort.db` database is made up of four tables: `patients`, `samples`, `mutations`, and `genes`.

### `patients` Table 
* The primary key is `patient_id`.
* Each row represents one patient and metadata like their age at diagnosis, sex, etc.
* Columns:
  * patient_id
  * sex
  * age_at_diagnosis
  * stage
  * vital_status
  * followup_months

### `samples` Table 
* The foreign key is `patient_id`, allowing the `samples` table to merge with the `patients` table.
* Each row represents one tissue sample and its associated metadata, such as the aneuploidy score, MSI Mantis score, etc.
* Columns:
  * sample_id
  * patient_id
  * tissue_source_site
  * tmb_nonsynonymous
  * aneuploidy_score
  * msi_mantis_score

### `mutations` Table 
* The foreign key is `sample_id`, allowing the `mutations` table to merge with the `samples` table.
* Each row represents a mutation and its associated metadata, such as the gene, mutation type, etc.
* Columns:
  * mutation_id
  * sample_id
  * gene_symbol
  * variant_classification
  * variant_type
  * protein_change
  * chromosome
  * start_pos
  * end_pos
  * t_ref_count
  * t_alt_count

### `genes` Table 
* The foreign key is `gene_symbol`, allowing the `genes` table to merge with the `mutations` table.
* Each row represents an individual gene and includes the gene ID and the chromosome the gene is located on.
* Columns:
  * gene_symbol
  * entrez_gene_id
  * chromosome
