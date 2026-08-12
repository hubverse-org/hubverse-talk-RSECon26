# The Hubverse: Open-Source Infrastructure for Collaborative Infectious Disease Modeling

**US-RSE'25 Conference Talk**\
October 6-8, 2025 \| Philadelphia, PA

## About

This repository contains the Quarto presentation slides and materials for the hubverse talk at the US Research Software Engineer Association Conference 2025.

## Abstract

Predictive models have become essential for public health decision-making during infectious disease outbreaks. Yet the rapid proliferation of models, especially during the COVID-19 pandemic, has created a fragmented landscape marked by inconsistent metrics, overlapping forecasts, and limited comparability. Collaborative modeling hubs offer a promising solution by coordinating model submissions, promoting transparency, and facilitating ensemble modeling.

The [hubverse](https://hubverse.io/) is a modular, open-source software ecosystem designed to support the setup and operation of these hubs. Built primarily on open-source software (R, Python, JavaScript, Arrow) and freely available platforms like GitHub, the hubverse introduces data standards for probabilistic model output, utilities for hub administration, validation and ensembling tools, visualization templates, and mechanisms for model evaluation and public-facing communication.

This talk introduces the hubverse through real-world examples, including its recent adoption by the CDC's FluSight influenza forecasting hub, and highlights how this infrastructure is helping standardize infectious disease modeling efforts and support evidence-based decision-making.

## Repository Contents

-   **Quarto slides**: Presentation source code
-   **Talk materials**: Supporting files and resources

## Installation

To render the slides locally, you'll need:

1.  **R** (version 4.0 or higher)
2.  **Quarto** (version 1.3 or higher)

### Installing Quarto

Download and install Quarto from https://quarto.org/docs/get-started/

Or if you're using R, you can install it via:

``` r
install.packages("quarto")
```

### Installing R Dependencies

Install required R packages:

``` r
# Install CRAN packages
install.packages(c("dplyr", "knitr"))

# Install all hubverse packages from R-universe
install.packages(
  c("hubData", "hubEnsembles"),
  repos = c("https://hubverse-org.r-universe.dev", "https://cloud.r-project.org")
)
```

Alternatively, you can install the entire hubverse suite:

``` r
# Install the hubverse meta-package (includes all core hubverse packages)
install.packages("hubverse", 
  repos = c("https://hubverse-org.r-universe.dev", "https://cloud.r-project.org")
)
```

## Rendering the Slides

### From the command line:

``` bash
quarto render index.qmd
```

This will generate an HTML presentation that you can open in your browser.

### From RStudio:

1.  Open `index.qmd` in RStudio
2.  Click the "Render" button, or
3.  Press `Ctrl+Shift+K` (Windows/Linux) or `Cmd+Shift+K` (Mac)

### Preview while editing:

``` bash
quarto preview index.qmd
```

This will open a live preview that automatically updates as you edit.

## Viewing the Slides

Once rendered, open `index.html` in your web browser. The presentation uses Quarto's reveal.js format for interactive slide navigation.

## Learn More

-   **Hubverse website**: https://hubverse.io/
-   **Hubverse documentation**: https://docs.hubverse.io/
-   **GitHub organization**: https://github.com/hubverse-org
-   **US-RSE'25 Conference**: https://us-rse.org/usrse25/

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.

## Citation

If you reference this talk or presentation, please cite the slides PDF on Zenodo:

```         
Krystalli, A. (2025). The Hubverse: Streamlining 
Collaborative Infectious Disease Modeling. US-RSE Conference 2025. Zenodo. 
[https://doi.org/10.5281/zenodo.10.5281/zenodo.17297552](https://doi.org/10.5281/zenodo.17297552)
```

If you use or adapt the code from this repository, you may cite this repository:

``` bibtex
@misc{krystalli2025hubverse_talk,
  author = {Krystalli, Anna},
  title = {The Hubverse: Streamlining Collaborative Infectious Disease Modeling - US-RSE'25 Talk Materials},
  year = {2025},
  publisher = {GitHub},
  url = {https://github.com/r-rse/hubverse-talk-usrse25}
}
```


