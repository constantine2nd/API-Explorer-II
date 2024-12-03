Welcome to the OBP API Explorer II
=================================

# ABOUT

This application is used to explore OBP APIs and interact with the data and services in the context of the logged in user.

This application will gradually replace the original API Explorer. Long live the API Explorer!



## Install the Prerequisite Software
  * required: { node: `>=16.14` }
  * required: { npm: `>=8.0.0` }

### Development Project Setup

  * Setup your .env file (see .env.example)

##### Install dependencies

```sh
yarn install
```
or
```sh
npm install
```

##### Compile and Hot-Reload for Development

```sh
yarn dev
```
or
```sh
npm run dev
```

##### Get a Consumer Key for the OBP-API

API Explorer needs a Consumer Key / Secret to access the Open Bank Project API with OAuth.
To get this Consumer, go to the Portal of OBP-API, login and "Get a Consumer Key".
The callback URL (if running locally) should be http://localhost:5173/api/callback
Copy and paste the Consumer Key and Consumer Secret and add it to your .env file here.
You can use .env.example as a basis of your .env file. 



##### ~~Run Unit Tests with [Vitest](https://vitest.dev/)~~

<strike>

```sh
yarn test:unit
```
</strike>

or
<strike>

```sh
npm test:unit
```
</strike>

## Compile and Minify for Production

##### Build 

```sh
npm run build
```

##### Build Server 

```sh
npm run build-server
```



##### Start the backend server
```sh
npx ts-node <path-to-your-install>/server/app.js
```

##### Check the status of API-Explorer II back-end
```
Please find a message at a log file similar to this one:

Backend is running. You can check a status at http://localhost:8085/api/status

and use the link to check the status
```


##### Nginx deployment

```config
server {
    # Frontend
    location / {
        root    /path_to_dist/dist;
        try_files $uri $uri/ /index.html;
    }
    
    # Proxy API
    location /api {
        proxy_pass http://localhost:8085;
    }
}
```

# LICENSE

This project is licensed under the AGPL V3 (see NOTICE) and a commercial license from TESOBE.

