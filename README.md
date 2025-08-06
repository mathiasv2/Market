# What is it ❓

**Market** is a simple microservices-based application designed to manage products and customer orders. It consists of two independent services:

- A **Product Service** that handles product creation, updates, and inventory.
- A **Command (Order) Service** that processes customer orders and manages product quantities.

These services communicate asynchronously using **RabbitMQ** and expose their APIs through a centralized **API Gateway**. Each service has its own dedicated **MySQL** database to ensure data separation and autonomy.

This project serves as a basic example of distributed architecture using containers and message-based communication.


# Get Started 🚀

All you need to do is to clone this repository with : 

```git clone --recurse-submodules https://github.com/mathiasv2/Market.git```

Then ```cd Market```

Then ```docker compose up --build``` at root project 

Both databases needed will be created, both microservices will start and you can finally use gateway api endpoints

# Product Endpoints 📦

- GET http://localhost:3000/product/getall
- GET http://localhost:3000/product/get/{productId}
- POST http://localhost:3000/product/create JSON body should be something like :
    ```
    {
    "price": 10,
    "quantity": 10,
    "name": "Macron"
    }
- PUT http://localhost:3000/product/update/{productId} JSON body should be something like :
    ```
    {
    "price": 10,
    "quantity": 1000,
    "name": "EXPLOSION"
    }
- DELETE http://localhost:3000/product/delete/{productId}

# Command Endpoints 🛒

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

  
# Tech Stack 📚

| Layer              | Technology        |
|--------------------|-------------------|
| Language           | C# (.NET)         |
| API Communication  | REST              |
| Messaging          | RabbitMQ          |
| Databases          | MySQL (one per service) |
| API Gateway        | Custom Gateway (C#) |
| Containerization   | Docker, Docker Compose |


  
