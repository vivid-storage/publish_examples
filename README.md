# Posit Connect & Python

Posit Connect is a publishing platform for the work your team creates in R and Python.
This repository contains examples of Python content you can deploy to Connect, including:

## Interactive apps

- [Streamlit](./streamlit-income-share/README.md)
- [Dash](dash-app/README.md)
- [Flask](flask-sentiment-analysis-app/README.md)
- [Voila](./jupyter-voila/README.md)

### Web APIs

- [Flask](./flask-sentiment-analysis-api/README.md)
- [FastAPI](./fastapi-stock/README.md)

## Documents

- [Jupyter Notebooks](./jupyter-interactive-visualization/README.md)
- [Quarto Documents](./quarto-lightbox/README.md)

## Reticulate

<a href="https://rstudio.github.io/reticulate/">
  <img src="reticulated_python.png" width="200">
</a>

Reticulate allows you to call Python from within an R session.
This enables you to use models built in Python to power Shiny apps, visualize pandas dataframes with ggplot2, and much more.

### Interactive apps

- [Serving Sentiment Analysis with Plumber and spaCy](./reticulatd-sentiment-analysis-api/README.md)
- [Image Classification with PyTorch and Shiny](./reticulated-image-classifier/README.md)

### Documents

- [Visualizing pandas dataframes with ggplot2](./reticulated-rmarkdown-notebook/README.md)

## Getting Started

You can deploy examples from this repo to your Connect server [via git-backed deployment](https://docs.posit.co/connect/user/git-backed/), or clone the repository and deploy examples from their manifests with the [`rsconnect` CLI](https://docs.posit.co/rsconnect-python/).

If you want to explore an example more closely before deploying it:

* Clone this repository
* create a virtual environment in the folder you want to work in
* restore the needed packages into the virtual environment

```bash
$ cd flask-sentiment-analysis-api
$ python -m venv .venv
$ source .venv/bin/activate
$ python -m pip install -U pip setuptools wheel
$ python -m pip install -r requirements.txt
```

For reticulated content, set the `RETICULATE_PYTHON` environment variable to point to your virtual environment, by placing an `.Renviron` file in the folder containing the following:

```
RETICULATE_PYTHON=.venv/bin/python
```

## Publishing basics

Overview: 

* Create and activate a virtual environment 
* Run the examples locally
* Acquire an [API key](https://docs.posit.co/connect/user/api-keys/) 
* Publish the examples with the [rsconnect cli](https://github.com/rstudio/rsconnect-python)
* Save the environment and deployment details for future git-backed publishing

```
rsconnect add \
    --api-key <MY-API-KEY> \
    --server <https://connect.example.org:3939> \
    --name <SERVER-NICKNAME>
```

```
rsconnect deploy api . -n <SERVER-NICKNAME>
```
