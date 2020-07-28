# Introduction

In this repository you will find an analysis of human chromosomes. This analysis
primarily focuses on chromosomal morphology. The point of this data science
project is to establish whether or not protein composition affects chromosomal
alignment and ending structure. Locus locations and amino acid information
were used to this end.

# Background

In biochemistry, there are many phenomena in which we know little about.
Protein formation is one of those. Proteins are the machines that allow our body
to function daily. Our body makes proteins everyday, quite frequently. Information
about how to make proteins is encoded in DNA. When DNA is organized it is called
chromosomes. The only time that DNA organizes into a chromosome is when the cell
in which the DNA is located is preparing to divide. All other times, DNA has
no discernable structure as far as humans can tell. This chromosomal organization
does however provide insight into various types of diseases.

Currently, the only way to track DNA is by radioactively tagging it. This can
affect the organism in which the tag is inserted. This study attempts to classify
proteins by their location on a chromosome, something that is known, by using
the protein's amino acid composition. This amino acid driven classifier could
potentially provide an alternative pathway to protein study and isolation for
the delivery of drugs.

# Business Case

This tracking system could lead to enhanced drug development capabilities,
medicine that is tailored to an individual's own genetic information,
a growth in understanding behind chromosomal based diseases,
and a variety of other health applications.

# Methodology

I used the data science model for processing data: obtain, scrub, explore, model,
and interpret. Ultimately this supervised machine learning model is based on human
chromosome 19 and includes only loci that have more than thirty three occurrences,
as seen below in Table 1.

| Locus    | Occurrences in Chromosome 19 |
|----------|------------------------------|
| KIR3DL2  | 94                           |
| FCAR     | 91                           |
| KIR2DL4  | 91                           |
| NCR1     | 83                           |
| KIR2DS4  | 63                           |
| KIR2DS2  | 61                           |
| CARD8    | 51                           |
| RPS9     | 49                           |
| OSCAR    | 48                           |
| ZNF266   | 46                           |
| ZNF415   | 46                           |
| DMKN     | 45                           |
| KIR3DL3  | 45                           |
| NLRP2    | 40                           |
| VSTM1    | 38                           |
| KIR2DL1  | 36                           |
| CEACAM21 | 35                           |
| MBOAT7   | 35                           |
| TSEN34   | 34                           |
| LILRB1   | 33                           |

Table 1. Loci included in machine learning model to study Chromosome 19.

From this collected data, two studies were run. One where loci classification
was performed, and a second study, called strand, that identified whether or not
the evaluated sequence was a protein.

# Model

The models evaluated include: a decision tree classification model, a bagged
classification model, and a random forest classification model. A pipeline and a
grid search were used to find optimal parameters for the random forest model.

# Results

For the loci study, a test accuracy of 99% was achieved
using the random forest classifier. For the strand study, the best performing
model was the bagged classifier, with a test accuracy of 71%.

<img src="/images/confusion matrix best model.png">

Figure 1. Confusion Matrix for best parameters for loci study.

The best parameters for the loci study were:
- max_depth: 9
- min_samples_split: 0.1
- n_estimators: 151.

<img src="images/confusion matrix for strand best model.png">

Figure 2. Confusion Matrix for best parameters for strand study.

The best parameters for the strand study were:
- max_depth: 20
- min_samples_split: 0.1
- n_estimators: 451.

# Contact

If you have additional questions or would like to discuss any of the contents,
feel free to reach out to me either here or through my [blog][link1].

The post directly connected to this project can be found [here][link2].


[link1]: eannefawcett.github.io
[link2]: https://eannefawcett.github.io/2020/03/20/Working-with-NCBI-Databases/
