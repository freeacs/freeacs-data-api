# data-api

For now only used by
https://github.com/freeacs/freeacs-web

# Setup
1. git clone `git@github.com:freeacs/freeacs-data-api.git`
2. cd freeacs-data-api
3. git submodule init
4. git submodule update
5. mvn install

# Run api project
1. cd data-api
2. mvn spring-boot:run
3. Now accessible on http://localhost:9000/rest

# Authorization
1. Send a POST request to http://localhost:9000/rest/user/signin with body `{ "username": "admin", "password": "freeacs"  }`
2. You get a response with like this `{ "username": "admin", "token": "[the jwt token]" }`
3. Save the token somewhere
4. For each subsequent requests to the server, set a header `Authorization: Bearer [the jwt token]`
5. Call http://localhost:9000/rest/user/me to get current logged in users info
