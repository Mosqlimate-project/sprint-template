# Registering in the Mosqlimate Platform
The Mosqlimate Platform is responsible for all interactions with the the participants of this sprint, including getting the data and uploading predictions. Therefore, to participate in this sprint, the first step we require from you, as team leader, is to register your team to the Mosqlimate platform (There is not cost associate with this membership). In order to to this, simply go to [api.mosqlimate.org](https://api.mosqlimate.org/), click on the "Login with GitHub" in the top right corner of the page, and follow the instructions. Once you create your Mosqlimate profile, you are set to follow the steps below.

![image](https://github.com/Mosqlimate-project/sprint-template/assets/4005254/91633601-2d13-4b2d-b9a7-7cbf50b1871a)

That's how it looks like if you got this step right.

Now let's move on to setting up the GitHub repository for your submission.


## Cloning the github template for the Infodengue Sprint submission
This github repository should be used as a template for developing your submission for the 2024 Infodengue Sprint. To know about the challenge, please read carefully the call [LINK]. 

If you have a GitHub account, you can create a new public repository clicking the (+) button on the top right of this page. In the following page, you can create the repo under your user as shown below, make sure to use our template as indicated by the red arrow in the figure below. You can name your repository any way you like, we recommend a name easy to remember!

![create repo](/repo_creation.png)

Don't forget to set it as a public repository!

 
## Step-by-step Tutorial of how to prepare your submission
Now that you have your repository setup, be aware that all the code related to your model should be committed to it. You you want to register more than on model, be sure to repeat the step above for each one, so that they are in separate repositories.

We assume here that you are already familiar with GitHub and how to use it. If you're not, please take a look at [this tutorial](https://docs.github.com/en/get-started/start-your-journey/hello-world).

If you already have source code related to the model you will work with, you can copy the code to this repository, or start from scratch based on your previous code.


### Installing the Mosqlient library
The Mosqlimate platform is where all models and predictions are stored, alongside with the data used for the modeling. It provides a [REST API](https://api.mosqlimate.org/api/docs) that is completely language agnostic, for accessing the data as well as registering models. it is fully documented but requires some familiarity with APIs to use.

In addition, we make available a a simplified client library named [Mosqlient library](https://github.com/Mosqlimate-project/mosqlimate-client), available for Python and R, that simplifies the interaction with the platform.

To install the library for Python, from the os terminal type:

```bash
$ pip install -U mosqlient
```

for R:

```R
> library(reticulate)
> py_install("mosqlient")
```

You need to already have the reticulate package installed.


### Starting your work!
We prepared a couple of demo Jupyter notebooks to get you started.  In you local computer make sure you have Python 3.x and Jupyter installed.

If you are an R user, make sure you have the R kernel installed in your Jupyter notebook. you can install it by running the following command **in an R terminal**:

```R
> install.packages("IRkernel")
> IRkernel::installspec()
```

After this you can just open the notebooks indicated below and follow the instructions in them.


Follow the [R demo notebook](/Demo%20Notebooks/R%20demo.ipynb) or [Python demo notebook](/Demo%20Notebooks/Python%20demo.ipynb) to learn of the essential steps you must follow to complete a submission of your work. If you run into dificulties, please reach out fo help at our [sprint community forum]() on our discord server.

If you prefer not to work on a Jupyter notebook,  we have added standalone R scripts alongside the demo notebooks.





