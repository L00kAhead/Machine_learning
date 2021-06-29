# Machine_learning
# Oreeva Dataset Description

## What is inside
Dataset contains records of completed real estate transactions in the United Kingdom. There are some groups of features:

- **Land Registry**: government's list of all real estate transactions with prices and other main properties.

- **EPC**: Energy Performance of Buildings Data England and Wales. Database which describes energy efficiency of most real estate properties. [Details](https://en.wikipedia.org/wiki/Energy_Performance_Certificate_(United_Kingdom))
- **Feature Engineering**: Features that were not obtained directly from databases, but instead were calculated through the parsing of various sources. For example `closest_school` was obtained by calculations from OSM using the geographic coordinates of the property.

## Features description
[Land Registry features](https://www.gov.uk/guidance/about-the-price-paid-data):
- 'transaction_id': some unique id of transaction (not important for training)
- `created`: transaction date formatted as 'YYYY-MM-DD'
- `duration`: in the UK there are two types of ownership, freehold - the land in your property, leasehold: the land belongs to the landlord, usually such a lease lasts for several decades. [details](https://hoa.org.uk/advice/guides-for-homeowners/i-am-buying/leasehold-v-freehold-whats-the-difference/)
- `price`:  price in pounds. this is target column
- `old_new`: is this a new flat (purchased from building company first time). Y - new, N - old
- `property_type`: type of property: F=flat	T=terraced house D=detached house and S=semidetached house
- `postcode`: zip code is an local feature, no more than ten houses usually belong to one postcode, String
- `city`: String
- `street`: String
- `building_name`: some houses do not have a number, but have a name, a string (this is UK, bro)
- `building_number`: String

[Energy Performance Certificates features](https://epc.opendatacommunities.org/docs/guidance#FAQ):
- `flat`
- `floor_level` 
- `number_of_rooms` 
- `total_floor_area`  
- `epc_current_energy_rating` 
- `epc_potential_energy_rating` .
- `epc_property_type` 
- `epc_built_form` 
- `epc_energy_consumption_current` 
- `epc_lighting_cost_current` 
- `epc_heating_cost_current` 
- `epc_hot_water_cost_current` 
- `epc_flat_storey_count` 
- `epc_glazed_area` 
- `epc_number_open_fireplaces` 
- `epc_windows_description` 
- `epc_windows_energy_eff` 
- `epc_walls_description` 
- `epc_walls_energy_eff` 
- `epc_roof_description` 
- `epc_roof_energy_eff` 
- `epc_floor_height` 

__Calculated features:__
- `latitude`: degrees
- `longitude`: degrees
- `postcode_sector`:  Big group of postcodes [Example of N-sector](https://cdn.shopify.com/s/files/1/0720/9527/products/MSM21-greater-london-postcode-sector-map-detail-large_1800x.jpeg)
- `closeststop`: distance to the nearest stop, meters
- `crimesin3km_antisocial`: the number of recorded (for what period - difficult to say) antisocial behaviour within a radius of 3 km, times. [about antisocial behaviour](https://www.police.uk/crime-prevention-advice/anti-social-behaviour/)
- `closestschool`: distance to the nearest school, meters
- `closestpark`: distance to the nearest park or playground, meters
- `address_id`: unique address number (in our database)
- `distance_center`: distance to the business center, km
 
