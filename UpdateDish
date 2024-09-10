
# README for POS System Dish Update API

## Introduction
This README provides information about the external API endpoint designed for POS systems integrated with our service. The endpoint facilitates real-time updates to dish information whenever a change is made within a POS system.

## Getting Started
To use this API, POS systems must have been provided with an API key by our service. This key is required to authenticate and authorize requests made to the endpoint.

### Prerequisites
- POS systems need an authorized API key provided by us.
- Integration setup completed between the POS system and our service.

### Using the API
The API endpoint is designed to receive updates about changes in dish details from the POS systems. Below are the steps to set up and use the API:

1. Ensure you have received an API key.
2. Use the endpoint as described below to send updates.

## API Endpoint Details

### Endpoint
**URL**: `/update-dish`

**Method**: `POST`

### Headers
- **API-Key**: _Your_API_Key_Here_

### Request Body
#### Required Fields
- **pos_id** (string): The unique identifier for the POS system.
- **pos_name** (string): The name of the POS system.
- **dish_catalog_id** (string): The catalog identifier for the dish.

#### Optional Fields
- **name** (object): The multilingual name of the dish, structured as a language map.
- **description** (string): A description of the dish.
- **price** (float): The price of the dish. Must be greater than 0.
- **is_visible** (boolean): Visibility status of the dish on the menu.
- **out_of_stock** (boolean): Stock availability of the dish.

### Sample Request
```json
{
  "pos_id": "12345",
  "pos_name": "ExamplePOS",
  "dish_catalog_id": "67890",
  "name": {
    "en": "Cheeseburger",
    "fr": "Cheeseburger"
  },
  "description": "A delicious cheeseburger with all the fixings.",
  "price": 8.99,
  "is_visible": true,
  "out_of_stock": false
}
```

## Responses
### Success Response
- **Code**: 200 OK
- **Content**: 
```json
{
  "message": "Dish updated successfully."
}
```

### Error Responses
- **Code**: 400 Bad Request
- **Content**: 
```json
{
  "error": "Missing required fields or invalid data format."
}
```

- **Code**: 401 Unauthorized
- **Content**:
```json
{
  "error": "Invalid API Key."
}
```

## Notes
- Ensure that the API key is securely stored and not exposed in public repositories or client-side code.
- Validation checks are performed on all inputs, and requests with invalid or missing required fields will be rejected.
- Detailed logging and monitoring are recommended to track the usage and troubleshoot any issues.

## Conclusion
This endpoint is crucial for keeping dish details consistent across the POS systems and our service in real-time. Proper implementation and usage of this API will enhance the accuracy and reliability of the data within the integrated systems.
