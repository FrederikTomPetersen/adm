# Accessing geodata from different sources
This repo aims to enable users to access to different sources of geodata and manage them in an easy way

Geodata basically comes in two dataformats - vector data and raster data

# Rasterdata
Rasterdata is images with a certain pixel resolution which gives the rasterdatasets gridcell size. Raster data can be anything from satelitte images, ortophotoes, elevation models ect. The values of the cell lies in the bandwidth of the images. Raster dataset are typically analyzed through, local, focal, zonal and global methods.

# Vectordata
Vectordata is your typical data but with the addition of a geography. the geography can either be a point, a line and a polygon. These types of data needs geograpically consistency. For example the outline of a polygon can not intersect it self. 

Vectordata comes in a whole bunch of formats which typically is due to the fact that all GIS-software developers created their own types of files compatiable with their GIS-software. I have no intention on elaborating on every type. For a start I will eleaborate on shapefiles which has become the most common type fileformat for distribution besides the GeograpicMarkupLanguage (GML) and GeoJson.

# shapefiles 
Shapefiles (.shp) is by far the easiest way to distribute static datafiles. The shapefiles consists of severeal file types. Three of these diffent files are manadatory. These files are the .shp which contains the features geography, .dbf which contains the data associated with the geographies. it is basically a table. the last file is the .shx which is the index, this serves to connect the .shp and .dbf and index the data for faster processing. for a more complete description see the technical description: https://www.esri.com/library/whitepapers/pdfs/shapefile.pdf 

Shapefiles can be downloaded all over the internet - simply serach for what you are looking for. 
Here is a link to the national boundaries of the world: https://geonode.wfp.org/layers/geonode%3Awld_bnd_adm0_wfp










Administrative grænser  - Administrative borders of denmark



This repo aims to contain teh administrative borders of Denmark in shapefile format for static downsload


kommunale administrative grænser i multupart udgade - dvs. at hver kommune består af en række i tabellen 

De tre obligatoriske filer (.shp , .dbf ,  .shx) må ikke slettes. svarer til henholdsvis geografien, den bagvedlæggende tabel og det index, der kæder de to ting sammen

Tabellen bag de administrative grænser indeholder blandt anden Kommunenavn, Kommunekode ( eks 0101 for Københavns Kommune), Regionskode, Landsdelskode. En oversigt over kommunekoder kan findes på http://download.aws.dk/adresser

Det burde være lige til at lave et left_joine, når I skal visualisere data

Dataet er en ældre udgave hentet fra download.kortforsyningen.dk, men don't worry så meget er der heller ikke sket med grænsedragningen.

Data kan også lives trækkes gennem kortforsyningens Web Feature Service :

https://services.kortforsyningen.dk/service?request=GetCapabilities&version=1.0.0&ticket=08002cd91d930f8bf19d9c496c790712&servicename=dagi_gml2&service=WFS


GETTING STARTET IN PYTHON:

https://stackoverflow.com/questions/30447790/displaying-a-shapefile
