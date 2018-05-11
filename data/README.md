# User_Behavior_Logs_Quick_Analysis
## Necessary Data Files

This whole project starts with one single user log file. A sample dataset called ```UBA_sample_data``` could be found in this directory. Running the notebook files in order (0 to 3) would generate the rest neccessary data files. 

As for geological information package and databases, run
```
pip install geoip2
```
then download the databases from:
 - City GeoIP - http://geolite.maxmind.com/download/geoip/database/GeoLite2-City.tar.gz
 - Country GeoIP - http://geolite.maxmind.com/download/geoip/database/GeoLite2-Country.tar.gz

and unzip the compresses files within this folder into
 - GeoLite2-City_20180501
 - GeoLite2-Country_20180501