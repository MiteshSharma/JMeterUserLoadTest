# JMeter User Load Test

Creating a JMeter test plan with a thread group which can run CRUD operations on user resource at a given server. Each creates operations need to have different email address randomly generated before sending the request. Fetch authentication token and user id provided a response to create user request. An authentication token is used as the header in all subsequent requests and user id in URL and body parameter as needed. Finally, have a view result tree listener where we can see all requests with their responses.

Step 1: Add a Thread Group to our test plan

Step 2: Add an HTTP request defaults using the config elements to define default parameters like hostname and port of server needed for all requests.

Step 3: Add an HTTP request sampler to send Create user request

Step 4: Add a BeanShell pre-processor to generate a random email address for creating user request.

Step 5: Add a JSON extractor post-processor to get authentication token and userId from the response of creating user request.

Step 6: Add an HTTP header manager to add authentication token as the header to all subsequent requests.

Step 7: Add Update user, get user and delete user HTTP request sampler for subsequent requests with userId as dynamic variable fetched from creating user post-processor.

Step 8: Add View result tree to get the response to all requests.

Using JMeter version : 5.0
