# Data Analytics/Big Data Certificate — Python and R  
 
 
### by Marcelo Jimenez, Petroleum Engineering Graduate from The University of Texas at Austin  

___

Right after graduation and over the summer of 2021, I worked towards this Data Analytics certificate as I wanted to broaden my skill set. Coding and Data Analysis always intrigued me and decided to deepen my knowledge so that I could one day use it in the Petroleum Engineering industry. This Repository coresponds to all the projects I did in Python and R to complete my certificate. 

Below is a Summary of the aim and results of the various projects I completed. The complete description and lines of code are located inside this repository and are linked in this summary.
___

#### Course Objectives and Outcomes:


* Identify types of business problems for which data analysis can provide significant insights in support of **business decision-making**.

* Translate business objectives into analytical opportunities using **data mining**.

* Select and justify **appropriate types of data** analysis and statistical procedures

* Apply **data analytics in eCommerce** (e.g., understanding customer behavior, segmenting customers by key demographic factors, selecting new products strategically and predicting their profitability).

* Become broadly competent in the use and evaluation of **statistical machine learning techniques** of classification, regression and association.

* Apply **dimensionality reduction** methods to broad datasets to reduce their complexity prior to modelling

* Identify and solve collinearity through feature engineering and **feature selection**

* Interpret the results of data analysis to **make models and predictions** and to establish the reliability of those predictions.

* Acquire, process, and **analyze extremely large data sets** using cloud-based data mining methods to discover patterns or do data exploration.

#### Course Agenda


First Header | Second Header | Third Header
------------ | ------------- | ------------
Content from cell 1 | Content from cell 2
Content in the first column | Content in the second column

1. **Introduction**: objectives, plan
2. **Variogram Calculation**: quantifying spatial continuity
3. **Variogram Modeling**: formulating valid spatial continuity models
4. **Kriging**: spatial estimation
5. **Conclusions**: summary and feedback

#### Getting Started

Here's the steps to get setup locally with Anaconda for Python 3.\*, common Python packages, Jupyter Notebooks and the GeostatsPy package:

1. Install [Anaconda 3](https://www.anaconda.com/products/individual). 
2. From Anaconda Navigator (within Anaconda3 group), go to the environment tab, click on base (root) green arrow and open a terminal. 
3. In the terminal type: pip install geostatspy. 
4. Open Jupyter Notebook and in the top block get started by copy and pasting the code block below from this Jupyter Notebook to start using the geostatspy functionality. 

```python
import geostatspy.GSLIB as GSLIB
import geostatspy.geostats as geostats
```

For more information about about the GeostatsPy package check out the [documentation](https://github.com/GeostatsGuy/GeostatsPy) and [code](https://github.com/GeostatsGuy/GeostatsPy/tree/master/geostatspy). 

You will need to copy these data files to your working directory.  They are available in the [DataSets](https://github.com/GeostatsGuy/GeostatsPy_Intro_Course/tree/master/DataSets) folder of this repository:

* [sample_data_MV_biased,csv](https://github.com/GeostatsGuy/GeostatsPy_Intro_Course/blob/master/DataSets/sample_data_MV_biased.csv)

* [sample_data_biased.csv](https://github.com/GeostatsGuy/GeostatsPy_Intro_Course/blob/master/DataSets/sample_data_biased.csv)




*Marcelo*
