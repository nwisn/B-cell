

# Statistical supplement

This [Vignette](https://nickwisniewski.com/B-cell/supplement.html) contains all of the statistical analysis for the associated manuscript. We included it in an effort to improve reproducibilty and provide full transparency regarding our statistical methods. After downloading the dataset and installing all the required R packages, the entire vignette can be created by using Knitr on the [Rmarkdown notebook](https://nickwisniewski.com/B-cell/supplement.Rmd).

## Summary

**Background**: 20 heart-failure patients receiving the Heartmate-II mechanical circulatory support device (MCSD) were sampled at 7 timepoints after implantation. Each sample consisted of 67 biomarker measurements – 29 B-cell markers and 38 cytokine markers. Additionally, each patient was associated with 7 categorical variables, such as age, sex, interMACS score, and survival. Due to practical limitations, not all samples were complete; after accounting for missing data, there are a total of 105 datapoints.

**Specific Aims**: We had the following two specific aims: (1) Our primary aim was to identify if and how any of the 67 biomarkers are associated with any of the 7 categorical variables. (2) We also sought to describe any global patterns in the set of biomarkers, such as temporal patterns.

**Methods**: Our methods can be summarized sequentially according to the specific aims:

1. To identify biomarkers with interesting associations, we used a linear mixed effect model to model group or time effects, or group effects that changed in time. We estimated the local false discovery rate of these results, and reported results with q<0.1.

2. To identify specific timepoints where group effects occur, we did a post-hoc analysis using estimated marginal means based on the mixed effect model. We adjusted the statistical significance of all results using the Benjamini-Hochberg method.

3. To identify biomarker clusters, we biclustered the standardized biomarkers and samples. We also clustered biomarkers by temporal similarity, using the marginal means of each standarized biomarker at every timepoint. We computed the optimal number of clusters for both approaches by maximizing average silhouette width.

4. We related biomarker clusters and temporal clusters to each other, and to the list of significant biomarkers found in (2), using Fisher’s exact test.
