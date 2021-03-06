
<p align="center">

<img src="https://github.com/singha53/omicsBioAnalytics/blob/master/inst/extdata/figures/logo.png" width={400} alt="Omics BioAnalytics" />

</p>

**Omics BioAnalytics** is a Shiny app that perform common bioinformatics
analyses such as descriptive analyses of demographics variables,
exploratory data analysis, differential expression analysis and
biomarker discovery analysis. The can either use the provided sample
data to run through the various analyses of the app or upload their own
data (demographics variables, omics data).

## Installing

  - assuming R is installed.

<!-- end list -->

``` r
install.packages("devtools")
devtools::install_github("singha53/omicsBioAnalytics")
```

## Get started

  - Step 1) add inst/app/makeEnvVars.R with the following contents
    (.Renvion worked locally but not on shinyapps.io):

<!-- end list -->

``` r
saveRDS("your-s3-bucket-name", "S3BUCKET.rds")
saveRDS("your-aws-access-key", "AWS_ACCESS_KEY_ID.rds")
saveRDS("your-aws-secret-access-key", "AWS_SECRET_ACCESS_KEY.rds")
saveRDS("your-aws-region", "AWS_DEFAULT_REGION.rds")
saveRDS("your-dynamodb-table-name", "TABLE_NAME.rds")
```

> The above script is sourced in global.R and the env are set locally
> and on shinyapps.io at runtime.

  - Step 2) run the Shiny webapp

<!-- end list -->

``` r
library(omicsBioAnalytics);
omicsBioAnalytics::startApp()
```

## Programming/Scripting Languages

### Web-app

  - RShiny (v3.6.1)
  - RStudio (v1.2.5019)

### Multi-model app

  - [Omics BioAnalytics Alexa
    Skill](https://github.com/singha53/omics-bioanalytics-alexa-skill)

## Sample datasets used for this app

### COVID-19 case study

#### How to use?

``` r
library(omicsBioAnalytics);
data(covid19)
```

#### How to generate?

[steps to reproduce the COVID-19
data](https://github.com/singha53/omicsBioAnalytics/blob/master/inst/extdata/covid19/covid19.md)

### Heart Failure case study

#### How to use?

``` r
library(omicsBioAnalytics);
data(heartFailure)
```

#### How to generate?

[steps to reproduce the heart failure
data](https://github.com/singha53/omicsBioAnalytics/blob/master/inst/extdata/heartFailure/heartFailure.md)

### Pathway datasets

#### How to use?

``` r
library(omicsBioAnalytics);
data(pathwayDB)
```

#### How to generate?

[steps to reproduce the pathway
database](https://github.com/singha53/omicsBioAnalytics/blob/master/inst/extdata/pathwayDB/pathways.md)

## Features

  - analyze multiple omics data obtained on the same set of subjects
    (samples/observations)
  - interactive visualizations (heatmaps, networks, statistical graphs)
  - RShiny app as an R-package
  - voice-enabled analytics using an Alexa Skill

## Room for improvements

  - use of Shiny modules to improve server-side code
  - use of R6Class to improve code

## Contributing

If you???d like to contribute, please fork the repository and use a
feature branch. Pull requests are warmly welcome.

Note: if you build your own omicsBioAnalytics R-package and host it on
your own github, then prior to deploying the app to shinyapps.io, make
sure to restart your R session, then install the package from Github.

## Links

  - Repository: <https://github.com/singha53/omicsBioAnalytics/>

## References

  - [Shiny dashboard best
    practices](https://www.inwt-statistics.com/read-blog/best-practice-development-of-robust-shiny-dashboards-as-r-packages.html)
  - [Cloudyr dynamodb orphaned
    R-library](https://github.com/cloudyr/aws.dynamodb)

## Copyright and license

Copyright 2020 AMRITPAL SINGH Inc.

The code in this project is licensed under MIT license.
