# Pet Adoption Application

## Overview
This project is a Pet Adoption Application built with React and React Router. It allows users to browse pets available for adoption, search for specific types of pets, and view detailed information about each pet. The application uses React Router for client-side routing to navigate between different pages.

## Features
- **Home Page**: Displays a list of pets available for adoption.
- **Search Page**: Allows users to search for pets based on specific criteria.
- **Pet Details Page**: Shows detailed information about a selected pet.
- **Not Found Page**: Displays a message when a pet's details are not found.

## Project Structure
- `pages/home.js`: Home page component.
- `pages/search.js`: Search page component.
- `pages/detail.js`: Pet details page component.
- `pages/petNotFound.js`: Pet details not found page component.
- `components/root.js`: Root component that serves as the layout for nested routes.

## Routing
The application uses `react-router-dom` for routing. The routes are defined using JSX Route elements and managed by a `RouterProvider`.

### Routes
- `/`: Root route that renders the `Root` component.
- `/home`: Renders the `HomePage` component.
- `/:type`: Renders the `HomePage` component filtered by pet type.
- `/:type/:id`: Renders the `PetDetailsPage` component for a specific pet.
- `/search`: Renders the `SearchPage` component.
- `/pet-details-not-found`: Renders the `PetDetailsNotFound` component.

## Example Code
```javascript
import HomePage from './pages/home';
import SearchPage from './pages/search';
import PetDetailsPage from './pages/detail';
import PetDetailsNotFound from './pages/petNotFound';
import Root from './components/root';

// Add react-router-dom imports
import { Route, RouterProvider, createBrowserRouter, createRoutesFromElements } from 'react-router-dom';

// create router with JSX Route elements
const appRouter = createBrowserRouter(createRoutesFromElements(
  <Route path="/" element={ <Root/> }>
    <Route index element ={<HomePage/> }/>
    <Route path="home" element={<HomePage/> }/>
    <Route path=":type" element ={<HomePage/> }/>
    <Route path=":type/:id" element ={<PetDetailsPage/> }/>
    <Route path="search" element={<SearchPage/>}/>
    <Route path="pet-details-not-found" element={<PetDetailsNotFound/>}/> 
  </Route>
));

function App() {
  return (
    // replace below with a Router Provider
    <RouterProvider router = {appRouter}/>
  );
}

export default App;

Requirements
Node.js
npm or yarn
React
react-router-dom
How to Run
Clone the repository: git clone https://github.com/your-username/pet-adoption-app.git
Navigate to the project directory: cd pet-adoption-app
Install dependencies: npm install or  yarn install
Start the development server: npm start or yarn start
License
This project is licensed under the MIT License.
```
