# Wikimedia ORES

## Data acquisition

Two data sources are used: (1) Wikipedia articles of politicians and (2) world population data.

**Wikipedia articles -**
The Wikipedia articles can be found on [Figshare](https://figshare.com/articles/Untitled_Item/5513449). It contains politiciaans by country from the English-language wikipedia. The already downloaded dataset can be found in [Wiki articles](https://github.com/Francosinus/A3-hcds-hcc/tree/main/data_raw)

**Population data -**
This dataset is drawn from the [world population datasheet](https://www.prb.org/international/indicator/population/table/) published by the Population Reference Bureau (downloaded 2020-11-13 10:14 AM). The already downloaded dataset can be found in [World population data](https://github.com/Francosinus/A3-hcds-hcc/tree/main/data_raw)

### Getting article quality predictions with ORES

The predicted quality scores for each article in the Wikipedia dataset are accessed via a machine learning system called [**ORES**](https://www.mediawiki.org/wiki/ORES) ("Objective Revision Evaluation Service"). ORES estimates the quality of an article (at a particular point in time), and assigns a series of probabilities that the article is in one of the six quality categories. The options are, from best to worst:

| ID | Quality Category |  Explanation |
|----|------------------|----------|
| 1 | FA    | Featured article |
| 2 | GA    | Good article |
| 3 | B     | B-class article |
| 4 | C     | C-class article |
| 5 | Start | Start-class article |
| 6 | Stub  | Stub-class article |

### ORES REST API endpoint

The [ORES REST API](https://ores.wikimedia.org/v3/#!/scoring/get_v3_scores_context_revid_model) is used to access ORES scores. It expects the following parameters:


## Getting started

The "Amazing Python Data Workflow with Poetry, Pandas, and Jupyter"<sup>[1]</sup> is used for this project.

### Prerequisites

In order to take part in the course, please ensure that you have a Python version greater or equal to `3.6.1`, a working installation of [Poetry][1] and [git][2] installed.


### Setup

1. Clone this repository (or use SSH) and move it into the repo root.

	git clone https://github.com/Francosinus/A3-hcds-hcc.git
	cd A3-hcds-hcc

1. Install the dependencies in the repo root.

	poetry install

1. Create a subshell within the virtual environment by running:

	poetry shell

1. Open the project with Jupyter in your browser.

	jupyter notebook
	
Dependencies:  
``` python
python = "^3.6.1"  
pandas = "^1.1.3"  
jupyter = "^1.0.0"  
ipykernel = "^5.3.4"  
requests = "^2.24.0"  
matplotlib = "^3.3.2"  
seaborn = "^0.11.0"  
altair = "^4.1.0"  
bs4 = "^0.0.1"  
xlrd = "^1.2.0"
``` 

## Analysis

The analysis consists of calculating the proportion (as a percentage) of articles-per-population and high-quality articles for **each country** and for **each region**. By `"high quality"` arcticle an article that ORES predicted as `FA` (featured article) or `GA` (good article) is meant.

**Examples:**

* if a country has a population of `10,000` people, and you found `10` articles about politicians from that country, then the percentage of `articles-per-population` would be `0.1%`.
* if a country has `10` articles about politicians, and `2` of them are `FA` or `GA` class articles, then the percentage of `high-quality-articles` would be `20%`.


## Troubleshooting

* Problems when installing `poetry`? When installing `poetry` something goes wrong. It's not automatically in your path, so if you run `poetry --version` nothing happens. If you use `zsh` or `oh-my-zsh` then you need to add the following line to your `.zshrc` file `export PATH="$HOME/.poetry/bin:$PATH`.

* Trouble with previewing notebooks directly in GitHub? --\> https://nbviewer.jupyter.org/

---- 
`[1]` https://mungingdata.com/python/jupyter-workflow-poetry-pandas/, accessed: 2020-10-28

[1]:	https://python-poetry.org/docs/
[2]:	https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
