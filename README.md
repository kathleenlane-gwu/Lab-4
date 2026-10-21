# Lab-4
Repository for lab 4

## Explore the Schema

`patients` Table Columns
* patient_id
* sex
* age_at_diagnosis
* stage
* vital_status
* followup_months

`samples` Table Columns
* sample_id
* patient_id
* tissue_source_site
* tmb_nonsynonymous
* aneuploidy_score
* msi_mantis_score

`genes` Table Columns
* gene_symbol
* entrez_gene_id
* chromosome

`mutations` Table Columns
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
