# adm

administrative borders of denmark

kommunale administrative grænser i multupart udgade - dvs. at hver kommune består af en række i tabellen 

De tre obligatoriske filer (.shp , .dbf ,  .shx) må ikke slettes. svarer til henholdsvis geografien, den bagvedlæggende tabel og det index, der kæder de to ting sammen

Tabellen bag de administrative grænser indeholder blandt anden Kommunenavn, Kommunekode ( eks 0101 for Københavns Kommune), Regionskode, Landsdelskode. En oversigt over kommunekoder kan findes på http://download.aws.dk/adresser

Det burde være lige til at lave et left_joine, når I skal visualisere data

Dataet er en ældre udgave hentet fra download.kortforsyningen.dk, men don't worry så meget er der heller ikke sket med grænsedragningen.

Data kan også lives trækkes gennem kortforsyningens Web Feature Service :

https://services.kortforsyningen.dk/service?request=GetCapabilities&version=1.0.0&ticket=08002cd91d930f8bf19d9c496c790712&servicename=dagi_gml2&service=WFS


GETTING STARTET in Python:

https://stackoverflow.com/questions/30447790/displaying-a-shapefile
