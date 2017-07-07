## itg-eaton93pr

InfluxDB + Telegraf + Grafana stack for read the stats from Eaton 93PR UPS. The stats are polled by telegraf via SNMP with 60s interval.

Stats mapped:
- Mode
- Input status
- Input phase voltage
- Input phase freq
- Input situation (voltage or freq out of range)
- Output status
- Output phase voltage
- Output phase freq
- Output load % per phase
- Output temp status
- Inverter status
- Battery status
- Battery voltage
- Battery time remaining
- Battery replace needed
- Low battery condition
- Battery charge
- Charger status


### Requirements
- docker>= 1.10
- docker-compose >= 1.7.1

### Usage
First you need to set your UPS address in the **UPS_HOST** env var placed in the .env file

1. Bring up the stack:
```shell
docker-compose up
```
2. Go to [http://localhost:3000](http://localhost:3000) in your browser, you should see Grafana's login page (user:admin, pass:admin)

3. Setup a new datasource with the following values, then click "Add":
  - Name: whatever you want, ie influxdb
  - Type: InfluxDB
  - URL: http://influxdb:8086
  - Database: ups

4. Import the dashboards ("Dashboards" -> "Import") from the dir grafana of this repo 
