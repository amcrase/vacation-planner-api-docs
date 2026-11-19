# Vacation Planner API Documentation

## Overview

The Vacation Planner API is a REST API designed to help travelers plan future vacations and maintain records of past trips.

Users can organize destinations, accommodations, dining options, and activities while tracking ratings from previous travel experiences.

The API is intended for individual travelers and boutique travel agencies looking for a convenient way to organize travel plans.

## Features

The Vacation Planner API allows users to:

- Create and organize vacation plans.
- Track past and upcoming trips.
- Research and save accommodations.
- Organize restaurants, bars, and other dining options.
- Add activities, tours, museums, and landmarks.
- Record ratings of previous travel experiences.
- Reference past trips when planning future vacations.

## Getting Started

New to the Vacation Planner API?

Start with the [Quickstart Guide](docs/quickstart.md) to learn how to access the API, retrieve trip information, and understand JSON responses.

## Documentation

The documentation is organized into the following sections:

| Documentation | Description |
|---|---|
| [Quickstart Guide](docs/quickstart.md) | Get started with the API and retrieve your first trip. |
| [Tutorials](docs/tutorials.md) | Follow step-by-step instructions for working with accommodations, dining options, activities, and vacation plans. |
| [API Reference](docs/reference.md) | Explore API resources, properties, endpoints, and request and response formats. |

## API Resources

The Vacation Planner API organizes travel information into four primary resources.

| Resource | Description |
|---|---|
| `trip` | Stores vacation destinations, travel dates, and ratings. |
| `accomodation` | Stores lodging information associated with trips. |
| `dining` | Stores restaurants, bakeries, bars, and other dining options. |
| `activity` | Stores museums, tours, landmarks, and other travel activities. |

Each trip has a unique identifier (`id`). Related resources use the `tripId` property to associate accommodations, dining options, and activities with a specific trip.

## Project Information

This documentation repository was created as part of the **University of Washington API Documentation technical writing course**.

The project focuses on developing clear, accessible, and task-oriented documentation that helps users understand and interact with the Vacation Planner API.

## Documentation Status

Documentation is currently under development. API endpoints, authentication requirements, and implementation details will be updated as they are confirmed.
