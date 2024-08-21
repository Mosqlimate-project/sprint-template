# Background
The Mosqlimate group evaluated the performance of each model using a set of scores. The logarithmic score, CRPS and the interval score were computed using the 'ScoringRules Python package'. Other metrics were calculated as additional feedback for the teams, without affecting the classification of the models. These metrics included (i) average scores in specific parts of the prediction window, considering epidemic onset (weeks between growth start and the peak) and epidemic peak (3-week window centered on the peak) and (ii) the time lag which maximizes the cross-correlation between forecasts and data.

Seven teams participated in the Dengue 2024 Sprint. They submited dengue predictions using a variety of modeling approaches:
1. D-fense -
2. Dobby Data - LTSH model
3. GeoHealth - Prophet model with PCA and variance threshold and LSTM model with PCA and vaiance threshold Models
4. Global Health Resilience - Temp-SPI Interaction Model
5. PET - BB-M Model
6. Ki-Dengu Peppa - Weekly and yearly (iid) components and Weekly and yearly (rw1) components Models
7. DS_OKSTATE - Info dengue CNN LSTM Ensemble Model

All teams used tools for visualization and data provided by the Mosqlimate platform for comparing arbovirus forecasting experiments:
• climatic, demographic and case open datasets: https://api.mosqlimate.org/datastore/
• Model Registry: https://api.mosqlimate.org/models/
• Visualization tools: https://api.mosqlimate.org/vis/dashboard
• Forecast scoring tools: logarithmic score, CRPS and the interval score

XX teams used climate data, XX used serotype data, and X used additional data on e.g global climate provided by the team itself. 

After finalizing models the submitting forecasts for 2022-2023 and 2023-2024 training seasons 

# Evaluation Methods

## Scores
The logarithmic score, CRP1 and the interval score were computed using the `scoringrules3` Python package. 

The CRPS is computed using the equation below:

$$
CRPS(\mathcal{N}(\mu_i, \sigma^2_i), y_i) = \sigma_i { \omega_i[\Phi(\omega_i) - 1] + 2\phi(\omega_i) - \frac{1}{\sqrt{\pi}}},
$$

where $\Phi(\omega_i)$ and $\phi(\omega_i)$ is the cumulative distribution function (CDF) and the probability density function (PDF) of the standard normal distribution, respectively, evaluated at the normalized prediction error $\omega_i = \cfrac{y_i - \mu_i}{\sigma_i}$. Additionally, $y_i$ represents the cases observed in week $i$, $i$ is the mean forecasted value in week $i$ and $\sigma_i$ is the standard deviation of the forecast on week $i$.

The Log score is computed using the formula below: 

$$
LogS(\mathcal{N}(\mu_i, \sigma^2_i), y_i) = log\left( \cfrac{\phi(\omega_i)}{\sigma_i}\right)
$$

The Interval score is computed using the formula below: 

$$
S^{int}_\alpha(l_i, u_i; y_i) = u_i - l_i + \cfrac{2}{\alpha}(l_i - y_i)I\{y_i < l_i\} + \cfrac{2}{\alpha}(y_i - u_i)I\{y_i > u_i\}
$$

where $I$ is the indicator function, $\alpha$ the significance level of the interval, $u_i$ the upper value of the interval at week $i$ and $l_i$ the lower value. 

Other metrics were calculated as additional feedback for the teams, without affecting the classification of the models, such as (i) average scores in these regions of interest in the prediction window, considering epidemic onset (weeks between growth start and the peak) and epidemic peak (3 week window centered on the peak) and (ii) the time lag, maximizing cross-correlation between forecasts and data
 
## Ranking
For each year and state, the models were assessed according to the six scores listed in the table below.
| Average Score S* | Score (S) used | Final Week|
| -----------------| ---------------|-----------|
|𝑆1                |CRPS            | 52        |
|𝑆2                |CRPS            | 26        |
|𝑆3                |Log Score       | 52        |
|𝑆4                |Log Score       | 26        | 
|S5                |Interval Score  | 52        |
|S6                |Interval Score  | 26        |


The models were ranked according to each score, that is, each model received rank R1, R2, …, R6, for each year and state. Finally, the final ranking RYS of the models were calculated with the following formula, for each year and state:

(...)


# Results

Table below shows the teams and their corresponding model_ids: 


| Team                     | Model id |
| ------------------------ | ------------- |
| D-fense                  | ------------  |
| Dobby Data               | 21            |
| GeoHealth                | 25,26*        |
| Global Health Resilience | 22            |
| BB-M                     | 30            |
| Ki-Dengu Peppa           | 27, 28        |
| DS_OKSTATE               | 29            |
 
 * Since the GeoHealth team provided 8 predictions using model 25 and 2 using model 26, and each model made predictions for diferent states, to have consistency in the table legends and figures below, we refer to model 26 as model 25 in the cases it was used.

## Ranking 

The figures in this section are generated in the `Apply_the_score_to_predictions.ipynb` notebook. 

For AM: 

| AM - 2023 | AM - 2024 |
|--------|--------|
| ![AM - 2023](./figures/ranking_AM_2023.png) | ![AM - 2024](./figures/ranking_AM_2024.png) |

For CE: 

| CE - 2023 | CE - 2024 |
|--------|--------|
| ![CE - 2023](./figures/ranking_CE_2023.png) | ![CE - 2024](./figures/ranking_CE_2024.png) |

For GO: 

| GO - 2023 | GO - 2024 |
|--------|--------|
| ![GO - 2023](./figures/ranking_GO_2023.png) | ![GO - 2024](./figures/ranking_GO_2024.png) |


For PR: 

| PR - 2023 | PR - 2024 |
|--------|--------|
| ![PR - 2023](./figures/ranking_PR_2023.png) | ![PR - 2024](./figures/ranking_PR_2024.png) |


For MG: 

| MG - 2023 | MG - 2024 |
|--------|--------|
| ![MG - 2023](./figures/ranking_MG_2023.png) | ![MG - 2024](./figures/ranking_MG_2024.png) |


The overall rank based on the rank for each mandatory state: 

![Global](./figures/ranking_global.png)

# Conclusion



# Plots of scores 

The Figure below represents the CRPS score by model and state: 

The figures in this section are generated in the `compare_the_scores_figures.ipynb` notebook. 

![CRPS score](./figures/curve_crps.png)

The Figure below presents the Log score by model and state: 

![CRPS score](./figures/curve_log_score.png)

The Figure below presents the interval score by model and state: 

![CRPS score](./figures/curve_interval_score.png)
