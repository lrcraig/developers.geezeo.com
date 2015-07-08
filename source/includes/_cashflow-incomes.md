# Cashflow Incomes

## Get Cashflow Incomes

```shell
curl -X "GET" "http://geezeo.dev:3000/api/v2/users/:user_id:/cashflow/incomes" -u "%geezeo-api-key%:"
```

```ruby
uri = URI('https://geezeobkdemo.mybankhq.com/api/v2/users/:user_id:/cashflow/incomes')
key = ':geezeo-aip-key:'

Net::HTTP.start(uri.host, uri.port,
  :use_ssl => uri.scheme == 'https') do |http|

  request = Net::HTTP::Get.new uri.request_uri
  request.basic_auth key,''

  response = http.request request

  puts response.body
end
```

> Response payload

```json
{
  "incomes": [
    {
      "id": 387,
      "amount": "-100.0",
      "frequency": "Every other week",
      "name": "Paycheck",
      "start_date": "2013-07-16",
      "stopped_on": "2013-07-17"
    }
  ]
}
```

Return a list of all cashflow incomes defined for a user.

`GET /api/v2/users/:user_id:/cashflow/incomes`

### Frequency
Frequency will be one of the values defined below.

| Frequency | | |
| --------- |-----|-----|
|`Daily`|`Every four weeks`|`Every other week`|
|`Every six months`| `Monthly`| `Once`| 
|`Quarterly`| `Twice a month`| `Weekly`|
|`Yearly`|


### Status Codes

| Status | Description |
|--------|-------------|
| 200 OK | returned when successful |
| 401 Not Authorized | returned when invalid credentials are provided |
| 404 Not Found | returned when an invalid user is specified |

## Get Cashflow Income

```shell
curl -X "GET" "http://geezeo.dev:3000/api/v2/users/:user_id:/cashflow/bills/:cashflow_income_id:" -u "%geezeo-api-key%:"
```

```ruby
uri = URI('https://geezeobkdemo.mybankhq.com/api/v2/users/:user_id:/cashflow/bills/:cashflow_income_id:')
key = ':geezeo-aip-key:'

Net::HTTP.start(uri.host, uri.port,
  :use_ssl => uri.scheme == 'https') do |http|

  request = Net::HTTP::Get.new uri.request_uri
  request.basic_auth key,''

  response = http.request request

  puts response.body
end

```

> Response payload

```json
{
  "incomes": [
    {
      "id": 387,
      "amount": "-100.0",
      "frequency": "Every other week",
      "name": "Paycheck",
      "start_date": "2013-07-16",
      "stopped_on": "2013-07-17"
    }
  ]
}
```


Return complete information for a cashflow income.

`GET /api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:`


### Frequency
Frequency will be one of the values defined below.

| Frequency | | |
| --------- |-----|-----|
|`Daily`|`Every four weeks`|`Every other week`|
|`Every six months`| `Monthly`| `Once`| 
|`Quarterly`| `Twice a month`| `Weekly`|
|`Yearly`|

### Status Codes

| Status | Description |
|--------|-------------|
| `200 OK` | returned when successful |
| `401 Not Authorized` | returned when invalid credentials are provided |
| `404 Not Found` | returned when an invalid user or income is specified |


## Create Cashflow Income

```shell
curl -X "POST" "http://geezeo.dev:3000/api/v2/users/:user_id:/cashflow/incomes" -u "%geezeo-api-key%:" -d ":request_payload:"
```

```ruby
uri = URI('https://geezeobkdemo.mybankhq.com/api/v2/users/:user_id:/cashflow/incomes')
key = ':geezeo-aip-key:'

Net::HTTP.start(uri.host, uri.port,
  :use_ssl => uri.scheme == 'https') do |http|

  request = Net::HTTP::Get.new uri.request_uri
  request.basic_auth key,''
  request.body = :request_payload:

  response = http.request request

  puts response.body
end

```


> Request payload

```json
{
  "income": {
    "amount": 100.0,
    "frequency": "Every other week",
    "name": "Paycheck",
    "start_date": "2013-07-17"
  }
}
```

> Response payload

```json
{
  "incomes": [
    {
      "id": 387,
      "amount": "-100.0",
      "frequency": "Every other week",
      "name": "Paycheck",
      "start_date": "2013-07-17",
      "stopped_on": null
    }
  ]
}
```


Create a new cashflow income.

`POST /api/v2/users/:user_id:/cashflow/incomes`


### Parameters

| Parameter | Description |
|-----------|-------------|
| `amount` | The bill's amount. If positive, it will be converted to a negative number. __Required__ |
| `frequency` | How often the bill recurs. __Required__ |
| `name` | The bill's payee. __Required__ |
| `start_date` | The bill's start date, in ISO-8601 format. __Required__ |


### Frequency
Frequency will be one of the values defined below.

| Frequency | | |
| --------- |-----|-----|
|`Daily`|`Every four weeks`|`Every other week`|
|`Every six months`| `Monthly`| `Once`| 
|`Quarterly`| `Twice a month`| `Weekly`|
|`Yearly`|


### Status Codes

| Status | Description |
|--------|-------------|
| `201 Created` | returned when successful |
| `401 Not Authorized` | returned when invalid credentials are provided |
| `404 Not Found` | returned when an invalid user is specified |
| `422 Unprocessable Entity` | returned when the parameters given were invalid |



## Update Cashflow Income

```shell
curl -X "PUT" "http://geezeo.dev:3000/api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:" -u "%geezeo-api-key%:" -d ":request_payload:"
```

```ruby
uri = URI('https://geezeobkdemo.mybankhq.com/api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:')
key = ':geezeo-aip-key:'

Net::HTTP.start(uri.host, uri.port,
  :use_ssl => uri.scheme == 'https') do |http|

  request = Net::HTTP::Put.new uri.request_uri
  request.basic_auth key,''
  request.body = :request_payload:

  response = http.request request

  puts response.body
end

```

> Request payload

```json
{
  "income": {
    "amount": -100.0,
    "frequency": "Every other week",
    "name": "Paycheck",
    "start_date": "2013-07-17"
  }
}
```

Update an existing cashflow income.

`PUT /api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:`


### Parameters

| Parameter | Description |
|-----------|-------------|
| `amount` | The bill's amount. If positive, it will be converted to a negative number. __Required__ |
| `frequency` | How often the bill recurs.  __Required__ |
| `name` | The bill's payee. __Required__ |
| `start_date` | The bill's start date, in ISO-8601 format. __Required__ |

### Frequency
Frequency will be one of the values defined below.

| Frequency | | |
| --------- |-----|-----|
|`Daily`|`Every four weeks`|`Every other week`|
|`Every six months`| `Monthly`| `Once`| 
|`Quarterly`| `Twice a month`| `Weekly`|
|`Yearly`|


### Status Codes

| Status | Description |
|--------|-------------|
| 204 No Content | returned when successful |
| 401 Not Authorized | returned when invalid credentials are provided |
| 404 Not Found | returned when an invalid user or income is specified |
| 422 Unprocessable Entity | returned when the parameters given were invalid |


## Stop Cashflow Income

```shell
curl -X "PUT" "http://geezeo.dev:3000/api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:/stop" -u "%geezeo-api-key%:" 
```

```ruby
uri = URI('https://geezeobkdemo.mybankhq.com/api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:/stop')
key = ':geezeo-aip-key:'

Net::HTTP.start(uri.host, uri.port,
  :use_ssl => uri.scheme == 'https') do |http|

  request = Net::HTTP::Put.new uri.request_uri
  request.basic_auth key,''

  response = http.request request

  puts response.body
end

```

Stop a cashflow income.

`PUT /api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:/stop`

### Status Codes

| Status | Description |
|--------|-------------|
| 204 No Content | returned when successful |
| 401 Not Authorized | returned when invalid credentials are provided |
| 404 Not Found | returned when an invalid user or income is specified |


## Delete Cashflow Income

```shell
curl -X "DELETE" "http://geezeo.dev:3000/api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:" -u "%geezeo-api-key%:" 
```

```ruby
uri = URI('https://geezeobkdemo.mybankhq.com/api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:')
key = ':geezeo-aip-key:'

Net::HTTP.start(uri.host, uri.port,
  :use_ssl => uri.scheme == 'https') do |http|

  request = Net::HTTP::Delete.new uri.request_uri
  request.basic_auth key,''

  response = http.request request

  puts response.body
end

```


Delete a cashflow income.

`DELETE /api/v2/users/:user_id:/cashflow/incomes/:cashflow_income_id:`

### Status Codes

| Status | Description |
|--------|-------------|
| 204 No Content | returned when successful |
| 401 Not Authorized | returned when invalid credentials are provided |
| 404 Not Found | returned when an invalid user or income is specified |
