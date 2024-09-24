
# README for POS System Dish Update API

## Introduction
This README outlines details for the external API endpoint tailored for POS systems that are integrated with our service. This endpoint is designed to facilitate real-time updates to dish information, ensuring the POS system data aligns with changes made within the operational environment.

## Getting Started
POS systems need to be pre-configured with an API key provided by our service to interact with this endpoint. This key is crucial for authenticating and authorizing requests.

### Prerequisites
- An API key issued by our service.
- Completed integration setup between the POS system and our service.

### Using the API
The API endpoint accepts data updates concerning dish details from POS systems. Here’s how to set up and use the API effectively:

1. Obtain an API key from our service.
2. Configure your system to send updates using the provided endpoint details.

## API Endpoint Details

### Endpoint
**URL**: `https://menuapi.hopa.tech/v1/posRoutes/dish`

**Method**: `PATCH`

### Headers
- **Content-Type**: `application/json`
- **Authorization**: `Bearer Your_Access_Token_Here`

### Request Body
#### Required Fields
- **pos_id** (string): Unique identifier for the POS system This is the same identifier that was given by the POS system to Hopa's restaurant.
- **dish_catalog_id** (string): Catalog identifier of the dish. This is the same identifier that was given by the POS system.

#### Optional Fields
- **dish_name** (object): Multilingual name of the dish provided in key-value pairs where keys are language codes.
- **description** (object): Description of the dish, structured similarly to `dish_name`.
- **price** (number): Dish price. Must be a positive number.
- **is_visible** (boolean): Indicates if the dish should be visible in the menu.
- **out_of_stock** (boolean): Stock availability of the dish.

### Sample Request
```json
{
  "pos_id": "816583",
  "dish_catalog_id": "123456",
  "dish_name": {
    "he": "חומוס בשר",
    "en": "Meat Humus"
  },
  "description": {
    "he": "מגיע עם שתי פיתות"
    "en": "Comes with two pita bread."
  },
  "price": 55,
  "is_visible": true,
  "out_of_stock": false
}
```

## Responses
### Success Response
- **Code**: 204 OK
- **Content**: no content

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
  "error": "Invalid or missing authentication token."
}
```

## Notes
- Ensure the bearer token is securely stored and not exposed in public repositories or client-side code.
- Input validation is enforced, and requests with invalid or missing required fields will be rejected.
- We recommend implementing detailed logging and monitoring to track API usage and assist with troubleshooting.

## Conclusion
This API endpoint plays a vital role in maintaining up-to-date and consistent dish information across integrated POS systems and our service. Effective implementation and usage will significantly improve data accuracy and operational reliability.
