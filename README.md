# RabbitMQ Docker

Run a Rabbit Message Que using Docker and Docker-Compose. Install all [necessary plugins](https://www.rabbitmq.com/protocols.html) to use RabbitMQ as your MQTT Broker and connect to with your client software either using the MQTT or AMQP protocol over a websocket connection.


## Run

Run the container with the following command to be able to see the container log for debugging. The container will expose 

```bash
docker-compose up
```


Check the `./docker-compose.yml` file for the published ports:


| Service | Exposed Port |
| -- | -- |
| __AMQP__ | `5672` |
| __Management__ | `8080` |
| __MQTT__ | `1883` |
| __WebSocket__ | `1885` |


You can access the webinterface on port `8080` and connect to the MQTT Broker on port 1883 - both use default login specified in `./config/login.env`:


![RabbitMQ Docker](./rabbitmq_mqtt_ws_01.png)



MQTT over WebSocket can be accessed at `ws://server-address:1885/ws`.


Once everything is working use the `-d` flag to detached the container from your console:

```bash
docker-compose up -d
```