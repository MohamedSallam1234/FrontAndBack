# Microcers Ecommerce Website

## Overview

The **Microcers Ecommerce Website** is a scalable online shopping platform developed using microservices architecture. The platform provides an intuitive interface for users to browse products, add them to the cart, and complete the checkout process. The backend system is modular, allowing for seamless scaling, enhanced reliability, and clear separation of services.

### Key Features

- **User Authentication:** A secure login and registration system, allowing users to create accounts, log in, and manage their profiles.
- **Product Management:** Browse and view product listings, categories, and detailed information including images, pricing, and availability. Administrators can add, update, and remove products from the inventory.
- **Shopping Cart:** Add items to the cart, update quantities, and view the total price before proceeding to checkout. Cart data is stored and synchronized across sessions for logged-in users.
- **Checkout Process:** A clear and user-friendly checkout experience, including payment processing, address management, and order confirmation. Users can select from different payment methods such as credit cards or PayPal.
- **Real-Time Communication:** Uses Kafka for efficient inter-service communication, ensuring real-time synchronization across microservices, including inventory updates and order status changes.
- **Wishlist Management:** Users can add products to their wishlist for later viewing and easily add wishlist items to the cart. The wishlist feature provides users with a personalized shopping experience.
- **Rental Options:** Products can be rented as well as purchased, allowing flexible purchasing options. Users can select rental duration, and rental pricing is calculated accordingly.
- **Order Tracking:** Users receive real-time updates on their order status, from processing to shipping and delivery.
- **Customer Reviews:** Users can leave reviews and ratings for products they have purchased, helping other customers make informed decisions.

## Technologies Used

- **Frontend:** [Next.js](https://nextjs.org) for the user interface and improved SEO.
- **Backend:** [NestJS](https://nestjs.com) used to implement microservices with a modular approach.
- **Database:** [MongoDB](https://www.mongodb.com) for efficient and scalable data storage.
- **Messaging System:** [Kafka](https://kafka.apache.org) for reliable messaging between microservices.
- **Containerization:** [Docker](https://www.docker.com) to containerize the services and ensure consistency across different environments.
- **Authentication:** [JWT (JSON Web Tokens)](https://jwt.io) for secure user authentication and session management.
- **Payment Integration:** Integrated with third-party payment gateways such as Stripe and PayPal for secure payment processing.

## System Architecture

The application is built following a **microservices architecture** that divides the core functions into independent services that communicate using **Kafka**. Each service is containerized using **Docker** for easy deployment and scaling. This architecture ensures that each service can be developed, deployed, and scaled independently, improving overall system reliability and maintainability.

### Microservices Included:

1. **User Service**: Manages user registration, login, profile information, and authentication tokens. This service also handles password reset requests and email verification.
2. **Product Service**: Handles product listings, categories, inventory management, and product details. Provides APIs to add, update, and delete products for administrative users.
3. **Cart Service**: Manages user shopping cart operations, including adding items, updating quantities, and removing products. Cart data is persistent for logged-in users.
4. **Order Service**: Handles order processing, payment confirmation, and order history. Manages order status updates and notifies users of changes.
5. **Review Service**: Allows users to leave product reviews and ratings for other customers to see. Reviews are displayed on the product detail page and can be managed by users.
6. **Wishlist Service**: Manages user wishlists, allowing users to add and remove products for future reference.
7. **Notification Service**: Sends email notifications to users for important events such as order confirmation, shipping updates, and password resets.

## Features Walkthrough

1. **Login & Registration**:
    - Users can register using their personal details (name, email, phone, etc.) and verify their email to complete the registration.
    - Registered users can log in to view products, add items to their cart, and manage their wishlist.
    - **Forgot Password**: Users can reset their password by providing their registered email address, receiving a reset link, and setting a new password.

2. **Product Listings & Details**:
    - Browse featured listings and filter products by category, price range, and other attributes.
    - Each product page shows detailed information, including images, descriptions, pricing, availability, and user reviews.
    - **Related Products**: Display similar products to help users discover more items of interest.

3. **Shopping Cart & Checkout**:
    - Users can add products to the cart, update quantities, apply coupons, and proceed to checkout.
    - **Coupon Codes**: Users can apply valid coupon codes to receive discounts on their orders.
    - Secure checkout process with payment options including credit cards and PayPal.
    - **Shipping Address Management**: Users can add, update, and select shipping addresses during checkout.

4. **Order Management & Wishlist**:
    - Track order status, view order history, and manage saved addresses. Users can view order details, including items purchased, total amount, and current status.
    - Save products to wishlist for easy access in future sessions. Wishlist items can be moved to the cart for purchase.
    - **Order Cancellation**: Users can cancel orders that have not yet been shipped.

5. **Customer Reviews**:
    - Users can write reviews for products they have purchased, rate products, and help other users make informed decisions.
    - Reviews can be edited or deleted by the user who submitted them.
    - Product ratings are aggregated and displayed on product pages.

## Getting Started

### Prerequisites

- **Node.js** (v16+)
- **Docker** (for containerization)
- **MongoDB** (You can use a locally installed MongoDB or MongoDB Atlas)
- **Kafka** (for messaging between microservices)

### Installation Steps

1. **Clone the Repository**:
    ```bash
    git clone https://github.com/YourUsername/microcers-ecommerce.git
    cd microcers-ecommerce
    ```

2. **Install Dependencies**:
    ```bash
    npm install
    ```

3. **Configure Environment Variables**:
    - Create a `.env` file in the root directory with the required variables (MongoDB URI, Kafka configuration, payment gateway keys, etc.)

4. **Run Services with Docker**:
    ```bash
    docker-compose up
    ```

5. **Access the Application**:
    - The frontend will be available at `http://localhost:3000`
    - API endpoints will be available at `http://localhost:4000`

### Running Tests

- **Unit Tests**: Run unit tests for individual services using the following command:
    ```bash
    npm run test
    ```
- **Integration Tests**: Ensure all services work seamlessly together:
    ```bash
    npm run test:integration
    ```

## Contributing

We welcome contributions to improve this project. If you wish to contribute:

1. Fork the repository.
2. Create a new feature branch.
3. Commit your changes and create a pull request.

### Contribution Guidelines

- Ensure all new features are covered by unit and integration tests.
- Follow the existing code style and conventions.
- Write detailed commit messages to describe the changes made.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For more information, visit our [GitHub Repository](https://github.com/YourUsername/microcers-ecommerce) or contact Mohamed Ibrahim at [email@example.com].

## Future Enhancements

- **Microservice Auto-Scaling**: Implement Kubernetes for auto-scaling of microservices based on load.
- **ElasticSearch Integration**: Add ElasticSearch to enhance the search functionality and provide more accurate product search results.
- **Recommendation System**: Use machine learning algorithms to recommend products to users based on their browsing and purchasing history.
- **Multi-Language Support**: Provide multi-language support to reach a wider audience.
- **Advanced Analytics**: Add an analytics dashboard for admins to monitor sales, customer behavior, and system performance.
