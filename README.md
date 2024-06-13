# Template for Infodengue Sprint submission
This repository should be used as a template for developing your submission. If you already have a GitHub account, You must create a new public repository under your user as shown below:
![create repo](/repo_creation.pngrepo_creation.png)

You can name your repository any way you like.

## Step-by-step Tutorial of how to prepare your submission
Now that you have your repository setup, all modeling work should be committed to it. We assume here that you are already familiar with GitHub and how to use it. If you're not, please take a look at [this tutorial](https://docs.github.com/en/get-started/start-your-journey/hello-world).

If you already have source code related to the model you will work with, you can copy the code to this repository, or start from scratch based on your previous code.

### Registering in the Mosqlimate Platform
The [Mosqlimate Platform](https://mosqlimate.org/) is responsible for all interactions with the the participants of this sprint.

Therefore, to participate in this sprint, we require you, as team lead, to register to the Mosqlimate platform (There is not cost associate with this membership). In order to to this, simply go to [api.mosqlimate.org](https://api.mosqlimate.org/), click on the "Login with GitHub" in the top right corner of the page, and follow the instructions. Once you create your Mosqlimate profile, you are set to follow the steps below.

### Installing the Mosqlient library
The Mosqlimate platform, provides a [REST API](https://api.mosqlimate.org/api/docs) that is completely language agnostic. However, we also make available a a simplified client library named [Mosqlient library](https://github.com/Mosqlimate-project/mosqlimate-client), available for Python and R, that simplifies the interaction with the platform.

To install the library for python, from the console type:

```bash
$ pip install -U git+https://github.com/Mosqlimate-project/mosqlimate-client.git
```

for R you can use the following commands in the R console:

```R
> library(reticulate)
> py_install("git+https://github.com/Mosqlimate-project/mosqlimate-client.git")
```

You need to already have the reticulate package installed.


### Downloading the datasets
The sprint organizers prepared a set of compressed csv files with all the datasets. Follow the [R demo notebook](/Demo%20Notebooks/R%20demo.ipynb) or [Python demo notebook](/Demo%20Notebooks/Python%20demo.ipynb) to learn how to fetch the prepared datasets.

### Running your model
In order to upload you model's predictions to the platform, you need to format it as a JSON object as [described here](https://api.mosqlimate.org/docs/registry/POST/predictions/).


Please refer to the [Demo notebooks] mentioned above for a full example with all the steps.



