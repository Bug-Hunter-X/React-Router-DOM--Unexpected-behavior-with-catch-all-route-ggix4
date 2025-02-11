# React Router DOM Unexpected Route Behavior
This repository demonstrates an uncommon bug in React Router DOM v6 where the catch-all route (`*`) doesn't render as expected when navigating to a non-existent route.  The issue seems to be related to how React handles component unmounting and re-mounting in combination with the routing system.  This is a simplified example to illustrate the problem.

## Bug Description
The `App.js` file contains a simple React Router setup with three routes: `/`, `/about`, and a catch-all route for `*`.  Navigating to `/` or `/about` works as expected. However, when navigating to a non-existent route (e.g., `/invalid`), the `NotFound` component should render, indicating a 404 error. Instead, the app may show nothing, or strangely, keep showing a previous component.

## Solution
The solution in `AppSolution.js` addresses this by using the `useLocation` hook to force a re-render when the location changes. This ensures that the `NotFound` component is properly rendered when a non-existent route is accessed.

## Reproduction Steps
1. Clone this repository.
2. Run `npm install` to install dependencies.
3. Run `npm start` to start the development server.
4. Navigate to `/`, `/about`, and `/invalid` (or any other invalid route). Observe the unexpected behavior in `App.js` and the corrected behavior in `AppSolution.js`.