# Setting up the Express.js Backend
This document provides step-by-step instructions on how to build and run the JavaScript backend in Express for the CLI Task Timer project. Follow the steps below to set up the project environment and get the backend server running.

---

## Prerequisites

1. **Node.js** (Version 14 or higher recommended)
   - Download and install Node.js from nodejs.org.
2. **NPM or yarn**
   - NPM comes with Node.js installation. To check, run
 ```bash
 npm -v
 ```
  - Alternatively, install Yarn by running:
```bash
 npm install -g yarn
```
3. **Git**
   - Ensure Git is installed to clone the repository.
   - Check by running:
 ```bash
  git --version
 ```
4. **Postman or Browser**
   - Test API endpoints

## File structure overview 
The backend folder structure is as follows:

```
.
├── .idea/                  
├── bin/                    
├── models/
│   └── taskTimer.js        
├── public/
│   ├── stylesheets/
│   │   └── style.css       
│   └── index.html         
├── routes/
│   ├── index.js           
│   ├── timerRequests.js    
│   └── users.js           
├── app.js                 
├── functions.js            
├── package-lock.json      
├── package.json           

```
- **`models/taskTimer.js`**: Defines the structure for tasks and timers.
- **`routes/`**: Contains Express route handlers for different API endpoints.
- **`public/`**: Contains static files like the main HTML and CSS for the frontend.
- **`app.js`**: The main entry point of the application.

---

## Step-by-Step Guide

### 1. Clone the Repository

Clone the repository from GitHub:

```bash
git clone <repository-url>
cd <repository-folder>
```

Replace `<repository-url>` with the actual URL of the backend repository.

---

### 2. Install dependencies

Install all required dependencies listed in the package.json file:

```bash
npm install
```
If you are using yarn run: 

```bash
yarn
```

---

### 3. Run the application

Start the application using the following command:

```bash
npm start
```
Alternatively, for development mode with live reload (if using nodemon):

```bash
npm run dev
```
By default, the server will run on http://localhost:3000.

### 4. Test API Endpoints

1. Open Postman or your browser.
2. Test the available routes
    - Example:
    - Timer-related API endpoints can be found in routes/timerRequests.js.
    - User-related API endpoints are in routes/users.js.
---

## Common Scripts in package.json

- Start the application:
```bash
npm start
```
- Run in Development Mode:
```bash
npm run dev
```
(Ensure nodemon is installed as a dev dependency.)

---

## Troubleshooting

1. Port Conflict: If port 3000 is occupied, change the port in app.js:
```javascript
const PORT = process.env.PORT || 3001;
app.listen(PORT, () => {
    console.log(`Server running on port ${PORT}`);
});
```
2. Missing Dependencies: If you encounter issues with missing modules, reinstall dependencies:
   
```bash
npm install
```
3. Static Files Not Found: Ensure that the public/ directory is set as the static folder in app.js:

```javascript
app.use(express.static('public'));
```

4. Route Errors: Ensure your routes files are correctly imported in app.js:

```javascript
const timerRoutes = require('./routes/timerRequests');
app.use('/api/timers', timerRoutes);
```
---
Making sure you follow these steps correctly, you should be able to configure and run the Express.js backend succesfully.
