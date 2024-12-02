# Car Rental Website

## Overview

The **Car Rental Website** is a responsive, feature-rich platform designed to simplify car rentals in Kelowna and Vancouver. Users can search for cars, upload licenses, make secure bookings, and receive instant confirmations with a unique booking number. The admin panel provides tools to manage inventory, bookings, and maintenance schedules efficiently.

---

## Features

### **Frontend**
- **Dynamic Search and Filters**:
  - Filter cars by location, date range, car type, and price.
- **Car Listings**:
  - Browse cars with detailed cards including images, prices, and features.
- **Booking System**:
  - Upload a driver’s license securely.
  - Receive instant booking confirmations with a unique booking number.
- **Responsive Design**:
  - Built with Tailwind CSS for a seamless experience on all devices.

### **Backend**
- **APIs**:
  - Search available cars with filters.
  - Generate bookings and store customer data.
  - Securely upload license images to AWS S3.
- **Admin Panel**:
  - Manage car inventory (add/edit/delete cars).
  - Block dates for maintenance.
  - View booking history with details.

---

## Tech Stack

### **Frontend**
- **Framework**: React
- **Styling**: Tailwind CSS
- **State Management**: Redux

### **Backend**
- **Framework**: Node.js with Express.js
- **Database**: PostgreSQL (Amazon RDS)
- **Authentication**: AWS Cognito

### **Storage**
- **File Uploads**: AWS S3 for secure license storage.

### **Payment**
- **Integration**: Square API for secure transactions.

### **Hosting**
- **Frontend**: AWS Amplify
- **Backend**: AWS Lambda + API Gateway

---

## Database Schema

### **Tables**
1. **Cars**:
   - 'id': Primary Key
   - 'make', 'model', 'year', 'features', 'location', 'price_per_day'
   - 'availability': Array of blocked dates.
2. **Bookings**:
   - 'id': Primary Key
   - 'customer_name', 'email', 'phone'
   - 'car_id': Foreign Key referencing 'Cars'
   - 'start_date', 'end_date'
   - 'license_path': Path to S3 file
   - 'booking_number'
3. **Admin**:
   - 'id': Primary Key
   - 'username', 'password_hash'

---

## How It Works

### **User Flow**
1. Select a location (Kelowna/Vancouver).
2. Search for cars based on date range and filters.
3. View car details and click "Book Now."
4. Fill out the booking form with personal details and upload a license.
5. Make a secure payment via Square API.
6. Receive a booking confirmation with a unique number.

### **Admin Flow**
1. Log in to the admin panel.
2. Manage car inventory (add, edit, delete).
3. Block dates for maintenance or special bookings.
4. View and manage all bookings.

---

## Setup and Installation

### **Frontend**
1. Clone the repository:
   git clone https://github.com/your-username/car-rental-website.git
   cd car-rental-website
2. Install dependencies:
   npm install
3. Start the development server:
   npm start

### **Backend**
1. Set up the Node.js backend:
   cd backend
   npm install
2. Configure environment variables:
   - Add your AWS, Square API, and database credentials.
3. Start the server:
   npm start

---

## Future Enhancements
- Add multi-language support.
- Expand to additional locations.
- Implement user accounts for returning customers.
- Integrate advanced analytics with AWS Pinpoint.

---

## License
This project is licensed under the [MIT License](LICENSE).
