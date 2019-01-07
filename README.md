# 🔫 Crime and its determinants: Modeling those factors that influence crime rate on Buenos Aires city.

This repository collects datasets, figures and notebooks concering an ongoing research on how city features affect the crime rate on the surrounding areas.

#### Datasets

Unless specify differently, all datasets containing city features came from [BuenosAiresData](http://data.buenosaires.gob.ar/). 

Crime data was pulled from @ramadis [delito-caba repository](https://github.com/ramadis/delitos-caba).

#### Structure

Directory structure is as following:

- `assets`: Contains images and figures as svg or png extension.
- `data`: Contains all datasets used by `main.ipynb` notebook, mostly in csv format. All datasets directly under `data` are tidy and ready to use.
- `data/original` folder contains all raw and untidy datasets, this are datasets before preprocessing.
- `snb` (sidenotebooks): Contains all notebooks  used for data preprocessing. Generaly speaking, each notebook transforms a datasets inside `data/original` and saves it on `data` after some tidy up.

## 🏻 💃🏻 Crime rate on areas surrounding nightclubs

We explore the hypothesis stating that surrounding areas around nightclubs are more dangerous than other areas in Buenos Aires city. This was tested on a crime data subset, selecting only mug reports ocurring from 10pm to 8am during the last hours on a friday, saturday and the early sunday hours.

City geometry was divided in 3520 squares of roughly 250 meters on each side. We considered the crime count in each square being the sum of all reported mugs that occured inside the boundaries of each area. Around each nightclub we defined an area of influence with a radius of 800 meters.

<p align="center">
    <img src="assets/nighclubs_figure_one.png"/>
</p>

**Figure one:** Shows Buenos Aires City divided in 3520 squares, each squares has a color from white to dark blue representing the amount of mugs reported in each area, darker areas have higher crime reports. On orange we represent the position of Buenos Aires' nightclubs and their area of influence.

Effect size was calculated by fitting a linear model using glm and the negative binomial distribution, we report incidence rate rations plus confidence intervals. Inside the area of influence of nightclubs, the crime count was almost 2 times (1.96 CI 1.80 - 2.14) higher than on the areas outside the area of influence. After adjusting by the different neighborhood a total effect of 1.35 (CI 1.20 - 1.51) was observed.






