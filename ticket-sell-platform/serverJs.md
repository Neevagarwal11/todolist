# Ticket Sell Platform API

## Endpoints

### User Registration
- **Method:** POST
- **Endpoint:** `/api/register`
- **Description:** Registers a new user.
- **Request Body:**
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "User registered successfully!"
  }
  ```

### User Login
- **Method:** POST
- **Endpoint:** `/api/login`
- **Description:** Logs in a user.
- **Request Body:**
  ```json
  {
    "username": "string",
    "password": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Login successful"
  }
  ```

### User Logout
- **Method:** GET
- **Endpoint:** `/api/logout`
- **Description:** Logs out a user.
- **Response:**
  ```json
  {
    "message": "User logged out"
  }
  ```

### Get User Details
- **Method:** GET
- **Endpoint:** `/api/user`
- **Description:** Gets user details including any tickets purchased.
- **Response:**
  ```json
  {
    "username": "string",
    "events": [/* array of events */],
    "cart": [/* array of events in cart */]
  }
  ```

### Create New Event
- **Method:** POST
- **Endpoint:** `/api/events`
- **Description:** Creates a new event.
- **Request Body:**
  ```json
  {
    "name": "string",
    "date": "string",
    "location": "string",
    "price": "number"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Event created successfully!",
    "event": {/* event object */}
  }
  ```

### List All Events
- **Method:** GET
- **Endpoint:** `/api/events`
- **Description:** Lists all events.
- **Response:**
  ```json
  [/* array of events */]
  ```

### Buy Ticket
- **Method:** POST
- **Endpoint:** `/api/buy-ticket`
- **Description:** Allows a user to buy a ticket for an event.
- **Request Body:**
  ```json
  {
    "eventId": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Ticket purchased successfully",
    "event": {/* event object */}
  }
  ```

### Add Event to Cart
- **Method:** POST
- **Endpoint:** `/api/cart/add`
- **Description:** Adds an event to the user's cart.
- **Request Body:**
  ```json
  {
    "eventId": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Event added to cart",
    "cart": [/* array of events in cart */]
  }
  ```

### View Cart
- **Method:** GET
- **Endpoint:** `/api/cart`
- **Description:** Views the user's cart.
- **Response:**
  ```json
  {
    "cart": [/* array of distinct events in cart */],
    "totalDistinctEvents": "number",
    "eventCounts": [
      {
        "event": {/* event object */},
        "count": "number"
      }
    ]
  }
  ```

### Remove Event from Cart
- **Method:** POST
- **Endpoint:** `/api/cart/remove`
- **Description:** Removes an event from the user's cart.
- **Request Body:**
  ```json
  {
    "eventId": "string"
  }
  ```
- **Response:**
  ```json
  {
    "message": "Event removed from cart",
    "cart": [/* array of events in cart */]
  }
  ```
