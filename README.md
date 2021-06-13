# Covid-tracker
# Covid Tracker 
# Covid Tracker 

this  a MERN app created to track covid data in the World and more specifically in Morocco
## Installation

First all you need to have node.js installed , then after acceding to the project terminal execute the following commands:
### Back-end

```bash
cd back-end
npm install
npm start 
```
### Front-end

```bash
cd frontend
npm install
npm start 
```

## Dockerize the application
 1. Create two Dockerfile one inside front-end folder and the second inside back-end
 ### Front-end configuration
1.1 Front-end file
```bash

# Dockerfile for React client

# Build react client
FROM node:10.16-alpine

# Working directory be app
WORKDIR /usr/src/app

COPY package*.json ./

###  Installing dependencies

RUN npm install --silent

# copy local files to app folder
COPY . .

EXPOSE 3000

CMD ["npm","start"]

```
1.2 Back-end file 

```bash
#  Dockerfile for Node Express Backend

FROM node:10.16-alpine

# Create App Directory
RUN mkdir -p /usr/src/app
WORKDIR /usr/src/app

# Install Dependencies
COPY package*.json ./

RUN npm install --silent

# Copy app source code
COPY . .

# Exports
EXPOSE 8000

CMD ["npm","start"]

```
2.build an image 

```bash
 docker build -t react-app 
docker run -p 3000:3000 react-app

```
### Back-end configuration
3.build image
```bash
docker build -t node-app 

```
For more details visit this Link : 

https://medium.com/mozilla-club-bbsr/dockerizing-a-mern-stack-web-application-ebf78babf136
