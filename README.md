![Alt text](map.jpg)

# St. Paul Crime RESTful-API

This RESTful-API was created to query St. Paul Crime data that was collected and released by the St. Paul Police Department. The main focus of this API is to effectively sort through data in efficient and useful ways to allow effective and accurate deductions to be made from the data. These deductions can help visualize and discover trends and observations that can result in change of approach to crime in the St. Paul area.  

The main tools used to develop this API include JavaScript, Node, SQLite and Excel. 

---

See it in action online by clicking [here](https://tuck1297.github.io/Vue-Single-Page-St.-Paul-Crime/)!!!

There are three paths that the RESTful-API can be queried by: 

- Codes: 
  1. Code (INTEGER) - crime incident type numeric code
  2. incident_type (TEXT) - crime incident type description
- Neighborhoods:
  1. neighborhood_number (INTEGER) - neighborhood id
  2. neightborhood_name (TEXT) - neighborhood name
- Incidents: 
  1. case_number (TEXT): unique id from crime case
  2. date_time (DATETIME): date and time when incident took place
  3. code (INTEGER): crime incident type numeric code
  4. incident (TEXT): crime incident description (more specific than incident_type)
  5. police_grid (INTEGER): police grid number where incident occurred
  6. neighborhood_number (INTEGER): neighborhood id where incident occurred
  7. block (TEXT): approximate address where incident occurred

- Neighborhoods can be queried by the following: id (INTEGER)
- Codes can be queried by the following: code (INTEGER)
- Incidents can be queried by the following: 
   - start_date=yyyy-mm-dd (DATE)
   - end_date=yyyy-mm-dd (DATE)
   - code (INTEGER)
   - grid (INTEGER)
   - neighborhood (INTEGER)
   - limit (INTEGER)

- Example CMD Operation: 
   ```
   curl -X GET "http://localhost:8000/incidents?grid=5&limit=5"
   ```
---

In addition to these paths, there was also functionality added where new incidents can be added and current incidents 
can be deleted. NOTE: These operations have been disabled on the hosted version of this project. To try the delete and put functionalty this project will need to be hosted and run in your local development environment. 

- Example CURL CMD Operation: 
   ```
   curl -X DELETE "http://localhost:8000/remove-incident" -H "Content-Type: application/json" -d "{\"case_number\": 5}"
   ```
   ```
   curl -X PUT "http://localhost:8000/new-incident" -H "Content-Type: application/json" -d "{\"case_number\": \"19245014\", \"date\": \"2019-10-30\",\"time\": \"23:43:19\",\"code\": 700,\"incident\": \"Auto Theft\",\"police_grid\": 95,\"neighborhood_number\": 4,\"block\": \"79X 6 ST E\"}"
   ```
---

# Plug and Play

To use this project you will need to do the following: 

1. Clone this project into your personal integrated development environment (IDE)
2. If you have not already, install [Node](https://nodejs.org/en) to run in your (IDE)
3. Navigate to the file directory that holds this project in your IDE
4. Install project dependencies by typing the following in the terminal: 

```npm install```

5. Run the project by typing the following in the terminal: 

``` Node server.js```

You should then see the following in the terminal: 

``` 
   Now listening on port 8000
   Now connected to stpaul_crime.sqlite3
```

You can query by CMD using curl or for get requests by the browser by going to localhost on port 8000. 

There is also the following online tool for querying: [Webtools](https://www.webtools.services/online-rest-api-client). 
If you use this online tool make sure you use localhost with port 8000 as your testing url. 

## VueJS User Interface

You can see the VueJS User Interface that was created alongside this RESTful-API server in this Repo: [Github Repository](https://github.com/tuck1297/crime-vuejs-ui/).

## Languages and Tools Used
<div>
  <img src="https://github.com/devicons/devicon/blob/master/icons/css3/css3-plain-wordmark.svg"  title="CSS3" alt="CSS" width="60" height="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/html5/html5-original.svg" title="HTML5" alt="HTML" width="60" height="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/javascript/javascript-original.svg" title="JavaScript" alt="JavaScript" width="60" height="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/sqlite/sqlite-original-wordmark.svg" title="SQLite"  alt="SQLite" width="60" height="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/nodejs/nodejs-original-wordmark.svg" title="NodeJS" alt="NodeJS" width="60" height="60"/>&nbsp;
  <img src="https://github.com/devicons/devicon/blob/master/icons/git/git-original-wordmark.svg" title="Git" **alt="Git" width="40" height="60"/>
  <img src="https://github.com/devicons/devicon/blob/master/icons/github/github-original.svg" title="Github" **alt="Github" width="60" height="60"/>
  <img src="https://github.com/devicons/devicon/blob/master/icons/vscode/vscode-original.svg" title="vscode" **alt="vscode" width="60" height="60"/>
</div>
