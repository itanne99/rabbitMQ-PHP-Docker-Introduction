# RabbitMQ-PHP-Docker-Introduction

## Pre-req Install
- Docker Desktop

## How to Set Up Docker Containers
1. Open terminal to project directory
2. Run ```cd ./rabbitmq-client```
3. Run ```docker build . -t local-rabbit-client```
   1. This may take a minute or two
4. Return to the project root directory
5. Run ```cd ./rabbitmq-listener```
6. Run ```docker build . -t local-rabbit-client```
7. Return to the project root directory
8. Run ```docker compose up -d```
   1. This may take a minute or two

## Setting up RabbitMQ
1. After building the docker-compose
2. Open your browser and go to `localhost:15672`
3. Use the default login. User & Pass is `guest`
4. Click on 'Admin' tab
5. Click on 'Virtual Hosts' on the right side of the web page
6. In the 'Name' input enter: `testHost`
7. Click "Add virtual host"
8. Click on 'Users' on the right side of the web page 
9. In the 'Username' input enter: `test`
10. In both 'Password' inputs enter: `test`
11. Click 'Add user'
12. Click the 'test' on the top of the webpage
13. Under 'Set permission'
14. Change 'Virtual Host' in dropdown to `testHost`
15. Click 'Set permission'
16. Click 'Exchanges'
17. Under 'Add a new exchange'
18. Change 'Virtual Host' in dropdown to `testHost`
19. In the 'Name' input enter: `testExchange`
20. Click 'Add exchange'
21. Click on 'Queues'
22. Under 'Add a new queue'
23. Change 'Virtual Host' in dropdown to `testHost`
24. In the 'Name' input enter: `testQueue`
25. Click `testQueue`
26. Under 'Bindings'
27. In the 'From exchange' input enter: `testExchange`
28. In the 'Routing key' input enter: `*`
29. Click 'Bind'
30. The RabbitMQ Server is now ready for the listener and client

## Running the RabbitMQ Listener
1. After building the docker-compose
2. In terminal, Run `docker start rabbit-listener`
3. The listener should be up and running

## Running the RabbitMQ Client
1. After building the docker-compose
2. In terminal, Run `docker start rabbit-client-1`
3. To check if it ran, Run `docker container logs rabbit-listener`
4. That's it for the RabbitMQ Client