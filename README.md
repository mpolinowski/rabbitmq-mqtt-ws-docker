# RabbitMQ Docker

Run a Rabbit Message Que using Docker and Docker-Compose. Install all necessary plugins to use RabbitMQ as your MQTT Broker and connect to with your client software either using the MQTT or AMQP protocol over a websocket connection.


## Build

Take the `Dockerfile ` and build the RabbitMQ image with all plugins installed:

```bash
docker-compose build
```


## Run

Run the container with the following command to be able to see the container log for debugging. The container will expose 

```bash
docker-compose up
```


| Service | Exposed Port |
| -- | -- |
| __AMQP__ | `5672` |
| __Management__ | `15672` |
| __MQTT__ | `1883` |
| __WebSocket__ | `15675` |


MQTT over WebSocket can be accessed at `ws://server-address:15675/ws`.


Once everything is working use the `-d` flag to detached the container from your console:

```bash
docker-compose up -d
```