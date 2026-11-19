# Vacation Planner API Tutorials

## Overview

These tutorials demonstrate how to use the Vacation Planner
API to organize accommodations, dining options, activities,
and vacation plans.

Before beginning, complete the
[Quickstart Guide](quickstart.md).

The tutorials use sample records from the Vacation Planner
JSON database.

> **Note:** The API endpoints and base URL in these
> tutorials are illustrative. Confirm their implementation
> with the API developer before running requests.

---

# Tutorial 1: Retrieve Accommodations for a Trip

## Objective

Learn how to retrieve accommodation information and
identify which accommodations belong to a specific trip.

## Step 1: Understand the Accommodation Resource

The `accomodation` resource stores lodging information
associated with vacation destinations.

Each accommodation contains a `tripId` property that
connects it to a trip.

For example, the Paris trip has an ID of `1`.

## Step 2: Retrieve Accommodations

The following request illustrates how to retrieve
accommodation records.

**Example request:**

```http
GET /accomodation
```

**Example cURL command:**

```bash
curl -X GET "http://localhost:3000/accomodation"
```

## Step 3: Examine an Accommodation Record

The source database contains the following accommodation:

```json
{
  "tripId": 1,
  "type": "hotel",
  "name": "Ritz Paris",
  "price": "$$$$$",
  "rating": "5",
  "id": 1
}
```

The `tripId` value of `1` indicates that Ritz Paris
belongs to the Paris trip.

## Step 4: Identify Related Accommodations

Compare the `tripId` property in accommodation records
with the `id` property of the trip.

Records with matching identifiers belong to the same trip.

## Expected Result

You can identify which accommodations are associated
with a particular vacation.

---

# Tutorial 2: Explore Dining Options

## Objective

Learn how to retrieve dining information and identify
restaurants, bakeries, and bars associated with a trip.

## Step 1: Understand the Dining Resource

The `dining` resource stores information about dining
establishments.

Each dining record contains:

- A unique identifier.
- An associated trip identifier.
- The type of establishment.
- The establishment's name.
- A price category.
- A rating.

## Step 2: Retrieve Dining Records

**Example request:**

```http
GET /dining
```

**Example cURL command:**

```bash
curl -X GET "http://localhost:3000/dining"
```

## Step 3: Examine a Dining Record

The source database contains the following restaurant:

```json
{
  "tripId": 1,
  "type": "restaurant",
  "name": "La Tour d'Argent",
  "price": "$$$$$",
  "rating": "5",
  "id": 1
}
```

The `tripId` value of `1` associates this restaurant
with the Paris trip.

## Step 4: Explore Additional Dining Options

The Paris trip also includes the following dining records:

| Name | Type | Price | Rating |
|------|------|-------|--------|
| La Tour d'Argent | Restaurant | $$$$$ | 5 |
| Boulangerie Utopie | Bakery | $ | 5 |
| Pink Mama | Restaurant | $$ | 4 |

Compare the dining options to identify establishments
you may want to include in a vacation plan.

## Expected Result

You can retrieve dining information and identify
multiple establishments associated with the same trip.

---

# Tutorial 3: Find Activities for a Vacation

## Objective

Learn how to retrieve activities and identify attractions
associated with a vacation destination.

## Step 1: Understand the Activity Resource

The `activity` resource stores information about:

- Museums.
- Tours.
- Landmarks.
- Adventures.
- Other travel experiences.

Each activity contains a `tripId` property that
associates it with a trip.

## Step 2: Retrieve Activities

**Example request:**

```http
GET /activity
```

**Example cURL command:**

```bash
curl -X GET "http://localhost:3000/activity"
```

## Step 3: Examine an Activity Record

The Vacation Planner database contains the following activity:

```json
{
  "tripId": 1,
  "type": "museum",
  "name": "Louvre",
  "provider": "null",
  "price": "$$",
  "rating": "5",
  "id": 1
}
```

The `tripId` value of `1` indicates that the Louvre
is associated with the Paris trip.

## Step 4: Understand Activity Providers

Some activities include information about the
organization providing the experience.

For example:

```json
{
  "tripId": 2,
  "type": "tour",
  "name": "Free Tokyo Walking Tour",
  "provider": "Tokyo Localized",
  "price": "$",
  "rating": "null",
  "id": 2
}
```

This record identifies Tokyo Localized as the
provider of the walking tour.

> **Note:** The source database represents missing
> provider and rating values using the string `"null"`.

## Expected Result

You can retrieve activity records and identify
attractions associated with specific trips.

---

# Tutorial 4: Build a Complete Vacation Plan

## Objective

Learn how the Vacation Planner API organizes
accommodations, dining options, and activities
under a single vacation.

This tutorial demonstrates how existing records
can be combined into a vacation plan.

## Step 1: Select a Trip

Begin with the Paris trip from the source database.

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

The trip has an ID of `1`.

This identifier connects the trip to its related resources.

## Step 2: Identify Accommodations

Locate accommodation records with a `tripId` of `1`.

The database contains:

| Accommodation | Type | Price |
|---------------|------|-------|
| Ritz Paris | Hotel | $$$$$ |

## Step 3: Identify Dining Options

Locate dining records with a `tripId` of `1`.

The database contains:

| Dining Option | Type | Price |
|---------------|------|-------|
| La Tour d'Argent | Restaurant | $$$$$ |
| Boulangerie Utopie | Bakery | $ |
| Pink Mama | Restaurant | $$ |

## Step 4: Identify Activities

Locate activity records with a `tripId` of `1`.

The database contains:

| Activity | Type | Price |
|----------|------|-------|
| Louvre | Museum | $$ |

## Step 5: Review the Vacation Plan

The information can now be organized into a
single vacation plan.

### Paris Vacation Plan

**Destination:** Paris, France

**Travel Dates:** June 1–8, 2022

**Accommodation:**
- Ritz Paris

**Dining Options:**
- La Tour d'Argent
- Boulangerie Utopie
- Pink Mama

**Activities:**
- Louvre

All associated records share the same `tripId`.

## Expected Result

You can identify the resources associated with
a trip and organize them into a complete
vacation plan.

This example demonstrates how the source data
supports vacation planning.

It does not represent a confirmed API operation
that automatically generates an itinerary.

---

# Tutorial 5: Create a New Trip

## Objective

Learn how a POST request could be used to create
a new vacation record.

> **Important:** This tutorial illustrates a conventional
> REST API workflow. The POST endpoint and request
> requirements have not been confirmed by the API developer.

## Step 1: Prepare the Trip Information

Before creating a trip, identify the destination
and travel dates.

For this example, create a trip to Rome, Italy.

## Step 2: Prepare the JSON Request Body

```json
{
  "country": "Italy",
  "city": "Rome",
  "startDate": "2027-05-10",
  "endDate": "2027-05-17",
  "rating": "null"
}
```

The request body contains the destination,
travel dates, and rating.

The source database uses `"null"` as a string
for trips without ratings.

## Step 3: Send a POST Request

**Example request:**

```http
POST /trip
Content-Type: application/json
```

**Example cURL command:**

```bash
curl -X POST "http://localhost:3000/trip" \
  -H "Content-Type: application/json" \
  -d '{
    "country": "Italy",
    "city": "Rome",
    "startDate": "2027-05-10",
    "endDate": "2027-05-17",
    "rating": "null"
  }'
```

## Step 4: Verify the New Trip

If the API supports this operation, examine the
response to determine whether the new trip was created.

Verify that the returned record contains:

- Country: Italy.
- City: Rome.
- Start date: May 10, 2027.
- End date: May 17, 2027.

The API developer must confirm how identifiers
are assigned and which response status indicates
successful creation.

## Expected Result

Once the POST operation is implemented and confirmed,
users should be able to create a vacation record
and retrieve it for future planning.

---

## Next Steps

After completing these tutorials, you should
understand how the Vacation Planner API organizes
travel information.

You can continue exploring the API by:

1. Reviewing additional trips.
2. Comparing accommodations.
3. Exploring dining options.
4. Researching activities.
5. Organizing vacation plans.
6. Reviewing ratings from previous trips.

For complete resource definitions, data types,
and supported operations, consult the API Reference.