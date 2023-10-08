# Magneconn API
#

<div align="center">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/go/go-original.svg" height="200" alt="go logo"  />
</div>

###

## Project structure:

```go
.
├── api
│   ├── handlers.go
│   └── health
│       └── health.go
├── core
│   ├── core.go
│   ├── models.go
│   ├── parser.go
│   └── structurizer.go
├── db
│   ├── db.go
│   └── models.go
├── go.mod
├── go.sum
├── LICENSE
├── main.go
├── README.md
└── vars
    └── vars.go
```

## API docs

- This readme file provides an overview and documentation for the magneconn_api application's RESTful API, 
  focusing on the package handlers

- The API provides access to various space weather data retrieval endpoints:

### Endpoints:

1. GET /api/health
	- Description: check the health of the API
	- Response:
		- Status Code: 200 OK
		- Content-Type: application/json 
- Example:
```http
GET /api/health
```

2. GET /api/dst/last-month
	- Description: Retrieve space weather data for the last month's Dst index
	- Response:
		- Status Code: 200 OK
		- Content-Type: application/json
- Example:
```http
GET /api/dst/last-month
```

3. GET /api/dst/current-month
	- Description: Retrieve space weather data for the current month's Dst index
	- Response:
		- Status Code: 200 OK
		- Content-Type: application/json
- Example:
```http
GET /api/dst/current-month
```

4. GET /api/dst/by-date
	- Description: Retrieve space weather data for a specific date's Dst index
		- Query Parameters:
			- date (string): The date in YYYYMM format
	- Response:
		- Status Code: 200 OK
		- Content-Type: application/json
- Example:
```http
GET /api/dst/by-date?date=202301
```

5. GET /api/dst/avg/6h
	- Description: Calculate and retrieve the average Dst index for the last six hours
	- Response:
		- Status Code: 200 OK
		- Content-Type: application/json
- Example:
```http
GET /api/dst/avg/6h
```

6. GET /api/bz/6h
	- Description: Retrieve real-time solar wind data for the last six hours
	- Response:
	    - Status Code: 200 OK
	    - Content-Type: application/json
- Example:
```http
GET /api/bz/6h
```
- Error Responses
    - Status Code: 400 Bad Request
    - Content-Type: application/json

- Example Error Response:
```json
{
  "error": "date parameter is missing!"
}
```

```json
{
  "error": "Invalid date format"
}
```

### CORS Configuration

- The API is configured to allow Cross-Origin Resource Sharing (CORS) by using the github.com/gin-contrib/cors middleware, enabling access to the API from different domains

- The API will be available at https://somesite.xyz. Make requests to the defined endpoints to access space weather data

- Please ensure that the appropriate URL is used along with any required query parameters when making requests to the API endpoints

## Contributing

- Pull requests are welcome, for major changes, please open an issue first to
  discuss what you would like to change

## License

- [MIT](https://choosealicense.com/licenses/mit/)
