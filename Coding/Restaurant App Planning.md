## Idea

- Save restaurants you've been to and dishes you ate there
- Record thoughts about the restaurant and specific dishes
	- Could also have a rating system
- Cuisine tags
- Future features
	- Restaurant and/or dish recommendations
	- Price tracking
	- Social aspect - public and private profiles

## Tech stack

- Front-end: React (web) and React Native (mobile)
- Backend: Node.js
- Database: MySQL
- Docker?

## Frontend

- My Restaurants page
	- Lists all the restaurants you've added as a list or cards (alphabetical order)
	- Button to add a new restaurant
	- Search previously-added restaurants by name or cuisine
- Specific restaurant page
	- Section at the top for notes
	- Lists all the dishes you've added
	- Button to add a new restaurant

## Backend

- Restaurant and Dish endpoints
	- CRUD

## Database Tables

- Restaurants
	- ID (PK)
	- Name
	- Address/Location
	- Cuisine
	- Dishes (FK)
	- Notes or rating
- Dishes
	- ID (PK)
	- Name
	- Restaurant (FK)
	- Notes or rating