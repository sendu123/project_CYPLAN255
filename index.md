## Dream of An Ecological Silicon Valley
### Bay Checkerspot Butterfly Help Build A New Ecological Future in Silicon Valley
#### The research topic is about where to create a new habitat for Bay Checkerspot Butterfly to protect native species in Silicon Valley.
![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/cover.png)

### 1.Background
#### 1.1 Pollution And Health Risks
![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/background.png)

Silicon Valley, with a bright economic future, is now facing a serious pollution crisis, including dust pollution, chemical pollution, water pollution and health problems. So we are thinking about finding an ecological method to dream a new future for silicon valley, to protect the native species.

#### 1.2 An Important Umbrellar Species
After doing a lot of research, I realized that saving a random species isn't going to help silicon Valley build a stable ecosystem. So this ecological future needs an important starting point. I find that **Bay Checkerspot Butterfly** is a key umbrella species that protects many native animals and plants in Silicon Valley. As an important pollinator, this means the tiny butterfly can provide protection for a wide variety of native animals and plants. Therefore, it seems like butterflies can help build a new ecological future in Silicon Valley. 

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/umbrella.png)

However, in the study of bay checkerspot butterfly, it was found that they are rapidly declining. It’s imperative and imminent that we should pay more attention to such important species. Therefore, the goal of this project was to generate a suitability map and find out where the best places to build butterfly habitats are in San Jose. The result will be an important start point to start an ecological future.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/Google%20map.png)

### 2.Methodology And Data
#### 2.1 Methodolog
Researching needs of Bay Checkerspot Butterfly

Divide the needs of different life stages

Collecting data

Shapefile to geopandas

Buffer and kernel density

History maps to geopandas

History maps to geopandas

Data overlay

Suitability of caterpillar phase

Suitability of butterfly phase

Suitability of Bay Checkerspot Butterfly

#### 2.2 Data Sources
California plants Data: https://www.calflora.org/app/taxon?crn=1690

California plants Data: https://www.calflora.org/app/taxon?crn=1695

California plants Data: https://www.calflora.org/app/taxon?crn=6615

California plants Data: https://www.calflora.org/app/taxon?crn=4952

California plants Data: https://www.calflora.org/app/taxon?crn=4649

California plants Data: https://www.calflora.org/app/taxon?crn=4577

Land Use Classification Data: https://gisdata-csj.opendata.arcgis.com/pages/tree-canopy-and-land-use-classification

Aerial Imagery and Elevation: https://gisdata-csj.opendata.arcgis.com/pages/imagery-and-elevation

Road System Data: https://gisdata-csj.opendata.arcgis.com/maps/CSJ::public-street


### 3.Life Cycle of Butterfly
![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/life.png)

Caterpillars and butterflies have different ranges of activities, so the key findings focus on habitats that are suitable for two stages of the butterfly's life cycle, including **Caterpillar stage, butterfly stage**. This classification can make the results of the assessment more accurate.


### 4.Key Findings
In this part, I used python(mostly geopandas) to generate to distributions of certain needs of the bay chekerspot butterfly, and overlay the distribution and topography to help people better understand the context. At the same time, rate diffrent kinds of needs, the most suitable one for caterpillars or butterflies to live wins the highest point. This rating systerm can help quantify the overall analysis process and help create the final suitability map in the next step.

#### 4.1 Needs of Caterpillar
#### 4.1.1 Living on low shrubs
First, in the caterpillar stage, my key finding is that caterpillars need to hang on small shrubs to absorb heat from the ground. So we use geopandas to visualize the distribution of four kinds of low shrubs using the landcover data. There are four different colors in this map representing these shrubs. 

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/c_shrub2%20change.png) 

#### 4.1.2 Living near ridgelines
Caterpillars should be near ridge lines because butterflies need to spawn and mate at ridgelines. So I used elevation data to generate the ridgelines and visualized the distribution of ridgelines through geopandas.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/c_ridge1.png) 

#### 4.1.3 Living in serpentine soil

Caterpillars need to diapause in serpentine soil. The soil has many cracks which allows butterfly larvae or chrysalises to live in and prevents animals from trampling on caterpillars. The source of the soil data is from a historic distribution map, I used georeference tools to get the coordinates, and finally generate the area in geopandas.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/c_soil3.png) 

#### 4.1.4 Living near host plants
Caterpillars also need host plants for food, then I found three main host plants for caterpilars. And I used geopandas to show the locations of the host plants.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/cater%20plant.png)

But I found that the points are too small to generate a suitability map when overlay those layers, so I changed those point data to **Kernel Density** of host plants.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/c_plant4.png) 

#### 4.1.5 Living away from roads
Nitrogen dioxide produced by roads would encourage the growth of invasive species, these invasive species are main threats for host plants which are native to California. Therefore, the area within 200 meters of the road is very bad for caterpillars. I set up a 200-meter buffer for the road in Python, and the area inside the buffer gets only one point, while the area outside the buffer gets nine points.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/t_road.png) 

#### 4.1.6 Living away from developed land
I also took land use into account because human developments have an impact on bay checkerspot butterfly. This is a map showing distribution of developed lands with different land use. Depending on how much damage they do to the butterflies, they get different points.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/t_people.png) 

#### 4.2 Needs of Butterfly
#### 4.2.1 Living near host plants
In the Butterfly Stage, butterflies also need nectar plants for food. Here is the distribution of the nectar plants of bay checkerspot butterfly.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/butter%20plant.png) 

I used the same method to get the **Kernel Density** of nectar plants.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/b_plant5.png)

#### 4.2.2 Living near ridgelines
Butterflies need ridgelines to mate, and I also get the distribution of Ridgelines as well as a **200 meter buffer** because butterflies and caterpillars have different flying abilities.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/b_ridge6.png)

#### 4.2.3 Living near water
I also get the distribution of wetlands in San Jose because butterflies need waterlands for drinking water.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/b_water7.png)

### 5.Results---Suitability Map
Eventually, I used raster calculator to combine all layers to two suitability maps respectively for Caterpillar and Butterfly. Because in the previous stage, we graded each cell in each layer. Now each cell in different layers has different scores. I reclassified the scores in each image and add the scores of each pixel in different images to form two suitable maps for both butterflies and caterpillars. And overlay the two suitability map to get the fianl suitability map.

![](https://raw.githubusercontent.com/sendu123/project_CYPLAN255/gh-pages/drawings/map_final.png)

In the future, these area with the highest scores will have the biggist chance to build a habitat for bay checkerspot butterfly. Once the butterfly species are established, the native plants and animals under the "umbrella" will be protected, and the chance of an ecological future of Silicon Valley will be established.

### Contact
#### Final project for CYPLAN255
#### Sen Du (sen_du@berkeley.edu)
#### Professor: Max Gardner
