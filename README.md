# Spatial Data 101

## Workshop objectives

By the end of this workshop, participants should be able to:

- understand what makes data spatial
- distinguish between vector and raster data
- recognize common spatial analysis questions
- identify where to find spatial data and imagery at Stanford
- know how to access the main Stanford-supported spatial tools
- decide which resource is appropriate for a given project or research question

## Rough workshop outline

1. What is spatial data?
2. Vector and raster basics
3. Points, lines, polygons, grids, and imagery
4. Common spatial analysis tasks: proximity, containment, overlap, change over time
5. Where to find data at Stanford and beyond
6. Accessing and using core spatial tools and services
7. Choosing the right data and method for a research question

## Resource overview and onboarding

### EarthWorks

EarthWorks is Stanford's geospatial discovery platform for finding datasets, maps, and other spatial resources.

How to get started:
- Go to [EarthWorks](https://earthworks.stanford.edu)
- Search by keyword, place, or topic
- Use filters for resource class, data type, provider, and access
- Open a dataset record to review metadata and download files
- Follow any access instructions shown on the record

### Google Earth Engine

Google Earth Engine is a cloud-based platform for large-scale remote sensing and geospatial analysis.

How to get started:
1. Go to the [Earth Engine Code Editor](https://code.earthengine.google.com/)
2. Log in using your Stanford credentials
3. If you are a Stanford user attending a workshop, make sure you have been added to the Stanford GEE access workgroup
4. If you are not a Stanford affiliate, use the [personal-access request flow](https://earthengine.google.com/)
5. Click your profile icon in the top-right corner and select Register a new Cloud Project
6. Give the project a valid name and choose the parent resource for the project
7. Select the Stanford GEE project path or the appropriate project group when prompted
8. Complete the non-commercial registration and enable the Earth Engine API
9. Return to the Code Editor, choose the project, and confirm it is active before starting
10. Test access by loading the [sample script repository](https://code.earthengine.google.com/?accept_repo=users/maplesstanford/LoveData23SampleScripts) used for the 101 workshop.
11. Use the [Python 101 onboarding materials](https://github.com/mapninja/google_earth_engine_python_101) for the workshop and authentication workflow.

The GEE exercise produces the GeoJSON AOI used in the next step, giving participants a reproducible study area for later exploration in Planet Explorer.

### Planet

Planet provides access to high-resolution satellite imagery and Earth observation data.

#### Explore imagery in the Planet web interface

This workshop uses only the Planet.com web GUI. Use the GeoJSON AOI produced in the previous Google Earth Engine exercise to search for imagery in Planet Explorer; no Planet API or coding workflow is required.

1. Go to the [Stanford Planet access page](https://bit.ly/planetstanford)
2. Sign up using your Stanford-affiliated email and credentials
3. After approval, log in to [Planet Explorer](https://www.planet.com/explorer/)
4. Load the GeoJSON AOI produced in the Earth Engine exercise
5. Drag and drop the AOI GeoJSON into Planet Explorer to focus the map on your analysis area
6. Use the Filter Sidebar to inspect available items and view results
7. Search for evidence of recent fires, change, or other conditions in the AOI
8. Toggle earlier imagery to see if you can see burn scars grow

The Planet exercise follows Earth Engine: participants bring the AOI they created there into Planet Explorer and use the web interface to search for and inspect available imagery.

### Stanford Locator

Stanford Locator is a free geocoding service used to convert addresses and place names into geographic coordinates.

#### Geocode one address with the web interface

In this exercise, use the Stanford Locator service to geocode a single address and inspect the JSON result.

1. Go to [Stanford Locator](https://locator.stanford.edu).
2. Open the [USA geocoding service](https://locator.stanford.edu/arcgis/rest/services/geocode/USA/GeocodeServer).
3. On the service page, select **Get Address Candidates** (also labeled **Find Address Candidates** in the REST interface).
4. Enter the address from the example below into the form:
	- Address: `397 Panama Mall`
	- City: `Stanford`
	- Subregion: `CA`
	- Postal: `94305`
	- Postal Extension: `94305`
	- Country Code: `United States`
5. Set the response format to `pjson` (pretty-printed JSON), then submit the request.
6. Compare the resulting page with this example request URL:

	[Example JSON geocode request](https://locator.stanford.edu/arcgis/rest/services/geocode/USA/GeocodeServer/findAddressCandidates?Address=397+Panama+Mall&Address2=&Address3=&Neighborhood=&City=Stanford&Subregion=CA&Region=&Postal=94305&PostalExt=94305&CountryCode=United+States&SingleLine=&outFields=&maxLocations=&matchOutOfRange=true&langCode=&locationType=&sourceCountry=&category=&location=&searchExtent=&outSR=&magicKey=&preferredLabelValues=&f=pjson)

The response is a JSON geocode result. Look for the `candidates` list, then inspect the best candidate's `address`, `score`, and `location` fields. The `location.x` value is the longitude and `location.y` is the latitude. A high score indicates a stronger match, but always review the returned address before using the coordinates in a map or analysis.

### Allmaps

Allmaps is a free, open-source tool for georeferencing historical maps and working with IIIF-based map resources.

#### View an existing map annotation and export it for ArcGIS Online

1. Open the [David Rumsey map record](https://www.davidrumsey.com/luna/servlet/detail/RUMSEY~8~1~25145~990035) and view the map.
2. Get the map's [IIIF manifest URL](https://www.davidrumsey.com/luna/servlet/iiif/m/RUMSEY~8~1~25145~990035/manifest).
3. Open the [manifest in the Allmaps editor](https://editor.allmaps.org/images?url=https%3A%2F%2Fwww.davidrumsey.com%2Fluna%2Fservlet%2Fiiif%2Fm%2FRUMSEY%7E8%7E1%7E25145%7E990035%2Fmanifest&image=https%3A%2F%2Fwww.davidrumsey.com%2Fluna%2Fservlet%2Fiiif%2FRUMSEY%7E8%7E1%7E25145%7E990035&lang=en). This link loads the map and its existing annotations.
4. In the Allmaps editor, click the **Export** button.
5. Copy the exported **XYZ tiles URL**.

### ArcGIS Online

ArcGIS Online is Stanford's browser-based GIS environment for viewing, combining, and sharing web maps.

#### Add the Allmaps XYZ tiles to a new map

1. Go to [ArcGIS Online](https://stanford.maps.arcgis.com) and sign in with Stanford Single Sign-On.
2. Open **Map** to launch Map Viewer, then create a new map.
3. Select **Add** and choose **Add Data from URL**.
4. Enter the XYZ tile URL exported from Allmaps. For this exercise, use:

	[XYZ tile URL](https://allmaps.xyz/images/be75a1837d5d6eba/{z}/{x}/{y}.png)

5. Add the layer to the map and inspect the georeferenced historical map alongside the basemap.

### SimplyAnalytics

SimplyAnalytics is a web-based mapping and analysis platform for demographic and market data.

#### Workshop access

Only two concurrent SimplyAnalytics seats are available, so do not log in during the workshop. Watch the SimplyAnalytics demonstration instead.

After the workshop, you may create a SimplyAnalytics account using your Stanford email address. To access the service later, connect to the Stanford network or Stanford VPN, then sign in at [SimplyAnalytics](https://www.simplyanalytics.com).

## Suggested participant workflow

If you are starting from scratch, a good order is:

1. EarthWorks — find and evaluate data
2. Google Earth Engine — create the AOI GeoJSON and establish the study area
3. Planet — load the AOI in Explorer and search for recent fire evidence
4. Locator — geocode addresses or place names when needed
5. Allmaps — inspect IIIF annotations and export map tiles
6. ArcGIS Online — add the XYZ tiles to a new map

## Helpful links

- EarthWorks: [earthworks.stanford.edu](https://earthworks.stanford.edu)
- ArcGIS Online: [stanford.maps.arcgis.com](https://stanford.maps.arcgis.com)
- SimplyAnalytics: [www.simplyanalytics.com](https://www.simplyanalytics.com)
- Stanford Locator: [locator.stanford.edu](https://locator.stanford.edu)
- Allmaps: [allmaps.org](https://allmaps.org)
- Planet signup: [bit.ly/planetstanford](https://bit.ly/planetstanford)
- Google Earth Engine signup: [signup.earthengine.google.com](https://signup.earthengine.google.com)
- Google Earth Engine Code Editor: [code.earthengine.google.com](https://code.earthengine.google.com/)
- Stanford Geospatial Center: stanford-geospatial@stanford.edu

## Related workshop materials

- [ArcGIS Online 101](https://github.com/mapninja/ArcGIS-Online-101)
- [Planet API 101](https://github.com/StanfordGeospatialCenter/Planet_API_101)
- [Google Earth Engine 101](https://github.com/StanfordGeospatialCenter/Google-Earth-Engine_101)
- [EarthWorks tutorial](https://github.com/StanfordGeospatialCenter/Hacking_EarthWorks_Tutorial)
- [Geocoding / locator resources](https://github.com/StanfordGeospatialCenter/geocoding101)
- [Stanford Geospatial Center workshop series](https://github.com/StanfordGeospatialCenter/SGC-Workshop-Series)
