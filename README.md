# Todo List Application

This is a PHP-based Todo List application that allows users to manage their tasks. Users can add, update, and delete tasks, as well as create accounts, log in, and manage their sessions. The application uses MySQL as its database to store user information and tasks.

## Features

- User registration and login
- Add, update, and delete tasks
- Mark tasks as done
- Session management
- Simple and intuitive interface

## Prerequisites

- PHP 8.2 or higher
- MySQL
- A web server (e.g., Apache)
- XAMPP (recommended for local development)

## Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/anmolsharma2704/todo-php.git
    cd todo-php
    ```

2. **Set up the database:**

    - Start your MySQL server.
    - Create a database named `todo`.
    - Create the necessary tables using the following SQL commands:

    ```sql
    CREATE TABLE users (
        id INT AUTO_INCREMENT PRIMARY KEY,
        username VARCHAR(50) NOT NULL UNIQUE,
        password VARCHAR(255) NOT NULL
    );

    CREATE TABLE tasks (
        taskid INT AUTO_INCREMENT PRIMARY KEY,
        username VARCHAR(50) NOT NULL,
        task TEXT NOT NULL,
        done BOOLEAN DEFAULT FALSE,
        FOREIGN KEY (username) REFERENCES users(username)
    );
    ```

3. **Configure the database connection:**

    - Update the `connectdatabase` function in `index.php` and `database.php` to match your MySQL username, password, and server details:

    ```php
    function connectdatabase() {
        return mysqli_connect("localhost", "your_mysql_username", "your_mysql_password", "todo");
    }
    ```

4. **Start the PHP built-in server:**

    Navigate to your project directory and run:

    ```sh
    php -S localhost:4000
    ```

5. **Open the application:**

    Open your web browser and go to `http://localhost:4000`.

## Usage

1. **Register a new user:**

    - Go to the registration page.
    - Enter a new username and password to create an account.

2. **Log in:**

    - Go to the login page.
    - Enter your username and password to log in.

3. **Manage tasks:**

    - Add a new task using the task input field.
    - Mark tasks as done by checking the checkbox next to the task.
    - Delete tasks by selecting them and clicking the delete button.

4. **Log out:**

    - Log out by clicking the logout button to end your session.

## File Structure

todo-php/
├── index.php
├── database.php
├── login.php
├── register.php
├── todo.php
├── css/
│ └── style.css
└── README.md


## Contributing

Contributions are welcome! Please fork this repository and submit a pull request for any features, fixes, or enhancements.
