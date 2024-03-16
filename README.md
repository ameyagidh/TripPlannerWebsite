# TripPlanner
# Trip Advisor - Travel Planner

## Design Background

### Motivation:
Due to COVID-19, people are no longer able to travel around the U.S.. To better serve people with interests in traveling after the pandemic, our team plans to design and create a user-friendly web application for travelers to easily make visualized travel plans as well as interact with other travelers.

### Design:

<img width="1496" alt="Screenshot 2024-03-16 at 7 33 36 AM" src="https://github.com/ameyagidh/TripPlannerWebsite/assets/65457905/9b092dfd-6ad5-4e96-887d-f2412c6d957e">

<img width="1496" alt="Screenshot 2024-03-16 at 7 34 03 AM" src="https://github.com/ameyagidh/TripPlannerWebsite/assets/65457905/9b06aad2-67cd-4fe1-9883-a61600b8efd5">

<img width="1496" alt="Screenshot 2024-03-16 at 7 34 16 AM" src="https://github.com/ameyagidh/TripPlannerWebsite/assets/65457905/49827e86-8702-47f3-9a8c-9b32db927697">

- The website displays famous tourist places and an embedded Google Maps of San Francisco on the homepage.
- Users can select tourist sights and add them to their planner.
- Selected places are pinned on the embedded Google Maps.
- Google Maps calculates commute time and generates the best route using Google Maps API.
- Users can save their plans and add more text description or pictures to them.
- Users can share their trips on the website and browse posts shared by other users.
- Users can comment on other users’ posts and view other users' public profiles, which contain their shared posts.

---

## Users

### Traveler:
- Signed-in users can make trip plans and save plans into history.
- They can browse other users’ plans.
- Anonymous users can only search spots and browse the posts of other travelers but can't make a plan.

### Administrator:
- Administrators have all functions that travelers have.
- They can manage travelers’ accounts, such as editing users’ plans.

---

## Implementation Plan

### Proposed Technology Stack:
- **Front End:** React Js
- **Back End:** Node.js (using Express framework)
- **Database:** MongoDB to store user information and tourist spots information, image URLs; image files will be stored in a cloud file system.
- **Deployment:** The service will be deployed to Heroku.

### Main functionalities:
- User register/login/logout using token-based authentication.
- Homepage: tourists spot display on Google Map using Google Map Places API.
- Search for different tourist spots: Implement Map Places API to fetch the address, pictures, and other details for the selected spots and display those information on the detail page of the tourist spots.
- Make travel plans and save them into the database.
- Create a webpage that allows users to post or share their trips, and users can comment on the blog posts created by other users.
- Create POST/GET API that enables users to create and edit profile information in the Private User Profile.
- Create a public profile webpage that fetches data from our local API and display information of the account holder and his/her blog posts.

### External APIs:
- **Google Place API:** Provides users detailed information about the place they intend to visit. Enables users to find specific places with an address or name. Identifies users’ locations based on real-time signals.
- **Google Maps API:** Displays local context.
- **Google Routes API:** Directs users to the destination with reliable and efficient routes.

---

## RESTful URLs

### Users:
- Get a specific user’s information: `GET /api/users/<user_id>`
- Create a new user: `POST /api/users/create`
- Update user information: `PUT /api/users/update/<user_id>`
- Delete a user: `DELETE /api/users/delete/<user_id>`
- Get all users: `GET /api/users/`

### Trip:
- Get a specific post: `GET /api/posts/<post_id>`
- Create a new post: `POST /api/posts/create`
- Update post: `PUT /api/posts/update/<post_id>`
- Delete a post: `DELETE /api/posts/delete/<post_id>`
- Get all posts: `GET /api/posts/`

### Travel Plan:
- Create a trip route: `POST /api/trips/create`
- Update trip: `PUT /api/trips/update/<trip_id>`
- Delete a post: `DELETE /api/trips/delete/<trip_id>`
- Get trip details: `GET /api/trips/<trip_id>`

### Search using external API:

- Find tourist attractions detail in SF:
  ```
  GET https://maps.googleapis.com/maps/api/place/textsearch/json?query=<input_search_information>&type=tourist_attraction&locationbias=circle:50000@37.7749,122.4194&key=<YOUR_API_KEY>
  ```

- Google Places Autocomplete JS API: Suggest places in the dropdown box while the user is typing.
  ```
  url="https://maps.googleapis.com/maps/api/js?key=your_api_key&libraries=places"
  ```

- Display and search on Google Maps:
  ```
  https://www.google.com/maps/embed/v1/search?key=<YOUR_API_KEY>&q=<INPUT_INFO>
  ```

---

This repository is the project's backbone, where the codebase will be maintained and updated. For any inquiries or contributions, please feel free to reach out to the team members listed above. Let's make traveling easier and more enjoyable for everyone! 🌍✈️🚗
