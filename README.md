# grafanagockerubiquiti
My configs for grafana/telegraph/influxdb to show Ubiquiti Access Points and Edgerouter X

This is a basic skeleton for getting grafana running in docker to monitor and collect data for my edgerouter x and unifi access points.

To get this running I advise you create the following directories:

<configdir> - for telegraph persistent storage - place the telegraf.conf here
  
<influxdata> - for influxdb persistent storage
  
<grafanadata> - for grafana persistent storage
  
Modify your docker compose to reflect your persistent storage locations.

Notice - due to the user permissions in grafana 5.1.0 we have to specify the user in the docker compose under the grafana section.


Login to your Grafana instance using http://localhost:3000 - default user and password of admin/admin

We then need to add a datasource to our instance for influxdb http://localhost:3000/datasources

Add influxdb and set:

Name - telegraf (this is set in your telegraf.conf file
Type - Influxdb
URL  - http://localhost:8086
Access - Server (default)
Leave the Auth tick boxes empty
Leave skip TLS Verification tick box empty
Advanced Http Settings
Whitelist Cookies - leave empty

InfluxDB Details - these should match the details set in the Output Plugins section of the telegraf.conf
Database - telegraf
User     - admin
Password - admin

Click Save & Test and it should confirm connection with - Data source is working in a green box.

Next on the top left you will see a + symbol, click then select import:

In the Grafana.com Dashboard enter the ids for each dashboard you want to import:

Edgerouter Dashboard - https://grafana.com/dashboards/1756 >> the id to enter is 1756 then click load

Unifi Dashboard      - https://grafana.com/dashboards/1486 >> the id to enter is 1486 then click load

#
