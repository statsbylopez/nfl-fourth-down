# nfl-fourth-down

This repository contains RMarkdown code for a manuscript written by Michael Lopez and Derrick Yam pertaining to fourth down decision making in the National Football League. You can view a preprint of our manuscript [here]()

There are three .rmd files provided in the `Code/` section.

*Data Wrangling.rmd*: This file provides all of our data wrangling code. This file takes two data sources (Armchair Analysis, Football Outsiders) and cleans them for matching and analysis. This file also links each play to two win probability estimates, generated using a random forest algorithm (`Models/winprob_lock_rf.Rdata`) and a generalized additive model (`Models/winprob_horowitz_gam.RData`). We are not at liberty to share the Armchair Analysis data, but it can be downloaded for a nominal fee at [http://armchairanalysis.com/](http://armchairanalysis.com/). 

*Matching.rmd*: This file matches teams that did not go for it (control plays) to teams that did (treatment plays) using a nearest neighbor matching algorithm. Matching success is also assessed. 

*Results.rmd*: This file compares the matched cohort of plays to assess the benefit that teams have missed out on by not going for it on fourth down. Results are presented both league-wise, and team-level estimates (wins added) are generated using the bootstrap. 

Given a few dependencies in the R packages (in particular with dplyr::select(), these files work best when run consecutively (in order: Data Wrangling, Matching, Results). 

