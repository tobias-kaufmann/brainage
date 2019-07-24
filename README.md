# brainage
Code related to Kaufmann et al (2019) 'Common brain disorders are associated with heritable patterns of apparent aging of the brain'

## Preparations
We provide pre-trained xgboost models for estimating brain age from a set of 1118 features. When you compile your features, please make sure the ordering follows the ordering in the file "feature-names.csv". The brainage prediction model takes a matrix as input, where each row reflects data from a given individual and each column reflects one of 1118 features. The relevant features can be extracted from the atlas introduced in Glasser et al (2016) Nature, as well as using freesurfers asegstats2table for subcortical stats.

## Brain age estimation using R statistics
We provide different models for male and female brains, thus feature sets should be split into males and females.
> brainAge_females <- predict(mdl_agepred_female, as.matrix(features_females))

> brainAge_males <- predict(mdl_agepred_male, as.matrix(features_males))
