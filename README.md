# Home Metrics

A simple deployment of Grafana and InfluxDB, for use at home and local development. It includes Telegraf to allow for
easy StatsD metrics. Everything is orchestrated using docker compose, and requires an `.env` file for configuration.

The default configuration file will work, but has some _**very**_ weak passwords and tokens. Use at your own risk.

## Setup

**Configuration**

Copy the `.env.example` to a file called `.env`. Edit any values you like in this file. It is **highly** recommended
that you update the secrets and tokens within this file.

**Startup**

Run the following command:

```shell
docker-compose up -d
```

After a few seconds, everything will be started up and ready for use.

## Port Mapping

The following ports are available by default:

| Service | Local Machine Port |
| --- |--------------------|
| Grafana | 3000               |
| InfluxDB | 8086               |
| StatsD | 8125               |

**Note** These ports can be configured in the `.env` file.

## Usage

Graphana is available on `http://locahost:3000` by default, and is where you may visualise your metrics, or create
dashboards for monitoring.

InfluxDB is available on `http://localhost:8086` by default, and is where your metrics are stored. It has some great
data exploration tools, but generally you wont need to use the interface directly.

Telegraf will be used as a StatsD proxy via `udp://localhost:8125`. This is where your applications and scripts should
send their metrics.
