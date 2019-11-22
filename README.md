D(St)reams of Anomalies
==============================

The real world does not slow down for bad data

Author: Ruturaj Kiran Vaidya

Project Organization
------------

    ├── LICENSE
    ├── README.md          <- The top-level README for developers using this project.
    ├── data
    │   ├── external       <- Data from third party sources.
    │   ├── interim        <- Intermediate data that has been transformed.
    │   ├── processed      <- The final, canonical data sets for modeling.
    │   └── raw            <- The original, immutable data dump.
    │
    ├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
    │                         the creator's initials, and a short `-` delimited description, e.g.
    │                         `1.0-jqp-initial-data-exploration`.
    │
    ├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
    │   └── figures        <- Generated graphics and figures to be used in reporting

--------

<p><small>Project based on the <a target="_blank" href="https://drivendata.github.io/cookiecutter-data-science/">cookiecutter data science project template</a>. #cookiecutterdatascience</small></p>

### Before Getting Stated

If you are only interested in looking at the notebook then go to (There are notebook rendering problems in github ecosystem):

https://nbviewer.jupyter.org/github/Ruturaj4/d_st_reams_of_anomalies/blob/master/notebooks/1.0-rkv-d-st-reams-of-anomalies.ipynb

All the graphs are plotted using `matplotlib`.

### Aim

<ul>
<li>Load the dataset and do feature engineering</li>
<li>Determine anomalies using one or more anomaly detection model</li>
</ul>

### Dataset

For this project, I used nyc taxi data.

Data Link: https://github.com/numenta/NAB/blob/master/data/realKnownCause/nyc_taxi.csv

Five anomalies occur during the NYC marathon, Thanksgiving, Christmas, New Years day, and a snow storm.

### Discussion

I loaded the taxi dataset and did some feature engineering to analyse and to select data for algorithm training. First, I used z-score technique of oulier detection. Note that there are different techniques available, I chose the z-score technique. Second, I used `isolation forest` and `One class SVM` models for anamoly detection. I used `value` and `dayofweek` features to train the models. Following are some generated graphs after the analysis.

![alt text](/reports/figures/number_of_nyc_taxi_passengers_half.png)
![alt text](/reports/figures/number_of_nyc_taxi_passengers_month.png)
![alt text](/reports/figures/z_score_half.png)
![alt text](/reports/figures/z_score_month.png)
![alt text](/reports/figures/isoforest_half.png)
![alt text](/reports/figures/isoforest_month.png)
![alt text](/reports/figures/oneclasssvm_half.png)
![alt text](/reports/figures/oneclasssvm_month.png)

### Final Comments

In conclusion, I believe that the `isolation forest` worked well in this case, than the `One class SVM`. I observed that there are kind of unsual anomalies in the case of `One class SVM`. I think that it is very hard to select the "nu" parameter, during the training of the `One class SVM` algorithm. Lastly, I observed that the `z-value` algorithm worked really well (surprisingly). This also depends a lot on the datasets. It also finds almost correct anomalies, which are mentioned in the dataset documentation.

### References

<ul>
<li>Time series of price anomaly detection: https://towardsdatascience.com/time-series-of-price-anomaly-detection-13586cd5ff46</li>
<li>Unsupervised Anomaly Detection: https://www.kaggle.com/victorambonati/unsupervised-anomaly-detection</li>
</ul>

### License

<b>MIT</b>
