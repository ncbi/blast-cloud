---
layout: page
category: blastdb
title: "Available BLAST databases in GCP"
order: 6
---

The following BLAST databases are available in Google Cloud Storage (GCS) (data as of December 6, 2018). You can obtain an updated list of BLAST databases by running `update_blastdb.pl --showall pretty --source gcp`.

If working on GCP, you can get these BLASTDBs following these instructions:
* if you have BLAST+ installed, see [Get NCBI BLAST databases](https://www.ncbi.nlm.nih.gov/books/NBK537770/) in the BLAST+ user manual.
* Otherwise, if you have docker, follow [these instructions](https://github.com/ncbi/blast_plus_docs#show-blast-databases-available-for-download-from-the-google-cloud-bucket).

|Name    |Title                |Size (GB)|Last updated|
|--------|---------------------|---------|------------|
GPIPE/10090/106/GCF_000001635.24_top_level|Mus musculus GRCm38.p4 [GCF_000001635.24] chromosomes plus unplaced and unlocalized scaffolds|   1.3150|2016-06-22
GPIPE/9606/109/GCF_000001405.38_top_level|Homo sapiens GRCh38.p12 [GCF_000001405.38] chromosomes plus unplaced and unlocalized scaffolds|   1.5668|2018-03-28
SMARTBLAST/landmark_v5|Landmark database for SmartBLAST|   0.3628|2018-12-03
genomic/Viruses/NCBI_VIV_nucleotide_sequences_v5|NCBI VIV nucleotide sequences|  62.6420|2018-12-04
genomic/Viruses/NCBI_VIV_protein_sequences_v5|NCBI VIV protein sequences| 205.8316|2018-12-04
nr_v5|All non-redundant GenBank CDS translations+PDB+SwissProt+PIR+PRF excluding environmental samples from WGS projects| 205.8268|2018-12-03
nt_v5|Nucleotide collection (nt)|  62.6412|2018-12-03
pdb_v5|PDB protein database|   0.1357|2018-12-04
rRNA_typestrains/prokaryotic_16S_ribosomal_RNA_v5|16S ribosomal RNA (Bacteria and Archaea)|  62.6413|2018-12-04
ref_viroids_rep_genomes_v5|Refseq viroids representative genomes|   0.0001|2018-12-03
ref_viruses_rep_genomes_v5|Refseq viruses representative genomes|   0.0698|2018-12-03
refseq_protein_v5|NCBI Protein Reference Sequences| 205.8493|2018-12-04
refseq_rna_v5|NCBI Transcript Reference Sequences|  62.6473|2018-12-04
swissprot_v5|Non-redundant UniProtKB/SwissProt sequences|   0.3575|2018-12-04
taxdb|Taxonomy BLAST databases|   0.1479|2018-12-03
