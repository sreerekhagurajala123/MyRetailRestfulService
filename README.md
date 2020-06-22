# ProjectTitle
myRetailRestfulService

## Getting Started
myRetailRestfulService is an implementation of restful API's for retrieving as well as inserting product details using GET and PUT methods. The GET method gives the product details like name and price information for a given product ID where as the PUT method updates the price information of the product.

The myRetailRestfulService talks to third party RESTful service to get the name of the product. The price information of the product is stored on the Cassandra repository.
myRetailRestfulService service is built on Spring Boot framework with dependencies including Maven for build and Mockito for testcases.

### Prerequisites:-
* [1] SpringBoot Tool suite or any IDE framework for ease of use.
* [2] Maven
* [3] Cassandra
* [4] PostMan is used as a client to access Restful webservices

### How to setup cassandra ?
1) Follow the steps given at https://www.datastax.com/2012/01/working-with-apache-cassandra-on-mac-os-x to install cassandra.
2) Run the below command after  starting the cassandra server will create the database schema and insert the data into cassanda database
    cqlsh -f database_creation.cql 
    
Note:database_creation.cql is present in the cassandra folder

### How to start webservices server ?
1) Before starting webservices server make sure that Cassandra is running on port number mentioned in the properties file
2) Run the below command to start the webservices server under the target folder

java -jar myretail-0.1.0.jar

### How to test the webservices using PostMan client ?

1) Test GET Webservice

In the postman client select the GET option and in the url section copy the below url
http://localhost:8080/products/14971529
and the response should be
{"productID":14971529,"productName":"Kitchen cleaner","priceInfo":{"currency":"IND","price":93.49}}

2) Test PUT Webservice

In the postman client select the PUT option and in the url section copy the below url
http://localhost:8080/products/14971529 and in the body section copy the below JSON 
{"priceInfo":{"price":99.9,"currency":"IND"}}
and the response should be
Given product with id 14971529 is successfully updated

### run the test cases
execute the below command in the root folder where pom.xml is present

mvn clean install

### skip running the test cases
execute the below command in the root folder where pom.xml is present

mvn clean install -DskipTests

### Screeenshots of the application
Please check the images folder for the application images

