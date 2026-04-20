# Concept-by-Concept Guide for Building a React Application (PCp Examination)

## Overview

The exam is an end-to-end React application build, not just theoretical.

You are expected to:

* Perform token fetch and private data fetch (public API + protected API using JWT)
* Set up global state
* Implement routing using `react-router-dom`
* Build required features
* Deploy the application (Vercel or Render)

This follows the same pattern as your CA1:

* Creating a server
* Using JWT token to access dataset from `/private` endpoint

---

## How to Start Building Your Project

### 1. Initialize Your Project

* Open terminal in your target folder

* Run:
npm create vite@latest whatever_project_name -- --template react
cd whatever_project_name
npm install
npm install express react-router-dom axios uuid
npm run dev
---

## 2. Project Folder Structure (Inside `src`)

Irrespective of the project, most will require the following structure:

---

### API

* Responsible for fetching dataset from private endpoint using public base URL

* `api.js` should contain:

  * Function to call public token endpoint
  * Function to call private data endpoint using Bearer token

**Why:**
Keeps network logic separate from UI and state logic

---

### Components

* Contains reusable UI components
* Used to build the main page structure

---

### Routes

* Defines all application routes
* Includes paths like `/stats` or any route mentioned in the question paper

---

### Pages

* Each route has a corresponding page
* Contains logic and UI specific to that route

---

### Context

* Create an `AppContext` file
* The AppContext file is used to globally save the dataset and extensively use it by creating child components. The file in API and Appcontext goes hand in hand, meaning, the api.js sends the actual api request to the server to get the JWT token while the  AppContext file has the user info necessary for accessing the JWT token and fetching he dataset and store it globally for all the components. u will also add producer aned consumer custom hooks in this case


### Reducer

* Create an `AppReducer` file

* Define actions such as:

  * `SET_DATA`
  * `ADD_ITEM`
  * `DELETE_ITEM`
  * `TOGGLE_STATUS`
  * `UPDATE_ITEM`

**Why:**
Provides predictable and testable state updates using immutable patterns

---

once this your core logic and things are done, jut push the code to github and then do the following for live deplyment:

1. Sign in to Vercel with your github account
2. in the top right corner of the page you will find an ADD NEW option -> click on it and you will see 'Project' in the menu. Click on that ad your repository will be present. Just import it and the application will be deployed.

---

## Running the Project Locally

1. Clone the repository:
git clone <your-repo-url>
cd <your-project-folder>


2. Install dependencies:
npm install 

3. Start the development server:
npm run dev

Then checkout http://localhost:5173