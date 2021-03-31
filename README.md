## Student: Louis Manabat
**ID: s3719633**

### Analysis of the problem (What are you actually trying to solve) (5%)
There is a lack of automation in terms of testing, building and deploying the solution. Factors such as bug-fixes and adding new features to production, should have an automated process to reduce the unnecessary manual workload needed on several teams in the company.

### Explain and Justify the solution (How does the solution work) (10%)
The solution runs code testing by both checking the functionality of the code (via pre-written unit testing) and the structuring of the code (style/formatting). They will be checked to make sure the it is up to standard prior to deployment. Integration testing between the MongoDB database and the application will be ran to ensure that there aren't any errors when doing tasks such as registering a new user or logging in. A secuity check will be ran during any CI run in the pipeline, to ensure there are no vulnerabilities in the application. Assuming the application does have a security risk, it will kill the pipeline completely. This means that the solution cannot be deployed in its currrent state, and will need to be checked for what the security error is, and potentially replace such modules with with an alternative in the event that does happen. Once all the above has been completed, it will be pulled into the master branch (by at this point, should've passed all the testing in the other branches), where it will pack the application and get it ready for deployment.

# Simple Todo App with MongoDB, Express.js and Node.js
The ToDo app uses the following technologies and javascript libraries:
* MongoDB
* Express.js
* Node.js
* express-handlebars
* method-override
* connect-flash
* express-session
* mongoose
* bcryptjs
* passport
* docker & docker-compose

## What are the features?
You can register with your email address, and you can create ToDo items. You can list ToDos, edit and delete them. 

# How to use
First install the depdencies by running the following from the root directory:

```
npm install --prefix src/
```

To run this application locally you need to have an insatnce of MongoDB running. A docker-compose file has been provided in the root director that will run an insatnce of MongoDB in docker. TO start the MongoDB from the root direction run the following command:

```
docker-compose up -d
```

Then to start the application issue the following command from the root directory:
```
npm run start --prefix src/
```

The application can then be accessed through the browser of your choise on the following:

```
localhost:5000
```

## Testing

Basic testing has been included as part of this application. This includes unit testing (Models Only), Integration Testing & E2E Testing.

### Linting:
Basic Linting is performed across the code base. To run linting, execute the following commands from the root directory:

```
npm run test-lint --prefix src/
```

### Unit Testing
Unit Tetsing is performed on the models for each object stored in MongoDB, they will vdaliate the model and ensure that required data is entered. To execute unit testing execute the following commands from the root directory:

```
npm run test-unit --prefix src/
```

### Integration Testing
Integration testing is included to ensure the applicaiton can talk to the MongoDB Backend and create a user, redirect to the correct page, login as a user and register a new task. 

Note: MongoDB needs to be running locally for testing to work (This can be done by spinning up the mongodb docker container).

To perform integration testing execute the following commands from the root directory:

```
npm run test-integration --prefix src/
```

### E2E Tests
E2E Tests are included to ensure that the website operates as it should from the users perspective. E2E Tests are executed in docker containers. To run E2E Tests execute the following commands:

```
chmod +x scripts/e2e-ci.sh
./scripts/e2e-ci.sh
```


###### This project is licensed under the MIT Open Source License