# Sample Implementation of Automated Test Using WireMock

## Local Mongo DB setup by container

docker volume create --name=mongodata

docker run --name mongodb -v mongodata:/data/db -d -p 27017:27017 mongo

Then access the container

docker exec -it mongodb bash

Then open the MongoDB terminal by

mongo


for more read https://blog.jeremylikness.com/blog/2018-12-27_mongodb-on-windows-in-minutes-with-docker/

## Overview
This repository provides a sample Spring Boot Application for the demonstration of WireMock Usage in Unit Test and Component Test.

It is a insurance product quotation API, it exposes an endpoint ``POST /quotations/generate`` and quotation generation.

![Application Component Diagram](blob/WireMock-Quotation_Service.png)


## Build

Run this command to build and run all automated tests

`mvn clean install`

If you would like to run the component test only, then run this command

`mvn -Dtest=CucumberTest test`

## Unit Test

Unit test demonstrates the testing on API client with API stub created using WireMock.

![Unit Test Diagram](blob/WireMock-Unit_Test.png)


## Component Test

Component test is a block box test, it submits requests to the quotation service and verify the outputs. All external API services are mocked using WireMock.

![Component Test Diagram](blob/WireMock-Component_Test.png)


