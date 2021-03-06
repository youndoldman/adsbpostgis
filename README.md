# adsb-postgis
ADS-B and MLAT data from local raspberry pis ingested through Kafka into Postgres/PostGIS for spatio-temporal analytics

Initial system will ingest straight to Postgres from a single RasPi running the latest PiAware distro on the LAN.
The next phase will implement 2 more RasPis (on the WAN, not LAN) and a Kafka middleware for better resiliency
with data ingestion (without going the easy route of AWS SQS & RDS due to cost).

Tested on Python 3.5 and 3.6 with Anaconda distro. (all requirements are in the requirements.txt) on both
Windows 10 on Thinkpad T570 and MacOS Sierra on MBPt. Testing on Postgres 9.6 x64 with PostGIS 2.3.2.

~~~
On MacOS:
Download and 'initialize': https://postgresapp.com/
This will also install PostGIS.
Assuming you already have Anaconda installed and on your PATH
conda create -n adsbpostgis python=3.6
source activate adsbpostgis
git clone https://github.com/GISDev01/adsbpostgis.git
cd adsbpostgis
pip install -r requirements.txt
~~~
~~~
Windows:
Download and install: https://www.enterprisedb.com/downloads/postgres-postgresql-downloads#windows
Assuming you already have Anaconda installed and on your PATH
conda create -n adsbpostgis python=3.6
activate adsbpostgis
git clone https://github.com/GISDev01/adsbpostgis.git
cd adsbpostgis
pip install -r requirements.txt
~~~
```
Then, edit the config.yml.template to match your environment, and save as: config.yml

Open a sql shell and run the SQL script in ..\adsbpostgis\sql\postgres_setup.sql
```
Feel free to open a GitHub issue if you have any issues getting this project up and running locally.