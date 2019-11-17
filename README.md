# RabbitMQ MQTT dla MySensors i Domoticza

## Run

```
docker run -d --hostname my-rabbit --name some-rabbit -e RABBITMQ_DEFAULT_USER=ssh -e RABBITMQ_DEFAULT_PASS=ppp123 -e RABBITMQ_DEFAULT_VHOST=ssh -p 15672:15672 -p 1883:1883 greetingsfrompoland/ssh-rabbitmq-mqtt-mysensors:latest
```

### Docker Compose

```
  rabbitmq:
    image:  greetingsfrompoland/ssh-rabbitmq-mqtt-mysensors:latest
    hostname: rabbit
    environment:
      RABBITMQ_DEFAULT_USER: ssh
      RABBITMQ_DEFAULT_PASS: ppp123
      RABBITMQ_DEFAULT_VHOST: ssh
    volumes:
      - app_rabbitmq_data:/var/lib/rabbitmq
      - app_rabbitmq_conf:/etc/rabbitmq/
    ports:
      - 15672:15672
      - 1883:1883
```