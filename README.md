# brainage
Code and data related to 

Kaufmann et al. (2019) Common brain disorders are associated with heritable patterns of apparent aging of the brain. Nature Neuroscience. https://doi.org/10.1038/s41593-019-0471-7

## Brain age estimation
We provide pre-trained xgboost models for estimating brain age from a set of 1118 features. When you compile your features, please make sure the ordering follows the ordering in the file "feature-names.csv". The brainage prediction model takes a matrix as input, where each row reflects data from a given individual and each column reflects one of 1118 features. The relevant features can be extracted from the atlas introduced in Glasser et al (2016) Nature, as well as using freesurfer's asegstats2table.

Feature sets should be split into males and females and brain age can be estimated along the lines
> brainAge_females <- predict(mdl_agepred_female, as.matrix(features_females))

> brainAge_males <- predict(mdl_agepred_male, as.matrix(features_males))

! Note that several publicly available samples have been used to train these models. Only data not used in model training should be used when estimating brain age using these models !

## Brain age genetics
The summary statistics for a GWAS on brain age is available for download.
