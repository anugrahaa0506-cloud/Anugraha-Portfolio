# OpenWeatherMap API — Getting Started Guide

**Version:** 2.5  
**Last Updated:** April 2026  
**Audience:** Developers integrating weather data into applications

---

## Overview

The OpenWeatherMap API provides real-time weather data, forecasts, and historical weather information for any location in the world. This guide walks you through setting up your account, authenticating your requests, and making your first API call.

---

## Prerequisites

Before you begin, make sure you have:

- A free OpenWeatherMap account (sign up at [openweathermap.org](https://openweathermap.org))
- Basic familiarity with REST APIs and HTTP requests
- A tool for making API calls (curl, Postman, or your preferred programming language)

---

## Step 1: Get your API key

1. Log in to your OpenWeatherMap account.
2. Navigate to **API Keys** in your account dashboard.
3. Copy the default API key, or click **Generate** to create a new one.

> **Note:** New API keys can take up to 2 hours to activate. If you receive a `401 Unauthorized` error immediately after generating a key, wait and try again.

---

## Step 2: Make your first request

The base URL for all API calls is:

```
https://api.openweathermap.org/data/2.5/
```

### Request format

```
GET https://api.openweathermap.org/data/2.5/{endpoint}?{parameters}&appid={YOUR_API_KEY}
```

Your API key is passed as the `appid` query parameter in every request.

### Example: Get current weather for a city

```
GET https://api.openweathermap.org/data/2.5/weather?q=London&appid=YOUR_API_KEY&units=metric
```

This returns the current weather conditions for London, with temperature values in Celsius.

---

## Step 3: Understand the response

A successful request returns a JSON object. Here is a sample response for the request above:

```json
{
  "name": "London",
  "sys": {
    "country": "GB"
  },
  "weather": [
    {
      "id": 803,
      "main": "Clouds",
      "description": "broken clouds",
      "icon": "04d"
    }
  ],
  "main": {
    "temp": 14.2,
    "feels_like": 13.1,
    "temp_min": 12.8,
    "temp_max": 15.6,
    "humidity": 72,
    "pressure": 1012
  },
  "wind": {
    "speed": 5.1,
    "deg": 230
  },
  "visibility": 10000,
  "dt": 1712505600,
  "cod": 200
}
```

### Key response fields

| Field | Type | Description |
|-------|------|-------------|
| `name` | string | City name |
| `sys.country` | string | Country code (ISO 3166) |
| `weather[0].main` | string | Short weather condition (e.g., Rain, Clouds, Clear) |
| `weather[0].description` | string | Detailed weather description |
| `main.temp` | number | Current temperature in the requested unit |
| `main.feels_like` | number | Perceived temperature |
| `main.humidity` | number | Humidity percentage |
| `wind.speed` | number | Wind speed in metres/sec (or mph if `units=imperial`) |
| `visibility` | number | Visibility in metres (max 10,000) |
| `dt` | integer | Time of data calculation, Unix UTC timestamp |
| `cod` | integer | HTTP status code of the response |

---

## Endpoint Reference

### Current Weather

Retrieves current weather conditions for a specified location.

```
GET /data/2.5/weather
```

**Query parameters:**

| Parameter | Required | Type | Description |
|-----------|----------|------|-------------|
| `q` | Yes* | string | City name. Format: `city`, `city,country_code`. Example: `Paris,FR` |
| `lat` | Yes* | number | Latitude coordinate. Use with `lon`. |
| `lon` | Yes* | number | Longitude coordinate. Use with `lat`. |
| `id` | Yes* | integer | OpenWeatherMap city ID. |
| `zip` | Yes* | string | ZIP code. Format: `zip,country_code`. Example: `10001,US` |
| `appid` | Yes | string | Your API key. |
| `units` | No | string | Unit system. Options: `standard` (default), `metric`, `imperial` |
| `lang` | No | string | Language for the weather description. Default: `en`. See [supported languages](https://openweathermap.org/current#multi). |

> **Note:** At least one location parameter (`q`, `lat`+`lon`, `id`, or `zip`) is required.

**Example request by coordinates:**

```
GET https://api.openweathermap.org/data/2.5/weather?lat=48.8566&lon=2.3522&appid=YOUR_API_KEY&units=metric
```

---

### 5-Day Forecast

Returns weather forecast data in 3-hour intervals for the next 5 days.

```
GET /data/2.5/forecast
```

**Query parameters:**

Same location parameters as the Current Weather endpoint, plus:

| Parameter | Required | Type | Description |
|-----------|----------|------|-------------|
| `cnt` | No | integer | Number of timestamps to return. Default returns all available (up to 40). |

**Example request:**

```
GET https://api.openweathermap.org/data/2.5/forecast?q=Tokyo&cnt=8&appid=YOUR_API_KEY&units=metric
```

This returns the next 8 forecast entries (24 hours) for Tokyo in Celsius.

---

## Units of Measurement

| Unit system | Parameter value | Temperature | Wind speed |
|-------------|----------------|-------------|------------|
| Standard (default) | `standard` | Kelvin (K) | metres/sec |
| Metric | `metric` | Celsius (°C) | metres/sec |
| Imperial | `imperial` | Fahrenheit (°F) | miles/hour |

---

## Error Responses

The API returns standard HTTP status codes along with a JSON error body.

| Code | Message | Meaning |
|------|---------|---------|
| `400` | Bad Request | Missing or invalid parameters. Check your request format. |
| `401` | Unauthorized | Invalid or inactive API key. Verify your `appid` value. |
| `404` | Not Found | Location not found. Try a different city name format or use coordinates instead. |
| `429` | Too Many Requests | You have exceeded the rate limit for your subscription plan. |
| `500` | Internal Server Error | Server-side issue. Wait and retry. |

**Example error response:**

```json
{
  "cod": "404",
  "message": "city not found"
}
```

---

## Rate Limits

| Plan | Calls per minute | Calls per day |
|------|-----------------|---------------|
| Free | 60 | 1,000 |
| Startup | 600 | 10,000 |
| Developer | 3,000 | 100,000 |

If you exceed your rate limit, the API returns a `429` status code. Consider caching responses on your end to reduce unnecessary repeated calls.

---

## Next Steps

- Explore the [Air Pollution API](https://openweathermap.org/api/air-pollution) for CO2 and particulate data
- Use the [Geocoding API](https://openweathermap.org/api/geocoding-api) to convert city names to coordinates
- Review the full [API documentation](https://openweathermap.org/api) on the OpenWeatherMap website

---

*This document is a sample technical writing portfolio piece by Anugraha S, written using publicly available API documentation as reference.*
