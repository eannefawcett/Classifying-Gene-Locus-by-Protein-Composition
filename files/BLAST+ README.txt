<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN"
    "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">

<html xmlns="http://www.w3.org/1999/xhtml">
  <head>
    <meta name="generator"
    content="HTML Tidy for Linux/x86 (vers 1st October 2002), see www.w3.org" />

    <title></title>
  </head>

  <body>
<pre>
                         The BLAST Databases
                    Last updated on February 3, 2020

IMPORTANT: As of February 4, 2020, the BLAST databases on the FTP site are version 5 (v5).
At the same time, the databases offered has been changed. This document reflects those changes.
Information on newly enabled features with the v5 databases at 
https://ftp.ncbi.nlm.nih.gov/blast/db/blastdbv5.pdf


This document describes the BLAST databases available on the NCBI FTP site under 
the /blast/db directory. The direct URL is ftp://ftp.ncbi.nlm.nih.gov/blast/db

1. Quick Start
    * Get all numbered files for a database with the same base name:
      Each of these files represents a subset (volume) of that database,
      and all of them are needed to reconstitute the database.
    * After extraction, there is no need to concatenate the resulting files:
      Call the database with the base name, for nr database files, use "-db nr".
    * For easy download, use the update_blastdb.pl script from the blast+ package.
    * Incremental update is not available.

2. General Introduction

BLAST search pages under the Basic BLAST section of the NCBI BLAST home page
(http://blast.ncbi.nlm.nih.gov/) use a standard set of BLAST databases for 
nucleotide, protein, and translated BLAST searches.  These databases are made 
available as compressed archives of pre-formatted form) and can be donwloaed from
the /db directory of the BLAST ftp site (ftp://ftp.ncbi.nlm.nih.gov/blast/db/). 
The FASTA files reside under the /FASTA subdirectory.

The pre-formatted databases offer the following advantages:
    * Pre-formatting removes the need to run makeblastdb;
    * Species-level taxonomy ids are included for each database entry;
    * Databases are broken into smaller-sized volumes and are therefore easier 
      to download;
    * Sequences in FASTA format can be generated from the pre-formatted databases
      by using the blastdbcmd utility;
    * A convenient script (update_blastdb.pl) is available in the blast+ package 
      to download the pre-formatted databases.

Pre-formatted databases must be downloaded using the update_blastdb.pl script or 
via FTP in binary mode. Documentation for this script can be obtained by running 
the script without any arguments; Perl installation is required.

The compressed files downloaded must be inflated with gzip or other decompress 
tools. The BLAST database files can then be extracted out of the resulting tar 
file using the tar utility on Unix/Linux, or WinZip and StuffIt Expander on 
Windows and Macintosh platforms, respectively.  

Large databases are formatted in multiple one-gigabyte volumes, which are named 
using the basename.##.tar.gz convention. All volumes with the same base name are 
required. An alias file is provided to tie individual volumes together so that 
the database can be called using the base name (without the .nal or .pal 
extension). For example, to call the est database, simply use "-db est" option 
in the command line (without the quotes). 

For other genomic BLAST databases, please check the genomes ftp directory at:
    ftp://ftp.ncbi.nlm.nih.gov/genomes/

3. Contents of the /blast/db/ directory

The pre-formatted BLAST databases are archived in this directory. The names of 
these databases and their contents are listed below.

+-----------------------------+------------------------------------------------+
 File Name                    | Content Description                           
+-----------------------------+------------------------------------------------+
README                        | README for this subdirectory (this file)
nr.*tar.gz                    | Non-redundant protein sequences from GenPept, 
                                Swissprot, PIR, PDF, PDB, and NCBI RefSeq
nt.*tar.gz                    | Partially non-redundant nucleotide sequences from 
                                all traditional divisions of GenBank, EMBL, and DDBJ 
                                excluding GSS,STS, PAT, EST, HTG, and WGS.
landmark.tar.gz               | Proteome of 27 model organisms, see 
                                https://blast.ncbi.nlm.nih.gov/smartblast/smartBlast.cgi?CMD=Web&PAGE_TYPE=BlastDocs#searchSets
16S_ribosomal_RNA             | 16S ribosomal RNA (Bacteria and Archaea type strains)
18S_fungal_sequences.tar.gz   | 18S ribosomal RNA sequences (SSU) from Fungi type and reference material (BioProject PRJNA39195) 
28S_fungal_sequences.tar.gz   | 28S ribosomal RNA sequences (LSU) from Fungi type and reference material (BioProject PRJNA51803)
ITS_RefSeq_Fungi.tar.gz       | Internal transcribed spacer region (ITS) from Fungi type and reference material (BioProject PRJNA177353)
ITS_eukaryote_sequences.tar.gz| Internal transcribed spacer region (ITS) for eukaryotic sequences
LSU_eukaryote_rRNA.tar.gz     | Large subunit ribosomal RNA sequences for eukaryotic sequences
LSU_prokaryote_rRNA.tar.gz    | Large subunit ribosomal RNA sequences for prokaryotic sequences
SSU_eukaryote_rRNA.tar.gz     | Small subunit ribosomal RNA sequences for eukaryotic sequences
ref_euk_rep_genomes*tar.gz    | Refseq Representative Eukaryotic genomes (1000+ organisms)
ref_prok_rep_genomes*tar.gz   | Refseq Representative Prokaryotic genomes (5700+ organisms)
ref_viruses_rep_genomes*tar.gz   | Refseq Representative Virus genomes (9000+ organisms)
ref_viroids_rep_genomes*tar.gz   | Refseq Representative Viroid genomes (46 organisms)
refseq_protein.*tar.gz        | NCBI protein reference sequences
refseq_rna.*tar.gz            | NCBI Transcript reference sequences
swissprot.tar.gz              | Swiss-Prot sequence database (last major update)
pataa.*tar.gz                 | Patent protein sequences
patnt.*tar.gz                 | Patent nucleotide sequences. Both patent databases
                                are directly from the USPTO, or from the EPO/JPO 
                                via EMBL/DDBJ
pdbaa.*tar.gz                 | Sequences for the protein structure from the 
                                Protein Data Bank
pdbnt.*tar.gz                 | Sequences for the nucleotide structure from the 
                                Protein Data Bank. They are NOT the protein coding
                                sequences for the corresponding pdbaa entries.
taxdb.tar.gz                  | Additional taxonomy information for the databases 
                                listed here  providing common and scientific names
FASTA/                        | Subdirectory for FASTA formatted sequences
v4/                           | BLAST databases in version 4 (v4).  These files are no
                                longer being updated.
cloud/	                      | Subdirectory of databases for BLAST AMI; see
                                http://1.usa.gov/TJAnEt
+-----------------------------+------------------------------------------------+

4. Contents of the /blast/db/FASTA directory

This directory contains FASTA formatted sequence files. The file names 
and database contents are listed below. These files must be unpacked before
use.  They are provided as a convenience for users needing these sets in
FASTA format.  For use with BLAST, it is preferable to use the BLAST database
on the FTP site. 

+-----------------------+-----------------------------------------------------+
|File Name              | Content Description                                 |
+-----------------------+-----------------------------------------------------+
nr.gz*                  | non-redundant protein sequence database with entries
                           from GenPept, Swissprot, PIR, PDF, PDB, and RefSeq
nt.gz*                  | nucleotide sequence database, with entries from all 
                          traditional divisions of GenBank, EMBL, and DDBJ; 
                          excluding bulk divisions (gss, sts, pat, est, htg) 
                          and wgs entries. Partially non-redundant.
pdbaa.gz*               | protein sequences from pdb protein structures
swissprot.gz*           | swiss-prot database (last major release)
+-----------------------+---------------------------------------------------+
NOTE: 
(1) For screening for vector contamination, use the UniVec database:
    ftp://ftp.ncbi.nlm.nih.gov/pub/UniVec/
 *  marked files have pre-formatted counterparts. 

5. Database updates

The BLAST databases are updated regularly. There is no established incremental
update scheme. We recommend downloading the complete databases regularly to 
keep their content current.

6. Non-redundant defline syntax

The non-redundant databases are nr, nt and pataa. Identical sequences are 
merged into one entry in these databases. To be merged two sequences must
have identical lengths and every residue at every position must be the 
same.  The FASTA deflines for the different entries that belong to one 
record are separated by control-A characters invisible to most 
programs. In the example below both entries Q57293.1 and AAB05030.1
have the same sequence, in every respect:

>Q57293.1 RecName: Full=Fe(3+) ions import ATP-binding protein FbpC ^AAAB05030.1 afuC 
[Actinobacillus pleuropneumoniae] ^AAAB17216.1 afuC [Actinobacillus pleuropneumoniae]
MNNDFLVLKNITKSFGKATVIDNLDLVIKRGTMVTLLGPSGCGKTTVLRLVAGLENPTSGQIFIDGEDVTKSSIQNRDIC
IVFQSYALFPHMSIGDNVGYGLRMQGVSNEERKQRVKEALELVDLAGFADRFVDQISGGQQQRVALARALVLKPKVLILD
EPLSNLDANLRRSMREKIRELQQRLGITSLYVTHDQTEAFAVSDEVIVMNKGTIMQKARQKIFIYDRILYSLRNFMGEST
ICDGNLNQGTVSIGDYRFPLHNAADFSVADGACLVGVRPEAIRLTATGETSQRCQIKSAVYMGNHWEIVANWNGKDVLIN
ANPDQFDPDATKAFIHFTEQGIFLLNKE

Individual sequences are now identifed simply by their accession.version.  

For databases whose entries are not from official NCBI sequence databases, 
such as Trace database, the gnl| convention is used. For custom databases, 
this convention should be followed and the id for each sequence must be 
unique, if one would like to take the advantage of indexed database, 
which enables specific sequence retrieval using blastdbcmd program included 
in the blast executable package.  One should refer to documents 
distributed in the standalone BLAST package for more details. 

7. Formatting a FASTA file into a BLASTable database

FASTA files need to be formatted with makeblastdb before they can be used in local 
blast search. For those from NCBI, the following makeblastdb commands are
recommended:

For nucleotide fasta file:   makeblastdb -in input_db -dbtype nucl -parse_seqids
For protein fasta file:      makeblastdb -in input_db -dbtype prot -parse_seqids

In general, if the database is available as BLAST database, it is better to use the 
preformatted database.

8. Technical Support

Questions and comments on this document and NCBI BLAST related questions 
should be sent to the blast-help group at:
      blast-help@ncbi.nlm.nih.gov

For information about other NCBI resources/services, please send email to 
NCBI User Service at:
      info@ncbi.nlm.nih.gov

<!-- $Header: /src/NCBI/vault.ncbi/distrib/doc/blast/blastdb.html,v 1.13 2015/01/13 22:50:30 camacho Exp $ -->
</pre>
</body>
</html>
