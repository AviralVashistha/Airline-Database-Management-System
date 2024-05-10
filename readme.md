# Flight Management System (DBMS Project)

This is a database management system (DBMS) project for managing flights, passengers, tickets, transactions, and related entities.

## Database Schema

The project's database schema includes the following tables:

### `airport`

- `airport_code`: INT (Primary Key)
- `name`: VARCHAR(50)
- `city`: VARCHAR(50)
- `state`: VARCHAR(50)
- `country`: VARCHAR(50)

### `admin`

- `admin_id`: VARCHAR(50) (Primary Key)
- `admin_name`: VARCHAR(50)
- `contact`: VARCHAR(50)
- `address`: VARCHAR(50)
- `email_id`: VARCHAR(50)
- `age`: INT
- `airport_code`: INT (Foreign Key references `airport(airport_code)`)

### `airplane`

- `airplane_id`: INT (Primary Key)
- `flight_date`: INT
- `departure`: VARCHAR(50)
- `arrival`: VARCHAR(50)
- `airport_code`: INT (Foreign Key references `airport(airport_code)`)

### `airplane_type`

- `airplane_id`: INT (Primary Key, Foreign Key references `airplane(airplane_id)`)
- `capacity`: VARCHAR(50)
- `airplane_weight`: VARCHAR(50)
- `company`: VARCHAR(50)

### `Passenger`

- `passenger_id`: VARCHAR(50) (Primary Key)
- `passenger_name`: VARCHAR(50)
- `age`: INT
- `gender`: VARCHAR(10)
- `contact`: VARCHAR(20)
- `address`: VARCHAR(50)

### `ticket`

- `ticket_id`: VARCHAR(50) (Primary Key)
- `passenger_id`: VARCHAR (Foreign Key references `Passenger(passenger_id)`)
- `booking_date`: INT
- `availability_status`: VARCHAR (10)
- `class`: VARCHAR (50)
- `departure_loc`: VARCHAR (50)
- `arrival_loc`: VARCHAR (50)
- `seat_no`: INT
- `airplane_id`: INT (Foreign Key references `airplane(airplane_id)`)
- `amount`: INT

### `transaction`

- `transaction_id`: VARCHAR(50) (Primary Key)
- `ticket_id`: VARCHAR (50) (Foreign Key references `ticket(ticket_id)`)
- `booking_date`: INT
- `transaction_mode`: VARCHAR(50)
- `status`: VARCHAR(50)
- `amount`: INT

## Views

### `Flight_Details`

- Provides details about flights including airplane capacity, weight, and company.

### `Transaction_Summary`

- Summarizes transaction details including ticket and passenger information.

## Triggers

- `update_availability`: Updates ticket availability status to 'Booked' after a successful transaction.
- `insert_transaction`: Automatically inserts a transaction record when a new ticket is booked.

## Stored Procedure

### `GetPassengerDetails`

- Retrieves and displays details of passengers.

## Queries

Several SQL queries are provided for retrieving information from different tables.

## Modifications

The README also includes modifications made to the database schema, such as creating and dropping tables, altering table structures, and adding views, triggers, and stored procedures. One can create and remove views and triggers by running the code given just after triggers and views.
