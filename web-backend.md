[Back](web.md)

# Holton Orbeas Rogue Web Backend

## Technical Documentation
    
### GETTING STARTED

Holton Orbeas Rogue Web Backend was developed using the Node.JS JavaScript framework.

### INSTALLATION AND DEVELOPMENT

Firstly, the user must have [Node.JS](https://nodejs.org/en/) installed. And after that, the user must follow the guide for ExpressJS [here](https://expressjs.com/en/starter/installing.html).
Lastly, the user must have a text editor program. The developers suggest [Visual Studio Code](https://code.visualstudio.com/).

### PROGRAMMING LANGUAGE

Holton Orbeas Rogue Web Backend uses JavaScript for development

### DEBUGGING

The developers use Chrome Dev Tools. 

### IMPORTANT CLASSES

#### Initialization Classes
- **server.js** - handles the initialization of server configuration
- **config.js** - processes the environment ports
- **app.js** - initiates the middleware, routes, error handler, and server configuration

#### Middlewares

- **cookieMiddleware.js** - intercepts and validates the cookies
- **tokenMiddleware.js** - validates the authentication token

#### Controllers
- **adminController.js** - handles the requests related to the admin route
- **landmarkController.js** - handles the requests related to the landmark route
- **loginController.js** - handles the requests related to the login route
- **logoutController.js** - handles the requests related to the logout route
- **userController.js** - handles the requests related to the user route
- **wikipediaController.js** - handles the requests related to the wikipedia route

#### Routes
- **routes.js** - compiles the routes
- **adminRoutes.js** - contains the endpoints for the admin resource
- **landmarkRoutes.js** - contains the endpoints for the landmark resource
- **loginRoutes.js** - contains the endpoints for the login resource
- **logoutRoutes.js** - contains the endpoints for the logout resource
- **userRoutes.js** - contains the endpoints for the user resource
- **wikipediaRoutes.js** - contains the endpoints for the wikipedia resource

### ARCHITECTURE USED
Orbeas Rogue Web Backend uses the MVC architecture. To know more about it, please refer to this [link](https://developer.mozilla.org/en-US/docs/Glossary/MVC)
