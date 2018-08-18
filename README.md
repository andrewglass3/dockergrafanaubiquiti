# grafanagockerubiquiti
My configs for grafana/telegraph/influxdb to show Ubiquiti Access Points and Edgerouter X

This is a basic skeleton for getting grafana running in docker to monitor and collect data for my edgerouter x and unifi access points.

To get this running I advise you create the following directories:
<configdir> - for telegraph persistent storage - place the telegraf.conf here
<influxdata> - for influxdb persistent storage
<grafanadata> - for grafana persistent storage
  
Modify your docker compose to reflect your persistent storage locations.
