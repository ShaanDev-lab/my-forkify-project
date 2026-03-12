# forkify

Forkify is a modern recipe application that allows users to search, view, bookmark, and create recipes. With a database of over one million recipes, you can easily find cooking inspiration, adjust serving sizes dynamically, and save your favorites for later.

## Features

*   **Search Recipes**: Instantly search a database of over 1,000,000 recipes.
*   **View Recipe Details**: Display recipe details including ingredients, cooking time, serving size, and directions.
*   **Adjust Servings**: Dynamically update ingredient quantities based on the desired number of servings.
*   **Bookmark Recipes**: Save your favorite recipes for easy access. Bookmarks are stored in the browser's local storage.
*   **Create Your Own Recipes**: Upload your custom recipes, which will be automatically bookmarked and stored.
*   **Pagination**: Navigate through search results with a simple pagination interface.
*   **Responsive Design**: A user-friendly interface that adapts to various screen sizes.

## Project Architecture

This project is built using a Model-View-Controller (MVC) architecture to organize the code and separate concerns.

*   **Model (`/src/js/model.js`)**: Manages the application's state. It is responsible for all business logic, including fetching data from the Forkify API, managing search results, handling bookmarks, and processing recipe uploads.
*   **Views (`/src/js/views/`)**: Handle the presentation layer. Each component of the UI (e.g., recipe display, search results, bookmarks) has its own view class. The views are responsible for rendering data to the DOM and listening for user interactions. A parent `View.js` class contains common rendering logic inherited by other views.
*   **Controller (`/src/js/controller.js`)**: Acts as the bridge between the Model and the Views. It dispatches tasks based on user input from the views (e.g., a search query) and instructs the model to update its state. It then tells the relevant views to re-render based on the new state.

## Technologies Used

*   **Frontend**: HTML5, Sass/SCSS, JavaScript (ES6+)
*   **Build Tool**: Parcel
*   **Polyfills**: `core-js` and `regenerator-runtime` for cross-browser compatibility.
*   **API**: [Forkify API v2](https://forkify-api.jonas.io/v2)

## Local Development

To run this project on your local machine, follow these steps:

1.  **Clone the repository:**
    ```sh
    git clone https://github.com/shaandev-lab/my-forkify-project.git
    cd my-forkify-project
    ```

2.  **Install dependencies:**
    ```sh
    npm install
    ```

3.  **Get an API Key:**
    To use the recipe upload feature, you need an API key from the [Forkify API website](https://forkify-api.jonas.io/v2). Once you have a key, add it to `src/js/config.js`:
    ```javascript
    // in src/js/config.js
    export const KEY = '<YOUR_API_KEY>';
    ```

4.  **Start the development server:**
    This command will start the Parcel development server and open the application in your default browser.
    ```sh
    npm start
    ```

5.  **Build for production:**
    To create an optimized build for deployment, run:
    ```sh
    npm run build
    ```
    The bundled files will be placed in the `/dist` directory.
