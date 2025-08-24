# CineSeek — Movie Discovery App

## API Overview

CineSeek integrates with the **MoviesDatabase API** to fetch information on over 9 million titles, including movies, series, and episodes, as well as detailed cast and crew data :contentReference[oaicite:0]{index=0}. This API is accessed via RapidAPI and is central to powering our movie discovery features.

## API Version

The API version is not explicitly listed in the RapidAPI docs; however, it is currently the latest version hosted under the MoviesDatabase collection :contentReference[oaicite:1]{index=1}.

## Available Endpoints

**Endpoints available via the MoviesDatabase API:**

- `/titles`: Returns movie and TV series listings — supports pagination and filtering by year or genre :contentReference[oaicite:2]{index=2}.
- Additional endpoints (e.g., `/actors`, `/crew`): Provide access to casting and crew metadata :contentReference[oaicite:3]{index=3}.

## Request and Response Format

**Typical request structure:**

```http
POST https://moviesdatabase.p.rapidapi.com/titles
Content-Type: application/json
x-rapidapi-key: YOUR_API_KEY
{
  "genre": "Action",
  "year": 2022,
  "page": 1
}
```

## Example Response

{
"page": 2,
"results": [
{
"id": "tt1234567",
"title": "Action Movie",
"year": 2023,
"genre": ["Action", "Adventure"],
"rating": 7.8
}
]
}

## Authentication

To authenticate your requests, include the x-api-key header with your API key in each request. The API key is provided upon subscription to the MoviesDatabase API on RapidAPI.

## Error Handling

401 Unauthorized: Ensure that your x-api-key is included and valid.

404 Not Found: Verify that the requested resource exists.

429 Too Many Requests: Implement rate limiting in your application to avoid exceeding the API's usage limits.

Usage Limits and Best Practices
Rate Limit: The API has a rate limit of 1000 requests per hour.

Pagination: Use the page query parameter to paginate through large datasets.

Caching: Implement caching mechanisms to reduce the number of API calls and improve performance.

Secure API Key: Never expose your API key in client-side code; use server-side requests to keep your key safe.
