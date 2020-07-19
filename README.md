# Portfolio
MSc in Physics Facundo N. Paris

# [Impact of prisons on their surrounding venues](https://github.com/facuparis/Coursera_Capstone)
The main goal of this project is to describe one of the socioeconomic impacts of prisons: the number of venues in their surroundings. The focus will be to find and describe the influence radius of the prisons in the state of Alabama. Finally, we want to cluster the prisons by the similarities on their influences.(Full report and code click in the title)  

### Data Collection 
In this [link](https://www.prisonersofthecensus.org/data/kml.html) you can download an ''.kml'' file for each state in the USA. Here we can find the name, description, Correctional Population, and the GPS coordinates of each facility. The beautifulsoup library enables us to handle this type of extension.
The population number is important because a facility with a small number of inmates will be small, and may be unnoticed by the people on that neighborhood, introducing a bias in the study. It is possible that big facilities are constructed farther apart from cities, but if there is any, it will not go unnoticed. For this study we will keep only the prisons with populations larger than 600 inmates. With this restriction our dataset consists of 18 prisons. 
Now we use the Foursquare API to find the venues in the surroundings of a prison. Then, we use the geopy distance library to calculate the distance between a prison and the venues nearest to it.

### Results
We calculate the average value of near venues for all the prisons. Using regplot from seaborn library, we show a positive linear relationship between the meters from a facility and the number of venues. So, again, the presence of a prison impacts its surroundings in a negative way, reducing the number of venues in its vicinity. The number of venues grows as we go further away from the facilities.
As the final step of this analysis we apply a machine learning technique to cluster the prisons based on the distance to the venues. We use K-Means and the number of clusters was set to 3.  
When we analyze each cluster, we see that the violet dots are the prisons with almost no venues near them, the red dot is the Mobile County Jail that has a medium amount of venues, concentrated in the range of 1000-1200m. The last cluster corresponds to the green dots, which includes Jefferson County Sheriff's Office, Madison County Main Detention Facility and the Tuscaloosa County Jail. These facilities are the ones with the most venues in their surroundings. 
The top 5 biggest cities in the state of Alabama are: Birmingham ,Montgomery ,Mobile ,Huntsville, Tuscaloosa. There is a strong correlation between the city size and the number of venues near a facility. Green dots are in Birmingham,Huntsville and Tuscaloosa. Mobile is the red dot, and In Montgomery there are a lot of facilities but they are far away from the city. 


![](/images/prisons.png)
