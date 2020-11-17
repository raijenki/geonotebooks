# Geonotebooks
This is a general repo for code I wrote on jupyter-notebooks to test some ideas. Most (all) of them are just prototypes and aren't reliable for production use.

## Tests on OpenCV
These are some tests I made using OpenCV in 2015/2016. More files eventually to come when I find them.

* Color quantization: It's just a k-means clustering algorithm, which allows the choice of number of clusters.
* Alignments: Segmentation of magnetic data (based on a paper listed at the jupyer). I lost the final version where the structures were also segmented and converted to shapefile, to-do later. Also, the phase symmetry code isn't mine.

## Predictive Mineralization
This notebook uses a neural network to build a predictive model for iron mineralizations in a particular area from the Bahia state, Brazil.
* **Reqs**: Python 3, Matplotlib, GDAL, Tensorflow2/Keras.
* **Data preparation:** All inputs are RGB images files derived from interpolated meshs. They are resampled for a five-color scale, ranging from very low (000,000,255) to very high (255,0,0).
* **Inputs:** Coordinates from iron mineralizations (10 samples) and non-iron mineralizations (~200 samples) are hardcoded into the notebook. It also uses the following geophysical resampled images from the study area: total gradient, thorium, potassium, uranium, and ratios between them.
* **Outputs:** The predictive model from a multi-layer perceptron, with the last layer being activated by a tanh function. 

* Notes: Results aren't good, which shows either that the neural net can't establish a decent relation with the number of mineralization points provided or that there isn`t much relationship between the maps and the iron mineralization. 
