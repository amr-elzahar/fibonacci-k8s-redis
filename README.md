# Fibonacci Sequence

An application that calculates the value corresponding to a specific index in fibonacci series.

# Description

This is a full-stack application that consists of a React client, a Node.js server, a Postgres DB container, and a Redis container. The application allows users to input an index value for the Fibonacci series and receives back the corresponding value from either Redis. If the requested index already exists in Redis cache, the server returns its corresponding value from Redis. If not, it calculates its value using a helper function, inserts both the index and its value into the Postgres database for permanent storage, and saves them in Redis for in-memory caching. The init.sql file is script will run when the postgres container starts to create the database and the table.

# Installation

To install and run this application, you need to have Docker installed on your local machine. Once you have Docker installed, you can proceed with the following steps:

1. Clone this repository to your local machine.

```
git clone https://github.com/amr-elzahar/fibonacci-sequence.git
```

2. Navigate to the root directory of the project and open the terminal:

```
cd fibonacci-k8s-redis/
```

3. Run the command to build the images and start the containers:

```
kubectl create -f deployment
```

4. Run this command to access the React client application through your browser:

```
minikube service client
```

# Usage

Once you run the last command, the application will open automatically in you local browser. Now you can enter any index value in the text field and click on the "Calculate" button. After clicking on the "Calculate" button, you will see the corresponding value of the index in the Fibonacci series. Moreover, if the value already exists before in Redis cache, it will return in seconds. If not, it may take some time to calculate and store the value in Redis and Postgres for the first time.
