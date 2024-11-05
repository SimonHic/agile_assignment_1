## Docker Assignment - Agile Software Practice.

__Name:__ Simon Hickey

__Demo:__ .... The link to your YouTube demonstration ....

This repository contains the containerization of the multi-container application illustrated below:

![](./images/arch.png)

### Database Seeding.

- To automate the seeding of the MongoDB database, I created a mongodb-seed service in the docker-compose.yml file. This service utilizes the mongoimport command to import data from the provided seeding.json file into the tmdb_movies database, with added security by using the environment variables from the .env file. 
- I created a network called 'database-seed-network', which allows secure access to the database container. The automated seeding activates each time the stack is started, providing reliable initial data for development.

### Multi-Stack.

- This current setup provides a robust base for both development and production, with all required services included in the docker-compose.yml file. Currently, all components, such as mongo-express for database managment and mongo-seed for initial data population, are started together, making it ideal for testing.
- In the future, Docker Compose profiles could be implemented to differentiate between development and production environments. This would allow for selective service activation, for example, mongo-expresss and mongodb-seed can be enabled for development but disabled in production, thus ensuring a more secure deployment.

### References
- https://stackoverflow.com/questions/31210973/how-do-i-seed-a-mongo-database-using-docker-compose#answer-66729504 
- https://stackoverflow.com/questions/30063907/docker-compose-how-to-execute-multiple-commands#answer-30064175
- https://stackoverflow.com/questions/31210973/how-do-i-seed-a-mongo-database-using-docker-compose#33397913