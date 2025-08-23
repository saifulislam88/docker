🔍 Scenario:
You're deploying a RabbitMQ container in Docker and want to persist its data and use a custom config.
You decide to use Docker volumes like this:

docker run -d --name rabbitmq-prod --hostname rabbitmq-prod \
  -v rabbitmq-data:/var/lib/rabbitmq \
  -v rabbitmq-data:/etc/rabbitmq \
  --restart unless-stopped \
  -p 5672:5672 -p 15672:15672 \
  rabbitmq:management

❌ Problem:
In the above command, the same named volume `rabbitmq-data` is mounted to two different paths:
- /var/lib/rabbitmq (for data)
- /etc/rabbitmq (for configuration)

This creates a serious issue:
- It overwrites RabbitMQ's expected configuration directory with unrelated data
- RabbitMQ might fail to start or behave unpredictably
- You lose separation between configuration and persistent data

✅ Correct Usage:
Use separate volumes for each distinct role:

docker run -d --name rabbitmq-prod --hostname rabbitmq-prod \
  -v rabbitmq-data:/var/lib/rabbitmq \
  -v rabbitmq-config:/etc/rabbitmq \
  --restart unless-stopped \
  -p 5672:5672 -p 15672:15672 \
  rabbitmq:management

This ensures:
- Data and config are logically isolated
- Clear structure and easier backup or migration
- Fewer chances of data corruption

📌 Best Practice:
Never reuse the same Docker volume for multiple paths unless they serve the exact same purpose.
