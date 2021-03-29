# Monitoring with Prometheus

Prometheus is an open source monitoring solution created by sound cloud. The main idea of prometheus is to get metrics when its necesary, so for each exporter the time to scrap can be defined in the configuration file of the Prometheus server.

## Architecture
Prometheus works with 2 main components. 
- Prometheus Server
- Exporters

Prometheus server is the main instance who holds the configuration of where and who to scrape. Also the scraped data is stored in his local databas.
Promethues server go's to each exporter/targed who is defined in the `prometheus.yml` and ask his "Son" for the actual information.
The time interval can be defined on global or for each exporter. See more in the example code.

Exporters are quite different. So there exists severel types. For mor information go to the main documentation of prometeus. As example there are: 

- Node Exporter -> Gets system metrics
- Nginx Exporter -> Webserver Nginx metrics as Requests, read/write information, etc
- Grok Exporter -> Converts your own metrics in prometheus readeble metrics
- DB Exporter -> MySql or Oracle exporters to get information over your DB.
- ELK Exporter -> Elastik Search exporter. Get metrics ocer Elastik querys to have them in prometeus and to be able to do calculations, etc


## Node Exporter

Exporters are made for scraping data from your target machine. For each propose normaly exists an exporter. If not, you are always able to create your own with GO or Python. Find more informtion on Prometheus.io 

### How to start an exporter

Exporters work with his own web server and expose metrics over an specific port. Its allway grate to have an standard, so in my experience, i always expose de exporrters on port 100[XX]. So for example, node exporter `10.0.0.13:10090`. Why? having big networks bby this way its easy to identificate the exporters. 

Node exporter comes with some aditional configuration. So it is possible to start the exporter ofer an specific port or to activate mor scraping information. See the next list of my comun options. On the specific github page from `Node Exporter`you will find more options.

`node_exporter --collector.systemd --collector.netstat --web.listen-address=:10090`

- --collector.systemd -> Gives information over the system services
- --collector.netstat -> Network information
- --web.listen-address=:10090 -> Port especification


