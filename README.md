# 2020-carbon
Work travels by members of a research lab.
Visualization implemented with D3.v6



In order to run the visualization:
- open a terminal in the same directory where this readme is located
- run: python3 -m http.server 8000
- open the path in a browser: http://localhost:8000/viz/subsets_analysis.html


## Content

* **data/** the data in [tsv](https://bl.ocks.org/mbostock/3305937).
	* **missions.tsv** trips details
	* **users.tsv** members of the lab (pseudonymized)
	* **places.tsv** travel destinations
	* **countries.tsv** country codes
* **viz/** visualisation
* **vendor/** vendorized d3 v6.2.0 library

## Data structure

The attributes present in the **mission** table are:

* **mission_id** a unique id for missions (5615 values)
* **user_id** reference to a record in the **users.tsv** table
* **place_id** reference to a record in the **places.tsv** table
* **date** date of the trip in [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601) format
* **duration** duration of the stay in hours
* **mode** main mode of transport {'public', 'car', 'train', 'plane', 'other'}
* **co2** CO2 emmission per person per km

The **co2** value is in kg.

The attributes present in the **mission** table are:

* **user_id** a unique id for users (512 values)
* **name** the pseudonym for the user (unique for a given **house**)
* **house** groups of users (39 houses)
* **region** groups of houses (7 regions)
* **title** kind of user (4 titles)
* **rank** rank of user (ordered levels from 'A' (intern) to 'K' (emeritus), comparable accross titles)
* **institution** intitution of user (4 institutions + none)

The attributes present in the **place** table are:

* **place_id** a unique id for places (627 values)
* **distance** distance from Grenoble in km
* **country** [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code, usable for lookups into **countries.tsv** table

The actual locations are not given to reduce the chance of leaking private information.

The attributes present in the **countries** table are:

* **alpha2** the [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) country code (252 values)
* **country** name of the country in english (source [GeoNames](https://www.geonames.org/countries/))
* **continent** 2 letters code for continent

