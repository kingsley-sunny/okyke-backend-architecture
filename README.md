# Okyke System Architecture

## Overview

This document provides a comprehensive overview of the Okyke system architecture, a robust e-commerce platform. The architecture is designed to be modular, scalable, and secure, enabling users to browse products, order and also track orders.

## System Components

The system is organized into several interconnected modules, each responsible for specific functionalities:

### Authentication Layer

- **JWT and OAuth 2.0 Authentication**: Provides secure access to the system with industry-standard authentication protocols.
- **Auth Analytics**: Provide accurate analytics and extensive monitoring of authenticated users.

### Verification Module

The Verification module handles all verification and regulatory requirements:

- **Individual Verification**:

  - Email Verification: Validates the authenticity of the email
  - Phone Verification: Add an extra layer of validation by validating the authenticity of the phone number

- **Seller/Shop Verification**:

  - KYC Verification: Add an extra layer of secure verification incase of user misconduct
  - Business Registration: Validates business registration details (optional)

- **Verification Analytics**: Monitors verified user activities.

### Core Modules

#### Product Module

Manages products with the following capabilities:

- **Product Creation**:

  - Create Products: Creates a new product
  - Product collections: Handles the CRUD operations for the products collections
  - Product attributes: Contains extra product information including size, colors and variants 
  - Product Images: Manages the product images.

- **Product Managements**:

  - Manage Products: Handles products updates
  - Delete Product: Deletes product for a particular seller.

- **Product Analytics**:
  - Product Performance: Track product success metrics by measuring the product orders
  - Plan Products: Monitor how products are being utilized

#### Order Module

Handles orders with the following capacity:

- **Order Creation**:

  - Create Order: Handles order creation for a user.
  - Order Request: Get all the order information for a user


- **Order Management**:

  - Process Order: Handles all the details required to successfully process the order
  - Track Order: Implements monitoring of the order items
  - Cancel Order: discontinue a order.

- **Order Analytics**:
  - Order Performance: Track order success metrics
  - Order Monitoring: Monitor how order are being utilized
  - Order Tracking: Track details of each order.

#### User Module

Manages the activities of user

- **User Management**:

  - Manage Profile: Updates the profile of a user with the profile image
  - Manage Billing details: Add, Update and delete billing details for a user 
  - Manage Credit card details: Add, Update and delete credit card details for a user.
  - Reset Password: Handles change and forgot password for a user.
  

- **User Analytics**:
  - User monitoring: Monitor the activities of users
  - User Performance: Monitor the success rate of the users.
  - User Tracking: Track the user location for security reasons.


#### Cart Module

Manages the activities of user's cart

- **Cart Management**:

  - Add to cart: Add or increment an item to the cart
  - Manage Cart/Cart items: Update the cart items by incrementing, decrementing and clearing all items in the cart
  - Process Checkout: Gets all the fees including the Delivery fee.
  

- **Cart Analytics**:
  - User monitoring: Monitor the activities of the cart.


#### Generated Design Module

Handles the generated designes with the following capacity:

- **Generated Design Creation**:

  - Create Order: Creates generated designs for the user for easy reference.


- **Generated Design Management**:

  - Process Generated Design: Process with Generated Design with external APIs
  - Manage Generated Design: Manages the Generated Design by implementing CRUD operations on it

- **Generated Design Analytics**:
  - Generated Design Performance: Track Generated Design success metrics
  - Generated Design Monitoring: Monitor how Generated Design are being utilized

#### Payment Module

Handles all payment-related operations:

- **Payment Module Adapters**:

  - Paystack Adapter
  - Flutterwave Adapter
  - Providus Adapter
  - Custom Adapter

- **Payment Processing**:

  - Payment Link Generator
  - Virtual Bank Account Manager
  - Payment Processing Engine
  - Credit Card Payment Manager
  - Payment Verification
  - Refund Management
  - Payment Analytics

- **Webhook System**:

  - Payment Event Handler
  - Webhook Router
  - Webhook Security
  - Webhook Configuration


#### Notification Module

Handles all notification related operations:

- **Notification Module Services**:

  - Email Notification Module: Manages all email notifications.
  - SMS Notification Module: Manages all SMS notifications.
  - Push Notification Module: Manages all Push notifications.

- **Notification Adapters**:

  - Resend
  - Twillo
  - Firebase
  - Novu



### Message Queues
#### Queue Module
Handles all message Queues activities.

- **Queue Services**
  - Email Queue
  - Notification Queue
  - SMS Queue
  - Background Jobs

- **Queue Adapter**
  - Bullmq





## System Integrations

The architecture includes several key integrations between modules:

- The Order Module connects to the Payment, User and Product Modules for order creation
- All the Modules connects with the Notification Module
- The Cart Module intergates with the User, and Order Module for the cart management and vice-versa.
- The Payment module integrates with the queue module

## Design Principles

The system architecture follows these key design principles:

1. **Modularity**: Each component has a specific responsibility
2. **Scalability**: The system can handle growing numbers of users and transactions
3. **Security**: Multiple layers of security protect sensitive data
4. **Flexibility**: The system can adapt to different business models and requirements
5. **Integration**: Components work together seamlessly while maintaining separation of concerns

## Technical Implementation

The system is implemented using modern technologies and follows best practices:

- Module based architecture for scalability and maintainability
- RESTful APIs for communication between services
- Event-driven architecture for real-time processing
- Secure authentication and authorization
- Comprehensive logging and monitoring
- Database sharding and replication for performance and reliability

This architecture provides a solid foundation for an e-commerce system that can adapt to evolving business needs while maintaining security, performance, and reliability.

## Database Design
The Database design can be viewed with this link.

<a href="./MerchHub.pdf" target="_blank">View Database design PDF</a>
