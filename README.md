# Stream data store retrieval with mongodb
## **Problem/Task:** 

Implement a data pipeline to process streaming IoT data. Data is a sort of sensor reading for specific devices. The goal is to provide a simulation of these kinds of data pipelines to handle the incoming data and provide some APIs to get the average/median/max/min values of the reported metrics. 


### Implementation Overview

For this project, I have built a lightweight spring boot application that simulates an IoT data stream. It doesn't interact with real devices but instead generates random data to represent sensor readings.

In addition, I have implemented a separate mechanism for storing and retrieving specific metrics reported by different device types.

This project includes two main components: SensorDataProducer, and SensorDataService. 
The SensorDataProducer sends sensor data to a MongoDB Collection, and the SensorDataService class reads sensor data from the same collection using the MongoDB as a Data Pipeline Storage System. 

### Architecture

![image](https://github.com/adahiya31/spring-data-retrival-mongo/blob/main/img.png)

#Dependencies

•	MongoDB

•	Spring Boot

•	Spring Security 

•	Maven (Build and dependency tool)

•	Lombok 

•	JUnit (Sample Cases)

•	JWT Auth

# Installing MongoDB on a Docker Container Locally

1. Install Docker Desktop on your local machine
2. Ensure Docker Desktop is installed and running.
3. Open a terminal and run:

`
docker pull mongo
`

4. Start a MongoDB container:
   
`
docker run -d -p 27017:27017 --name mongodb mongo
`

5.  MongoDB is now running on `localhost:27017`.



### Building and Running the Project

To build and run this project, follow these steps:

1.	Clone the current Github repo.
2.	Install and run an instance of the MongoDB on a specific port or 27017.
3.	Install oracle JDK 21 on your local machine.
4.	Update the application.properties file to specify the MongoDB i.e DB name and port it is  running on.
5.    Testing the REST APIs
      
### To test the REST APIs, follow these steps:

*Option 1*
1. Import Postman collection.

*Option 2*
(to Check JWT functionality)
1.	Get the JWT token.
2.	Pass the JWT token in the Authorization header of each request.
   
 **Pass token in each request header**

#### Get Token by this call:
`
curl --location 'localhost:8080/authenticate' \
--header 'Content-Type: application/json' \
--data '{
    "username": "admin",
    "password": "admin"
}'
`

### Final tips
#### Application Flow:
1. Install and Configure the Docker and MongoDB.
2. Apply Configurations (in application.properties).
3. Setup your workspace and resolve imports error.
4. Make sure that all Maven dependencies are imported correctly.
5. Build and run as spring boot application.
6. Test using postman collection.

```
db.sensorDataDTO.createIndex( { SensorName: "text", ReportTimestamp: -1 } )
```

#### Default Username & Password:

```
Username: admin
Password: admin
```
