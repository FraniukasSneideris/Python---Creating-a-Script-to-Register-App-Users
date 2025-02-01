# Python-Creating-a-Script-to-Register-App-Users

This project enhances a simple user registration system by improving its modularity and functionality. The original idea comes from the DataCamp project "Creating Functions to Register App Users" which focuses on validating and registering individual users. This project expands on that by introducing Object-Oriented Programming (OOP), enhancing the structure, introducing Common-Line Interface (CLI) and allowing bulk user registration from a CSV file.

## Project Overview

Initially, the goal of the project was to create two functions that validate user inputs (name, email, password) and register them. The objective was to ensure that user input met certain validation criteria before account creation. The system used helper functions to validate user data and raise errors if anything was wrong. 

However, I wanted to improve the system by making it more modular, maintainable, and flexible. Here's what I did:

- I refactored the existing validation functions into a class called `Validate`.
- Then, I created a new class `RegisterUser` that inherited from `Validate` and added the registration logic.
- Finally, I added a third class, `Bulk`, to enable bulk user registration from a CSV file, making the system more flexible for handling multiple users at once.

## Features

- **OOP Structure**: The project is built with Object-Oriented Programming principles for easy extension and better maintainability.
- **CLI Support**: A command-line interface (CLI) was added for easy user interaction. You can validate and register users individually or in bulk from a CSV file.
- **User Validation**: The system validates user input for name, email, and password before registration.
- **Bulk Registration**: Allows registration of multiple users from a CSV file, making it easier to onboard users in large numbers.

## Classes and Methods

### `Validate` Class

This class encapsulates the logic for validating user data. It includes methods for validating:
- **Name**: Checks if the name is a string and at least 3 characters long.
- **Email**: Validates the email format, ensuring it includes an "@" symbol and an appropriate domain.
- **Password**: Ensures the password has at least one uppercase letter, one digit, and is longer than 8 characters.

### `RegisterUser` Class

This class inherits from `Validate` and adds functionality for user registration. It includes methods for:
- **validate_user**: Validates the user input by calling the validation methods from the `Validate` class.
- **register_user**: Registers the user if all validations pass, returning a dictionary with the user's details.

### `Bulk` Class

This class allows for bulk user registration from a CSV file. It includes methods for:
- **open_user_data**: Reads the CSV file containing user data.
- **process_user_data**: Processes the raw data from the CSV file into a usable format.
- **register_bulk**: Validates and, if validation is completed, registers users from the processed CSV data. 

## How to Use

You can run the system from the command line to validate or register users individually, or to process bulk user registrations from a CSV file. If you wish to try the bulk registration, feel free to use the files I've added to the repository: *user_data.csv* (clean data), or *tampered_user_data_(...).csv* (user_data.csv with alterations in name, email and password respectively).

### Validating a Single User
*python register_user.py "John Doe" "johndoe@example.com" "Password123" validate*

### Registering a Single User
*python register_user.py "John Doe" "johndoe@example.com" "Password123" register*

### Bulk registration
*python register_user.py --bulk --file user_data.csv* 

### Dependencies
- Python 3.x
- argparse (standard library)

### Enhancements
- Modular Design: The system's structure is improved using OOP principles, making it easier to expand or modify in the future.
- CSV Support: Added functionality for bulk user registration, making it scalable for applications needing to register many users at once.

## Conclusion
This project started as a simple user registration system and evolved into a more flexible, scalable solution through modular programming, OOP, and bulk registration support. It provides a solid foundation for handling user registration in small to medium-sized applications, and can easily be extended or integrated into larger systems.
