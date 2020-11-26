# Bla


## Getting started

The "Amazing Python Data Workflow with Poetry, Pandas, and Jupyter"<sup>[1]</sup> is used for this project.

### Prerequisites

In order to take part in the course, please ensure that you have a Python version greater or equal to `3.6.1`, a working installation of [Poetry][1] and [git][2] installed.


### Setup

1. Clone this repository (or use SSH) and move it into the repo root.

	git clone https://github.com/Francosinus/A3-hcds-hcc.git
	cd A3-hcds

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

## Troubleshooting

* Problems when installing `poetry`? When installing `poetry` something goes wrong. It's not automatically in your path, so if you run `poetry --version` nothing happens. If you use `zsh` or `oh-my-zsh` then you need to add the following line to your `.zshrc` file `export PATH="$HOME/.poetry/bin:$PATH`.

* Trouble with previewing notebooks directly in GitHub? --\> https://nbviewer.jupyter.org/

---- 
`[1]` https://mungingdata.com/python/jupyter-workflow-poetry-pandas/, accessed: 2020-10-28

[1]:	https://python-poetry.org/docs/
[2]:	https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
