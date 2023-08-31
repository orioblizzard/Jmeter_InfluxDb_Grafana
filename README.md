# JMeter, InfluxDB, and Grafana Setup using Docker Compose

This project demonstrates how to set up a testing environment using JMeter, InfluxDB, and Grafana using Docker Compose. It allows you to perform load testing with JMeter, store the results in InfluxDB, and visualize them in Grafana.

## Prerequisites

- Docker and Docker Compose are installed on your system.

## Getting Started

1. Clone this repository to your local machine.

```sh
git clone https://github.com/orioblizzard/jmeter-influxdb-grafana-docker.git
cd jmeter-influxdb-grafana-docker
```

## Contributing

1. Open the docker-compose.yml file and configure the environment variables for InfluxDB and Grafana (if needed). Adjust the database names, users, and passwords according to your preferences.

2. Start the services using Docker Compose.

```sh
docker-compose -f D:\your\file\ymalPath up -d
```
3. InfluxDB Configuration
    - InfluxDB is accessible at http://localhost:8086 after starting the services.
        - Open your web browser and navigate to the Grafana URL (e.g., http://localhost:3000), then log in with your configured credentials.

        - Once logged in, you'll be taken to the Grafana dashboard.

        - Click on "Configuration" (or the gear icon at the bottom left corner), then select "Data Sources".

        - Click on "Add data source" to add a new data source.

        - Select "InfluxDB" from the list of available data sources.

        - Under the "HTTP" section, fill in the following details:
            - URL: http://influxdb:8086 (The name influxdb is the service name in Docker Compose)
            - Access: Server
            - Database: The database name you configured in InfluxDB
            - User: The username you configured in InfluxDB
            - Password: The password of the user you configured in InfluxDB

        - Click on "Save & Test" to test the connection to InfluxDB and save the configuration.

        - Once the connection is successfully tested and the configuration is saved, you will receive a confirmation message on the screen.
        
    - You can use the InfluxDB command line tool (influx) or other InfluxDB clients to interact with the database.

4. Access Grafana in your web browser at http://localhost:3000. Use the default credentials (admin/admin) to log in.

5. Configure Grafana to connect to the InfluxDB data source:
    - Add InfluxDB as a data source.
    - Configure the connection details, such as the URL and database name.
    - Test the connection and save the data source.

6. Create dashboards and panels in Grafana to visualize the JMeter load test results stored in InfluxDB.


## Usage/Examples

1. Use JMeter to perform load testing and generate test results.

2. Configure the JMeter Backend Listener to send the results to InfluxDB. Use the appropriate configuration for InfluxDB connection.

3. InfluxDB will store the test results data.

4. Open Grafana and create dashboards to visualize the data:

    * Add panels to the dashboard.
    * Configure the panels to display the desired data using the InfluxDB data source.


## Clean Up

To stop and remove the containers, use the following command:

```sh
docker-compose -f D:\jmeterLab\dockers\docker-compose down
```
## License

This project is licensed under the MIT License.

## Authors

- [@orioblizzard](https://www.github.com/orioblizzard)