# RestFul_Web_Service_SpringBoot_Project
Created the backend for a mini messaging service, inspired by Twitter.

RESTful API where all endpoints require HTTP Basic authentication and generate output in JSON format. Implement the the following basic functionality:

`RESTful API where all endpoints require HTTP Basic authentication and generate output in JSON format`

`An endpoint to read the message list for the current user (as identified by their HTTP Basic authentication credentials). Include messages they have sent and messages sent by users they follow. Support a “search=” parameter that can be used to further filter messages based on keyword.`

`Endpoints to get the list of people the user is following as well as the followers of the user.`

`An endpoint to start following another user.`

`An endpoint to unfollow another user.`

`An endpoint that returns the current user's "shortest distance" to some other user. The shortest distance is defined as the number of hops needed to reach a user through the users you are following (not through your followers; direction matters). For example, if you follow user B, your shortest distance to B is 1. If you do not follow user B, but you do follow user C who follows user B, your shortest distance to B is 2.` 


Used: Spring Boot, H2 in Memory SQL Database
---
To test this API in postmen we have to select Authorization Type as "Basic Auth" and enter username and password. Here username is the id of the existing user and password is "password". Existing user_id[1,2,...,10]. If we enter wrong password then Endpoints will not work.
> username: 1 [id of the user]

> password: password

---
http://localhost:8080/user

Method: Get

Description: First, it fetch current user id from HTTP header. Then it will return list of messages of the current user. Include messages they have sent and messages sent by users they follow.

---
http://localhost:8080/user?search=ut

Method: Get

Desciption: Support a “search=” parameter that can be used to further filter messages based on keyword.

---
http://localhost:8080/user/connections

Method: Get

Description: It fetch current user id from HTTP header. Then it will return the list of people the current user is following as well as the followers of the user.

---
http://localhost:8080/user/follow?uid=2

Method: Put

Description: It fetch current user id from HTTP header and 2 is another user id. So here current user start following another user whose id 2. 

---
http://localhost:8080/user/unfollow?uid=2

Method: Delete

Description: It fetch current user id from HTTP header and 2 is another user id. So here current user unfollow another user whose id 2. 

---
http://localhost:8080/user/distance?uid=6

Method: Get

Description: Return distance between current user and another user whose id is 6.
