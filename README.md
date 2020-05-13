# dat-visualization-2
# First import the Pandas library needed for this task
import pandas as pd
In [2]:
# Read the csv file from the link
df = pd.read_csv('https://cocl.us/datascience_survey_data', sep=',', index_col=0)
print('Data read into DataFrame df')
Data read into DataFrame df
In [3]:
# Show df
df

                                  Very interested	     Somewhat interested     	Not interested
Big Data (Spark / Hadoop) 	            1332	                 729	                 127
Data Analysis / Statistics	            1688	                 444	                 60
Data Journalism	                        429	                   1081	                 610
Data Visualization	                    1340	                 734	                 102
Deep Learning	                          1263	                 770	                 136
Machine Learning	                      1629	                 477	                 74
# First import Matplotlib

%matplotlib inline 

import matplotlib as mpl
import matplotlib.pyplot as plt
print ('Matplotlib version: ', mpl.__version__)

# San Francisco latitude and longitude values
latitude = 37.77
longitude = -122.42

# create a plain world map
sanfran_map = folium.Map(location=[latitude, longitude], zoom_start=12)

# generate choropleth map
sanfran_map.choropleth(
    geo_data=sf_geo,
    data=df_crime_nh,
    columns=['Neighborhood', 'Count'],
    key_on='feature.properties.DISTRICT',
    fill_color='YlOrRd', 
    fill_opacity=0.7, 
    line_opacity=0.2,
    legend_name='Crime Rate in San Fransisco'
)

# display map
