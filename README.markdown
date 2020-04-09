Hello!

In this repository you will find an analysis of human chromosomes. This analysis
primarily focuses on chromosomal morphology. The point of this data science
project is to establish whether or not protein composition affects chromosomal
alignment and ending structure. Locus locations and amino acid information
were used to this end.

The following files were used to gather data for this project.
- amino acid abbreviations and molecular weights.pdf
- Amino acid information.csv
- Amino acid information.xlsx
- Amino-Acid-Codes.png
- GCF_000001405.39_GRCh38.p13_assembly_report_fixed.csv
- GCF_000001405.39_GRCh38.p13_assembly_report.csv
- GCF_000001405.39_GRCh38.p13_assembly_report.txt
- Homo_sapiens_AR109.20190905_annotation_report.xml
- ProteinTable51_582967.csv
- ProteinTable51_582967.txt
Where these files were found and their rational for use can be found throughout
the notebooks in this repository.

Using this gathered data and information, a database was accessed through an API
key and project tool as required by the National Center for Biotechnology
Information in the United States. Information about the database accessed can be
found in the BLAST + README.txt file. The notebooks with the prefix Database
show the work for interacting with this database in a variety of ways.
For an attempt as setting up a local interaction see:
- Database-Blast.ipynb
For an attempt to scrape the information see:
- Database-Scrap.ipynb
However, ultimately, I decided to use the API approach. This approach has the
benefit of at the time of request, the information received is the most up to
date information available. Genetic information is updated many times a day, so
this approach seemed most advantageous. This approach can be seen in action in:
- Database-API-21.ipynb
- Database-API-19.ipynb
Also in these notebooks is the decision about which chromosomes to study. There
are some limitations to the amount of data that can be accessed through the
database, so at first, chromosome 21 was selected, as it is the shortest
chromosome. After running through the entire study, the results were very poor
due to not having enough information to study. So, after some additional
analysis of the chromosomal make up, chromosome 19 was selected. Chromosome 19
is unique because it has a high incidence of multiple proteins located at the
same Locus, which allows for better statistical analysis.
From these notebooks the following files were generated:
- all_protein_data_21.csv
- all_protein_data_19.csv.

These files were read into new notebooks in which the analysis of the chromosomal
starts to take shape. These notebooks are:
- EDA-21.ipynb
- EDA-19.ipynb.
In these notebooks many features about the protein sequences and amino acids
are added and visualized. There are some strong correlations between some of the
original features and the developed features. After feature development, the
following files were generated:
- developed features.csv
- developed features 19.csv

These files were then read into new notebooks in which modeling takes place.
These modeling notebooks are as follows:
- Modeling-21.ipynb
- Modeling-19.ipynb
A few different types of models were evaluated. Ultimately, I opted to use a
RandomForest Classifier without scaling and without PCA. This is primarily due
to the sensitivity of the input data. Scaling had no affect on model performance,
and PCA worsened model performance. A grid search was used to find the best
parameters to use for the model. Information about parameter selection in the
grid searches can be found in the notebooks.

Other files associated with this project being completed as a part of the Flatiron
School cirriculumn are:
- CONTRIBUTING.md
- LICENSE.md
- module5_project_rubric.pdf
- smart.gif
- student.ipynb.

If you have additional questions or would like to discuss any of the contents,
feel free to reach out to me either here or through my blog:
eannefawcett.github.io
The post directly connected to this project can be found at:
https://eannefawcett.github.io/2020/03/20/Working-with-NCBI-Databases/
