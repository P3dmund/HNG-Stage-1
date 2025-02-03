# Number Facts API

## Overview

The **Number Facts API** is a simple Flask-based web service that classifies numbers and provides interesting mathematical properties along with a fun fact.

## Features
- Accepts a **GET** request with a number parameter.
- Determines if the number is **prime**, **perfect**, or **an Armstrong number**.
- Classifies numbers as **odd** or **even**.
- Computes the **sum of its digits**.
- Retrieves a **fun fact** about the number using [Numbers API](http://numbersapi.com/).
- Returns JSON-formatted responses.
- Handles invalid input gracefully.

## API Specification

### Endpoint
```
GET /api/classify-number?number=<integer>
```
### Example Request
```
curl "http://127.0.0.1:5000/api/classify-number?number=371"
```
### Success Response (200 OK)

```json
{
    "number": 371,
    "is_prime": false,
    "is_perfect": false,
    "properties": ["armstrong", "odd"],
    "digit_sum": 11,
    "fun_fact": "371 is an Armstrong number because 3^3 + 7^3 + 1^3 = 371"
}
```

### Error Response (400 Bad Request)

```json
{
    "number": "abc",
    "error": true
}
```

## Installation & Running the API

### Prerequisites
- Python 3
- Flask
- Requests Library

### Setup

1. Clone the repository:
   ```sh
   git clone <https://github.com/P3dmund/HNG-Stage-1.git>
   cd <HNG-Stage-1>
   ```
2. Install dependencies:
   ```sh
   pip install flask requests
   ```
3. Run the API:
   ```sh
   python app.py
   ```
4. Access it locally at:
   ```
   http://127.0.0.1:5000/api/classify-number?number=371
   ```

## Deployment

To deploy the API, use any cloud hosting service like:
- **Render**
- **Railway**
- **Fly.io**
- I used **Render**

Example steps for deploying on **Render**:

1. Push the code to GitHub.
2. Go to [Render](https://render.com/) and create a new web service.
3. Link your GitHub repo.
4. Set the **start command** as:
   ```sh
   python app.py
   ```
5. Deploy and get a public URL.

## Testing

To test the API:
- Use a browser: `http://127.0.0.1:5000/api/classify-number?number=371`
- Use **Postman** or **cURL**.

## Submission

Once deployed:
1. Ensure all acceptance criteria are met.
2. Verify the API is **publicly accessible** and stable.
