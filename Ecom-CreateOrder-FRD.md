# Functional Requirements Document (FRD)
# Feature: Create New Order

## 1. Introduction
This document defines the requirements for the "Create New Order" feature within the eCommerce platform. This feature will allow users to select products, add them to their cart, apply discounts, choose a payment method, and place an order. Upon order placement, a confirmation will be provided to the user and a notification will be sent to the admin.

## 2. Objective
The primary goal of this feature is to provide a seamless experience for users to place an order from browsing products to completing the payment process. This includes managing the shopping cart, applying promo codes, selecting shipping methods, and confirming the order.

## 3. Scope
This feature covers the following functionalities:
* Cart management (adding/removing products, modifying quantities)
* Promo code validation and application
* Shipping method selection
* Payment gateway integration
* Order confirmation (for both user and admin)
* User order history tracking
* Admin notifications for new orders

## 4. Functional Requirements
The following sections describe each of the major functional components required for the "Create New Order" feature.

### 4.1. Cart Management
FR-1.1: The system shall allow users to add products to their shopping cart.
The product details page should include an "Add to Cart" button that adds the product to the user's cart.

FR-1.2: The system shall allow users to view, edit, and remove products from the cart.
Users should see the cart summary with product name, quantity, price, and total.
Users can increase or decrease quantities or remove items from the cart.

FR-1.3: The system shall display a subtotal for the cart and update in real-time as items are added or removed.
The subtotal should update as users modify cart contents.

### 4.2. Promo Code Application
FR-2.1: The system shall provide an input field for users to enter a promo code at checkout.
The promo code input field should be clearly visible on the checkout page.

FR-2.2: The system shall validate the promo code entered by the user.
If the promo code is valid, the system shall apply the discount to the total order cost.
If invalid, the system shall display an error message.

FR-2.3: The system shall calculate and display the updated order total, including the applied promo code discount.

### 4.3. Shipping Method Selection

FR-3.1: The system shall allow users to select a shipping method from a list of available options.
Options may include standard, expedited, and free shipping.

FR-3.2: The system shall display the estimated delivery time and associated cost for each shipping method.
Upon selection, the system updates the order total with the selected shipping method.

### 4.4. Payment Gateway Integration

FR-4.1: The system shall integrate with a payment gateway to process payments.
Supported payment methods include credit/debit cards (Visa, MasterCard), PayPal, and possibly others (Stripe, etc.).

FR-4.2: The system shall allow the user to securely enter payment details (e.g., card number, expiry, CVV).
Payment details must be securely encrypted during transmission.

FR-4.3: The system shall validate payment details and inform the user of a successful or failed transaction.
In case of failure, the user shall be shown an error message and prompted to try again.

### 4.5. Order Confirmation
FR-5.1: Upon successful order placement, the system shall display an order confirmation page.
The order confirmation page should include:
* Order number
* Product details (name, quantity, price)
* Shipping method selected
* Total cost (including shipping and discounts)
* Estimated delivery date

FR-5.2: The system shall send an order confirmation email to the user.
The email should contain the order summary and expected delivery date.

### 4.6. Admin Notification
FR-6.1: The system shall notify the admin of a new order.
Notifications can be sent via email or updated in the admin dashboard.
Admins can view the order number, products ordered, shipping address, and payment method.

### 4.7. Order History
FR-7.1: The system shall allow users to view their order history.
Users should see past orders along with product names, quantities, and total cost.
Clicking on an order should provide detailed information on each product, shipping method, and payment.

## 5. Non-Functional Requirements

### 5.1 Performance:
Order processing time (from cart to order confirmation) should not exceed 5 seconds under normal load conditions.

### 5.2 Security:
Payment details must be securely encrypted using TLS/SSL encryption.
Compliance with PCI DSS standards for handling payment information.

### 5.3 Usability:
The user interface should be responsive and accessible across mobile and desktop platforms.
The process should be intuitive, with clear guidance through each step (e.g., adding to cart, entering payment details).

### 5.4 Availability:
The order processing system should be highly available, with uptime greater than 99.9%.

## 6. User Stories

### 6.1. User Stories for Cart Management
US-1.1: As a user, I want to add products to my cart so that I can review them before checkout.
US-1.2: As a user, I want to edit my cart so that I can change the quantities or remove items before proceeding to checkout.

### 6.2. User Stories for Promo Code Application
US-2.1: As a user, I want to apply a promo code to my order to receive a discount on my total.
US-2.2: As a user, I want to know immediately if my promo code is valid or invalid.

### 6.3. User Stories for Payment and Order Confirmation
US-3.1: As a user, I want to securely complete my payment so that I can finalize my order.
US-3.2: As a user, I want to receive an order confirmation after placing my order, so I know that my purchase was successful.

### 6.4. User Stories for Admin Notification
US-4.1: As an admin, I want to receive a notification when a new order is placed, so I can process it in a timely manner.

## 7. Acceptance Criteria
For each feature, the following criteria must be met:

* Cart Management:
Users can view, add, edit, and remove items from the cart.
Cart updates automatically when items are modified.

* Promo Code Application:
Valid promo codes apply the correct discount.
Invalid promo codes show a clear error message.

* Shipping Method Selection:
Users can choose a shipping method, and the total cost updates accordingly.

* Payment Gateway Integration:
Payment details are securely transmitted and validated.
Payment success/failure is communicated to the user clearly.

* Order Confirmation:
Users receive an email with an order summary and estimated delivery date.

* Admin Notification:
Admins receive an order notification with all necessary details to process the order.

## 8. Technical Requirements
* Payment Gateway Integration: Stripe, PayPal, or another secure payment processor.
* Email Service: SendGrid or a similar email service for confirmation emails.
* Database: MySQL or PostgreSQL to store order, payment, and user data.

## 9. Glossary
* Cart: A virtual container where users store selected items before proceeding to checkout.
* Promo Code: A code that users can apply to receive a discount.
* Payment Gateway: A service that securely processes online payments.
* Admin Dashboard: A backend interface for administrators to manage and process orders.
