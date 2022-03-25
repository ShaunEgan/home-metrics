# Home Grafana Stack

This is a simple deployment of Grafana with InfluxDB for use at home. It uses docker and docker-compose to spin up
everything, and requires a `.env` file for configuration and secret values.

## Setup

**Configuration**

First, copy the `.env.example` to a file called `.env`. Edit any values you like in this file, especially the secrets to
something only known to you.

**Startup**

Run the following command:

```shell
docker-compose up -d
```

After a few seconds, everything will be started up and ready for use.

## Port Mapping

The following ports are available by default:

| Service | Local Machine Port |
| --- | --- |
| Grafana | 3000 |
| InfluxDB | 8086 |

**Note** These can be configured in the `*_HOST_PORT` settings in the `.env` file.
