# RabbitMQ-PHP-Docker-Introduction

## Pre-req Install
- Docker Desktop

## How to Set Up Docker Containers
1. Open terminal to project directory
2. Run ```docker compose up -d```
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

## Running A RabbitMQ Client Message
1. After building the docker-compose
2. Run `docker exec -ti rabbit-client-1 /bin/bash`
3. Once loaded into the container, Run `php testRabbitMQClient.php "[Message]"`
4. From there the rabbit listener will have your message

# Troubleshooting
## To rebuild the docker-compose images
- Run the following command `docker compose build`