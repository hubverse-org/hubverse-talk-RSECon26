# The Hubverse: Streamlining Collaborative Infectious Disease Modeling

**RSECon26**\
9-11 September 2026 \| The Wave, University of Sheffield, UK

## About

This repository contains the Quarto presentation slides and materials for the hubverse talk at RSECon26, the Society of Research Software Engineering conference.

The talk is a 30 minute slot: aim for ~26 minutes of delivery plus questions.

## Abstract

Predictive models have become essential for public health decision-making during infectious disease outbreaks. Yet the rapid proliferation of models, especially during the COVID-19 pandemic, has created a fragmented landscape marked by inconsistent metrics, overlapping forecasts, and limited comparability. Collaborative modeling hubs offer a promising solution by coordinating model submissions, promoting transparency, and facilitating ensemble modeling.

The [hubverse](https://hubverse.io/) is a modular, open-source software ecosystem designed to support the setup and operation of these hubs. Built primarily on open-source software (R, Python, JavaScript, Arrow) and freely available platforms like GitHub, the hubverse introduces data standards for probabilistic model output, utilities for hub administration, validation and ensembling tools, visualization templates, and mechanisms for model evaluation and public-facing communication.

This talk introduces the hubverse through real-world examples, including its recent adoption by the CDC's FluSight influenza forecasting hub, and highlights how this infrastructure is helping standardize infectious disease modeling efforts and support evidence-based decision-making.

## Structure and timing

| Section | Slides | Target |
|-------------------|-----------------------------------|------------------|
| Background | problem, promise, origins, enter the hubverse | 4 min |
| Anatomy of a hub | architecture figure, shared data standard | 2 min |
| Meet the hub | CDC FluSight introduced as the running example | 1 min |
| Configuring FluSight | config overview, `admin.json`, `tasks.json`, task IDs, output types (×3), output type + target config, model metadata | 9 min |
| Beyond the data standard | GitHub Actions, cloud, dashboards, the roles recap, who's using it | 4 min |
| FluSight in operation | file location, validation (×2), `hubData`, ensembles, dashboards | 4 min |
| Wrap-up | lessons, thank you | 1 min |

Two ordering rules the deck follows. FluSight is introduced *before* the config deep dive, so every config file, data row and screenshot from that point on comes from one real hub the audience has already met. And no tool or concept is shown working on FluSight before it has been described — which is why "Beyond the data standard" sits ahead of the FluSight walkthrough, not after it. The roles diagram closes that section as a deliberate bookend to the architecture figure in "Anatomy of a hub": the same system, redrawn by person instead of by data flow.

That totals ~25 min, which fits. If the room runs late, the safest cuts, in order: **`dashboard — model evaluations`** (the forecasts slide already makes the dashboard point) and **`where model output lives`**, which is deliberately a 20-second beat and so is cheap to drop entirely. The "who's using it" notes are longer than you can deliver — pick three or four hubs and the local-hub point, and drop the rest.

Speaker notes across the deck run to roughly 3,650 words, about 26 minutes at a measured pace and 24 at a brisk one. They are prompts rather than a script, and several slides are images you talk over briefly.

## Source files

-   `index.qmd` — the slides
-   `_roles-diagram.qmd` — inline SVG reworking of Figure 2 of the hubverse paper (roles ↔ tools). Revealed in fragments: modelers, then analysts, then stakeholders, then the hubverse panel.
-   `_output-types.qmd` — inline SVG showing how `quantile`, `cdf`, `pmf` and `sample` each represent a predictive distribution
-   `custom.scss`, `title.scss`, `title-slide.html`, `bg_style.lua` — theming
-   `assets/images/paper-fig1-hub-architecture.jpg` — Figure 1 of the hubverse paper, reused under CC BY 4.0 from the [preprint](https://doi.org/10.1101/2025.10.03.25337284)

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
  c("hubData", "hubEnsembles", "hubAdmin"),
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

The `hubData` and `hubEnsembles` chunks read the CDC FluSight hub. Set `params$flusight_path` in the YAML header to a local clone to render offline; otherwise the slides connect to the public S3 mirror.

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

-   **Paper**: Consortium of Infectious Disease Modeling Hubs *et al.* (2026) A software platform for collaborative infectious disease modelling, *Nature Health*. https://doi.org/10.1038/s44360-026-00145-7 ([open-access preprint](https://doi.org/10.1101/2025.10.03.25337284))
-   **Hubverse website**: https://hubverse.io/
-   **Hubverse documentation**: https://docs.hubverse.io/
-   **GitHub organization**: https://github.com/hubverse-org
-   **RSECon26**: https://rsecon26.society-rse.org/

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE.md) file for details.

## Citation

If you use or adapt the code from this repository, you may cite this repository:

``` bibtex
@misc{krystalli2026hubverse_talk,
  author = {Krystalli, Anna},
  title = {The Hubverse: Streamlining Collaborative Infectious Disease Modeling - RSECon26 Talk Materials},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/hubverse-org/hubverse-talk-RSECon26}
}
```

This talk is archived on Zenodo:

```         
Krystalli, A. (2026). The Hubverse: Streamlining Collaborative 
Infectious Disease Modeling for Public Health Impact. Research Software 
Engineering Conference 2026 (RSECon26). Zenodo. 
https://doi.org/10.5281/zenodo.22685754
```

The previous version of this talk, given at US-RSE'25, is archived on Zenodo:

```         
Krystalli, A. (2025). The Hubverse: Streamlining 
Collaborative Infectious Disease Modeling. US-RSE Conference 2025. Zenodo. 
https://doi.org/10.5281/zenodo.17297552
```
