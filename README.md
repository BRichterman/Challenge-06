# Challenge-06

## Background
Creating a one-click service for people to buy properties and then rent them.

## Important code snippets
### Use API key to access data
''' python
load_dotenv()
#mapbox_api_access_token = os.getenv("MAPBOX_API_ACCESS_TOKEN")
mapbox_api_access_token = 'pk.eyJ1IjoicmljaHRlcm1hbmIiLCJhIjoiY2tydGpyMHdhOXNwNzJ2bXRjbmg5Mm8wYyJ9.zidk7u9JrtiNDSbzxsYXtg'
if not mapbox_api_access_token:
    print("Error with the Mapbox API access token. Check the .env file.")
px.set_mapbox_access_token(mapbox_api_access_token)
'''

### Grouping data so that it is meaningful for analysis
'''python
housing_units_by_year = sfo_data_df.groupby('year').mean()
housing_units_by_year.head()
'''

### Create meaningful graphics
'''python
px.scatter_mapbox(
    all_neighborhoods_df,
    lat="Lat",
    lon="Lon",
    size='sale_price_sqr_foot',
    color='gross_rent',
    size_max=25,
    hover_name='neighborhood'
    zoom=11
)
'''

## Graphics created

* Housing Units By Year 
![zoomed-housing-units-by-year](/Challenge-06/Images/zoomed-housing-units-by-year.png)

* Average Sale Price Per Sqr Foot
![avg-sale-px-sq-foot-gross-rent](/Challenge-06/Images/avg-sale-px-sq-foot-gross-rent.png)

* Pricing Info by Neighborhood
![pricing-info-by-neighborhood](/Challenge-06/Images/pricing-info-by-neighborhood.png)

* Mapbox Plot
![mapbox-plot](/Challenge-06/Images/mapbox-plot.png)
