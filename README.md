# Lab-4
Repository for lab 4

## Explore the Schema

The `cohort.db` database is made up of four tables: `patients`, `samples`, `mutations`, and `genes`.

### `patients` Table 
* The primary key is patient_id.
* Each row represents one patient and metadata like their age at diagnosis, sex, etc.
* Columns:
  * patient_id
  * sex
  * age_at_diagnosis
  * stage
  * vital_status
  * followup_months

### `samples` Table 
* The foreign key is patient_id, allowing the `samples` table to merge with the `patients` table.
* Each row represents one tissue sample and its associated metadata, such as the aneuploidy score, MSI Mantis score, etc.
* Columns:
  * sample_id
  * patient_id
  * tissue_source_site
  * tmb_nonsynonymous
  * aneuploidy_score
  * msi_mantis_score

### `mutations` Table 
* The foreign key is sample_id, allowing the `mutations` table to merge with the `samples` table.
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
* The foreign key is chromosome, allowing the `genes` table to merge with the `mutations` table.
* Each row represents an individual gene and includes the gene ID and the chromosome the gene is located on.
* Columns:
  * gene_symbol
  * entrez_gene_id
  * chromosome
