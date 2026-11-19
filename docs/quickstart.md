 Vacation Planner API Quickstart Guide

## Overview

The Vacation Planner API is a REST API designed to help travelers
plan future vacations and maintain a record of past trips.

Users can organize destinations, accommodations, dining options,
and activities in one place. The API also supports tracking
ratings from previous trips to help travelers make informed
decisions when planning future vacations.

The Vacation Planner API is intended for individual travelers
and boutique travel agencies.

### Key Features

- Create and organize vacation plans.
- Track past and upcoming trips.
- Research and save accommodations.
- Organize restaurants, bars, and other dining options.
- Add activities, tours, museums, and landmarks.
- Record ratings from previous travel experiences.

## Prerequisites

Before getting started, you should have:

- A basic understanding of REST APIs.
- Familiarity with JSON data.
- An API testing tool, such as Postman, or a terminal with cURL.
- Access to a running instance of the Vacation Planner API.

> **Note:** The API's base URL, authentication requirements,
> and deployment instructions have not yet been provided.
> Confirm these details with the API developer before
> making requests.

## API Resources

The Vacation Planner API organizes travel information into
four primary resources.

| Resource | Description |
|----------|-------------|
| `trip` | Stores vacation destinations, dates, and ratings. |
| `accomodation` | Stores lodging information associated with trips. |
| `dining` | Stores restaurants, bars, and other dining options. |
| `activity` | Stores attractions, tours, museums, and activities. |

> **Note:** The resource name `accomodation` is spelled
> with one "m" in the source database. This guide preserves
> that spelling to match the existing JSON structure.

## Retrieve Your First Trip

In this Quickstart, you'll retrieve an existing vacation
record and examine its JSON response.

### Step 1: Understand the Trip Resource

The `trip` resource stores basic information about a vacation,
including its destination, travel dates, and rating.

Each trip has a unique `id` that identifies the record.

For example, the Vacation Planner database contains
a trip to Paris, France, with an ID of `1`.

### Step 2: Send a GET Request

REST APIs commonly use GET requests to retrieve information.

The following example illustrates how to retrieve a trip
using its unique identifier.

**Example request:**

```http
GET /trip/1
```

**Example cURL command:**

```bash
curl -X GET "http://localhost:3000/trip/1"
```

> **Important:** The endpoint and base URL shown above
> are illustrative. They must be confirmed with the API
> developer before use.

### Step 3: Examine the JSON Response

The following record comes from the Vacation Planner
JSON database.

```json
{
  "country": "France",
  "city": "Paris",
  "startDate": "2022-06-01",
  "endDate": "2022-06-08",
  "rating": "4",
  "id": 1
}
```

The response contains the following information:

- `country`: France
- `city`: Paris
- `startDate`: June 1, 2022
- `endDate`: June 8, 2022
- `rating`: 4
- `id`: 1

### Step 4: Verify the Result

If the API implements the illustrated endpoint,
a successful request should return the record
associated with trip ID `1`.

Verify that the returned JSON contains:

- The destination Paris, France.
- The correct start and end dates.
- The trip's unique identifier.

If the API returns the expected record, you've
successfully retrieved your first vacation.

## Next Steps

Now that you understand how to retrieve a trip,
you can explore additional Vacation Planner resources.

Continue with the tutorials to learn how to:

1. Retrieve accommodations associated with a trip.
2. Explore restaurants and other dining options.
3. Find activities and attractions.
4. Build a complete vacation plan.
5. Create a new trip.

For detailed information about resource properties,
data types, and supported endpoints, consult the
API Reference documentation.