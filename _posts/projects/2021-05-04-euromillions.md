---
title: "Euromillions API"
excerpt: "A simple API to retrieve Euromillions lottery draws."
categories:
  - projects
tags:
  - euromillions
header:
  overlay_image: /assets/images/posts/euromillions/euromillionsHeader.webp
---

## What is Euromillions API?
It's a free API that can be used to retrieve the Euromillions lottery numbers for a specified day, year or even every lottery draw since the lottery's launch year (2004).

## Tech used
The API was coded in ASP.NET Core and is hosted on an Ubuntu server running nginx.
The results are obtained via a custom scraper that runs every Tuesday and Friday - the days at which the lottery is drawn - and then uploaded to an SQLite database using the API's database management endpoint.

## Request example
Making a request to the API is really simple.
The following example shows how you can retrieve a lottery draw for a specific date - in this case 30-04-2021.

### Request
```shell
curl -X 'GET' \
  'https://euromillions.telmoduarte.me/api/results/30-04-2021' \
  -H 'accept: application/json'
```

### Response
```json
{
  "date": "30-04-2021",
  "numbers": [
    1,
    16,
    24,
    28,
    46
  ],
  "stars": [
    2,
    11
  ],
  "resultPrettified": "1 16 24 28 46 + 2 11"
}
```
The response is returned as json with organized information, you can get individual numbers and stars or just the prettified result if you don't want to do extra formatting.

## Check it yourself
Feel free to check and test the API. It is available [here](https://euromillions.telmoduarte.me/).