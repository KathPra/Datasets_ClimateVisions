# Towards Understanding Climate Change Perceptions: A Social Media Dataset
This repo contains the official release for [Towards Understanding Climate Change Perceptions: A Social Media Dataset](https://www.climatechange.ai/papers/neurips2023/3) by [K.Prasse](https://www.uni-mannheim.de/dws/people/researchers/phd-students/katharina-prasse/), [S. Jung](https://jung.vision/), [I. Bravo](https://www.researchgate.net/profile/Isaac-Bravo-3), [S. Walter](https://www.professoren.tum.de/tum-junior-fellows/walter-stefanie), and [M. Keuper](https://www.uni-mannheim.de/dws/people/professors/prof-dr-ing-margret-keuper/).

Update: Given the updated X research access regulations, we are no longer allowed to share image links and have therefore removed them from the repo. Shortly, we will share image Twitter IDs to retrieve the images using the official X Api.

## Dataset Description
The image data is provided in the form image urls of X/Twitter images from the year 2019 in the context of climate change ("climatechange" or "climate change" or #climatechange).
Each downloaded image is either in ClimateCT or ClimateTV.
The annotations for ClimateCT are created by two independent annotators, while ClimateTV is annotated based on the hashtags shared along with the images.
This allows for an image independent annotation which may be noisy for the images where the hashtags do not match the image content.


## JSON
These files are intended for easy access to the data.
The labels are semantic.

## HDF5
These files contain the train/test split for ClimateCT in order to reproduce the results from the paper.
The labels are numeric:
```
# create mapping for labels
animal_mapping={'Amphibian or Reptile':0,'Birds':1, 'Farm animals':2, 'Fish':3, 'Insects':4,'Land mammal':5,  'No animals':6,'Other animals':7,  'Pets':8, 'Polar bear':9, 'Sea mammal':10}
setting_mapping={'Agricultural/rural':0,'Arctic, Antarctic':1, 'Desert':2, 'Forest, jungle':3, 'Indoor space':4, 'Industrial':5, 'No setting':6,'Ocean, coastal':7,'Other setting':8, 'Other nature':9,  'Outer space':10, 'Residential/commercial':11}
climateaction_mapping={'Fossil energy': 0, 'No climate action': 1, 'Other': 2,'Politics': 3, 'Protests': 4, 'Sustainable energy': 5}
consequences_mapping={'Biodiversity loss': 0, 'Covid & general health': 1, 'Drought': 2, 'Economic consequences': 3, 'Floods': 4, 'Human rights': 5, 'Melting Ice': 6, 'No consequences': 7, 'Other consequences': 8, 'Other extreme weather events': 9, 'Rising temperature': 10, 'Sea level rise': 11, 'Wildfires': 12}
type_mapping={'Collage': 0, 'Data Visualization': 1, 'Illustration': 2, 'Infographic': 3, 'Meme': 4, 'Other': 5, 'Photo': 6, 'Posters/Event invitations': 7, 'Screenshot': 8}
```
### For ClimateCT the structure is: 
1. train / val
2. label_class / url_class: The labels and and url are in the same order

### For ClimateTV the structure is:
1. label_class / url_class: The labels and and url are in the same order
In this case, there is no train/test split because all images are used for testing only.
