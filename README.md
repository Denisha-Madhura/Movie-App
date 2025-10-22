# Movie Explorer 🎬
A dynamic and feature-rich movie browsing application built with React. This app allows users to search for thousands of movies using the TMDB database and tracks trending searches in real-time using Appwrite, ensuring a fast and optimized experience.

https://github.com/user-attachments/assets/2553e520-ba50-4db0-b008-7cef292c9e9e

## ✨ Key Features
- Extensive Movie Catalog: Browse and search through thousands of movies powered by The Movie Database (TMDB).
- Real-time Trending Searches: A dedicated "Trending Searches" section, powered by Appwrite, displays the top 5 most popular recent searches, keeping the content fresh and relevant.
- Optimized Search Performance: Search functionality is optimized using a 500ms debounce to prevent excessive API calls, ensuring a smooth and responsive user experience.
- Modern UI: A clean, intuitive, and responsive dark-mode interface built with modern React standards.

## 💻 Tech Stack

| Category | Technology | Purpose | 
 | ----- | ----- | ----- | 
| **Frontend** | `React` | Building the user interface and component logic. | 
| **API/Data** | `TMDB API` | Main source for movie data (posters, titles, details). | 
| **Backend/DB** | `Appwrite` | Used for tracking, aggregating, and serving the real-time "Trending Searches" data. | 
| **Utilities** | `Debounce` | Optimizing the search input to manage API calls efficiently. |


## 🚀 Getting Started
Follow these steps to get your local environment set up and running.

### Prerequisites
You need to have Node.js and npm installed on your machine.

**1. Clone the repository**

```
    git clone [https://github.com/denisha-madhura/movie-app.git](https://github.com/denisha-madhura/movie-app.git)
    cd movie-app
```



**2. Install dependencies**
```
    npm install
    # or
    yarn install
```



**3. Setup Environment Variables**

This project requires environment variables for both TMDB and Appwrite. Create a file named .env in the root directory of the project and add the following:

```
    # --- TMDB Configuration ---
    REACT_APP_TMDB_API_KEY=YOUR_TMDB_API_KEY
    
    # --- Appwrite Configuration ---
    REACT_APP_APPWRITE_ENDPOINT=YOUR_APPWRITE_ENDPOINT
    REACT_APP_APPWRITE_PROJECT_ID=YOUR_APPWRITE_PROJECT_ID
    REACT_APP_APPWRITE_DATABASE_ID=YOUR_APPWRITE_DATABASE_ID
    REACT_APP_TRENDS_COLLECTION_ID=YOUR_TRENDS_COLLECTION_ID
```


How to get your keys:

- TMDB API Key: Register for a free account on The Movie Database (TMDB) and generate an API key.
- Appwrite Credentials:
  1. Set up an Appwrite instance (local or hosted).
  2. Create a new Project.
  3. Create a Database (e.g., movie_db).
  4. Create a Collection (e.g., search_trends) within that database. This collection is where search queries are logged.

**4. Run the application**
Start the development server:
```
npm start
# or
yarn start
```

The application will now be running at http://localhost:3000.

## 🛠 Appwrite Implementation Details

The real-time Trending Searches feature works as follows:
- Search Log: Every time a user executes a search (after the debounce period), the search term is logged as a new document in the dedicated Appwrite collection (search_trends).
- Aggregation: The application queries Appwrite to fetch the latest search logs.
- Real-time Update: Using Appwrite's real-time capabilities or periodic polling, the front end updates the "Trending Searches" list to reflect the most frequent recent queries, offering a truly dynamic trending list.

## 💡 Learning & Inspiration
This project was built as a hands-on learning exercise based on the following tutorial, which guided the core implementation of the React components and TMDB integration:
YouTube Tutorial:  https://youtu.be/dCLhUialKPQ

