---
layout: page
category: blastdb
title: "Additional NCBI BLAST databases"
order: 3
---

Users may want to install additional BLAST databases from the NCBI using the
`update_blastdb.pl` program. First, [log in to your running
instance via ssh]({{site.baseurl}}{% post_url 2015-06-09-logging-in %}) and run the
commands below :

    cd /blast/blastdb_custom
    update_blastdb.pl --decompress --passive <dbname>


The table below shows some of the available BLAST databases via this method (subject to change without notice). To see all available BLAST databases, please run the command `update_blastdb.pl --showall --passive`.

|Name    |Title                |Type|
|--------|---------------------|----|
|16SMicrobial      |16S ribosomal RNA sequences from bacteria and archaea (RefSeq)|DNA |
|landmark      |The [landmark database](https://blast.ncbi.nlm.nih.gov/smartblast/smartBlast.cgi?CMD=Web&PAGE_TYPE=BlastDocs) includes proteomes from 27 genomes spanning a wide taxonomic range  |Protein|
|human_genomic|Assembled human chromosomes from Reference and Genbank for various individuals, along with their scaffold components.|DNA|
|refseqgene|Genomic sequences for selected genes records from NCBI RefSeq project (NG accessioned), containing additional up- and downstream sequences beyond the transcribed region.|DNA|
|vector|A database contains common vector sequences found in the GenBank/EMBL/DDBJ.|DNA|
|pataa|Protein sequences from patents as supplied by USPTO. Its entries are EXCLUDED from the nr database.|Protein|
|patnt|The patent nucleotide sequence database contains entries from USPTO through GenBank or from EU/Japan Patent Agencies through EMBL/DDBJ. Entries are EXCLUDED from the nt database.|DNA|
|tsa_nr|Protein sequences from annotated on the transcriptome shotgun assembly. Its entries are EXCLUDED from the nr database.|Protein|
|tsa_nt|A database with earlier non-project based Transcriptome Sequence Assembly entries. Entries are EXCLUDED from the nt database.|DNA|
|env_nr|Protein sequences from large environmental sequencing projects, e.g., Sargasso Sea, Acid Mine Drainage. Its entries are EXCLUDED from the nr database.|Protein|
|env_nt|Nucleotide sequences from large environmental sequence projects, such as Sargasso Sea and Acid Mine Drainage. Its entries are EXCLUDED from the nt database.|DNA|
