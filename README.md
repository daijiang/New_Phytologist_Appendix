# New_Phytologist_Appendix
R scripts for Dune Meadows data set analyses

This R code cleans data, builds a phylogeny, and then conducts all analyses for the Dune Meadows dataset. The code comes with no guarantees and was tested in R v.3.2.3. Questions about the code can be send to Daijiang Li (daijianglee@gmail.com).

Please cite the paper if you use the code elsewhere.

`data_clean/` includes functional traits data; other data can be loaded from R package `vegan`.

`Rcode/`:

- `0_pkg_func.R`: packages and functions used.
- `1-data.R`: read and clean data.
- `2-forward_selection.R`: use forward selection to select functional traits to be included in the final model. So we can test how much of phylogenetic variation can be explained by measured functional traits. It first selected traits as fixed terms based on AIC. Then selected traits as both fixed terms and random terms (i.e. whenever select a trait as random term, its fixed term was included also). These two steps do not have phylogenetic random terms. After then, phylogenetic random terms were added. Finally, addition traits were tested to check whether they can reduce the residual phylogenetic patterns more.
- `3-phylosig.R`: to test phylogenetic signal of functional traits. And to test whether species trait-abundance relationships varied from site to site.
- `analyses.R`: detect phylogenetic patterns (attraction/repulsion); calculate % of phylogenetic variation explained by traits (refer to 2-forward_selection.R); and all other analyses used in the paper.

## issues

1. The original files in the journal website miss some part of the code (mostly creating data objects), which has been added at the end of the `1-data.R` file.
