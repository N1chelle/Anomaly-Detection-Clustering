# Anomaly-Detection through Clustering Algorithms


## The Mission

Acme Corporation is a worldwide supplier of technological equipment. The factory is facing significant problems with their manufacturing line, the machines are constantly facing failures due to a lack of maintenance and the production is stopped every time an unexpected failure is presented. As a result, Acme is losing millions of U.S. Dollars and important clients like Wile E. Coyote are experiencing delays in deliveries.

The company has collected audio samples of equipment working on normal and anomalous conditions. *Their objective is to develop a machine learning model able to monitor the operations and identify anomalies in the sound pattern.*

The implementation of this model can allow Acme to operate the manufacturing equipment at full capacity and detect signs of failure before the damage is so critical that the production line has to be stopped.

The mission is to build a machine learning model for Acme, so they can continue their manufacturing activities and help the Coyote to catch the roadrunner.


## Dataset Source

The dataset was downloaded from the following link:

[MIMII Dataset](https://zenodo.org/record/3384388#.YbNVkb3MJPZ)

## Previous Developments on the Project

Previously I had worked in a collabration on the same project to develop a machine learning model by using **classification algothrims**.
The model was built to predict the class of the audio i.e., whether it was a normal sound or anomalous(abnormal) sound. This could be done using classification since the data was already labeled as normal and abnormal for different equipments.
The link to the repository is : [brAIn](https://github.com/N1chelle/brAIn)

## Current Development

Now I have been working on the same mission but with a different approach. I have tried various machine learning algorithms based on **clustering techniques** to see if the model is able to identify **normal**, **anomalous** and **transitory**(sound from machine that is not running effectively but is not yet deffective) sounds by grouping it into a clusters. For this purpose the data used is unlabelled as we want the model to form its own clusters.

## Details

I have used the csv file formed in the previous project which contained audio features of *all the equipments*(fan, pump, slider and valve) for **model id_00**. The data relates to audios with **-6 dB** sound.

#### Audio Features Extracted:
* chroma_stft	
* spectral_centroid	
* spectral_bandwidth	
* spectral_rolloff	
* rms	
* zero_crossing_rate	

#### Clustering Algorithms used:
* KMeans
* DBSCAN
* Birch
* Agglomerative Clustering

## Observations

Normally clustering techniques are used for unlabelled data. But since the data received was labelled, I have used it as a reference to see if the model was forming the correct clusters or not.

### KMeans

At first I used the algorithm to form 2 clusters and then compared it with the original dataset:

Original: 

![](original_class.png)  

KMeans:

![](KMeans_cluster.png)

Also, I plotted a graph to view the distribution of the audio features:

Original:
![](original_plot.png)

![](Kmeans_plot.png)

Then I used the algorithm to form 3 clusters with the idea that it would group the sounds into normal, abnormal and transitory.

Dataset:

![](KMeans_cluster3.png)

Graph:

![](KMeans_plot3.png)


From the dataset and the plots I observed that the abnormal sound feature points were overlapping normal sound points.
I did not notice a clear distinction between normal and abnormal in the original graph itself which made it difficult for the model to identify similar data points. As a result, the clusters that were formed were not fully conclusive.




