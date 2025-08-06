# Get Started

All you need to do is to clone this repository with : ```git clone --recurse-submodules https://github.com/mathiasv2/Market.git```

Then ```docker compose up --build``` at root project 

# Product Endpoints

- GET http://localhost:3000/product/getall
- GET http://localhost:3000/product/get/{productId}
- POST http://localhost:3000/product/create JSON body should be something like :
    ```
    {
    "price": 10,
    "quantity": 10,
    "name": "Macron"
    }
- PUT http://localhost:5002/api/product/update/{productId} JSON body should be something like :
    ```
    {
    "price": 10,
    "quantity": 1000,
    "name": "EXPLOSION"
    }
- DELETE http://localhost:3000/product/delete/{productId}

# Command Endpoints 

- POST http://localhost:3000/command/create JSON body should be something like :
  ```
  {
  "productsOrdered": [
    {
      "productId": 1,
      "quantityOrdered": 10
    },
    {
      "productId": 2,
      "quantityOrdered": 3
    },
    {
      "productId": 3,
      "quantityOrdered": 20
    }
  ],
  "orderDate": "2025-08-06T09:06:00"
  }

- GET http://localhost:3000/command/get/{commandId} 

  
