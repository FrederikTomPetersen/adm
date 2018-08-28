# Accessing geodata from different sources
This repo aims to enable users to access to different sources of geodata and manage them in an easy way.
I'm no expert in either R og Python -so to manageing the data you

Geodata basically comes in two dataformats - vector data and raster data

# Rasterdata
Rasterdata is images with a certain pixel resolution which gives the rasterdatasets gridcell size. Raster data can be anything from satelitte images, ortophotoes, elevation models ect. The values of the cell lies in the bandwidth of the images. Raster dataset are typically analyzed through, local, focal, zonal and global methods.

My favorite way to access raster data is through Web Map Services.

# Vectordata
Vectordata is your typical data but with the addition of a geography. the geography can either be a point, a line and a polygon. These types of data needs geograpically consistency. For example the outline of a polygon can not intersect it self. 

Vectordata comes in a whole bunch of formats which typically is due to the fact that all GIS-software developers created their own types of files compatiable with their GIS-software. I have no intention on elaborating on every type. For a start I will eleaborate on shapefiles which has become the most common type fileformat for distribution besides the GeograpicMarkupLanguage (GML) and GeoJson.

# Shapefiles 
Shapefiles (.shp) is by far the easiest way to distribute static datafiles. The shapefiles consists of severeal file types. Three of these diffent files are manadatory. These files are the .shp which contains the features geography, .dbf which contains the data associated with the geographies. it is basically a table. the last file is the .shx which is the index, this serves to connect the .shp and .dbf and index the data for faster processing. for a more complete description see the technical description: https://www.esri.com/library/whitepapers/pdfs/shapefile.pdf 

Shapefiles can be downloaded all over the internet - simply serach for what you are looking for. 
Here is a link to the national boundaries of the world: https://geonode.wfp.org/layers/geonode%3Awld_bnd_adm0_wfp

# WFS services
Web Feature Services are by far my most favorite way to access data. The WFS is distrubte though a geoserver, which typically is connected to a database. The Geoserver fetches data from a database, and then distribute the data as a service. The major advantage of the WFS is taht once you have set uo your connection you wil lalways be provided with the latest dataset of the specific theme/maplayer requestet.

The WFS is called through a URL which for example could look like: 
http://example.com/geoserver/wfs?service=wfs&version=2.0.0

When called in a non example you should return a GML

The version parametre is useally 1.1.1  -  2.0.0 or 1.2.1

Depending on the purpose different parameters should be added to the base URL of the WFS. For example add:

    -request=GetCapabilities    This will return an overview of the datacontained in the wfs - metadata time!
    -request=GetFeature   	    Returns a selection of features from a data source including geometry and attribute values

example
http://example.com/geoserver/wfs?service=wfs&version=2.0.0request=GetCapabilities

If you want to request a feature you also need to define the typeNames parametre. in the example the "namespace::featuretype" need to be exchanged with the names given by the GetCapabilities request.
http://example.com/geoserver/wfs?service=wfs&version=2.0.0&request=GetFeature&typeNames=namespace:featuretype




https://services.kortforsyningen.dk/service?request=GetCapabilities&version=1.0.0&ticket=08002cd91d930f8bf19d9c496c790712&servicename=dagi_gml2&service=WFS


GETTING STARTET IN PYTHON:

https://stackoverflow.com/questions/30447790/displaying-a-shapefile
