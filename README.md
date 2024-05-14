# User Login-Signup System

A robust user authentication system implemented using PHP, MySQL, HTML, and CSS, adhering to the MVC architecture principles, with an emphasis on security and comprehensive error handling.

## Features

- User Registration
- User Login
- User Logout
- Secure password handling with hashing
- Session management
- Error handling and display

## Installation

1. **Clone the repository:**

    ```sh
    git clone https://github.com/your-username/repo-name.git
    cd repo-name
    ```

2. **Database setup:**

    - Create a database and import the provided SQL file (`database.sql`) to set up the required tables.
    - Update the database configuration in `includes/dbh.inc.php`:

    ```php
    <?php
    $dsn = 'mysql:host=your_host;dbname=your_dbname';
    $username = 'your_username';
    $password = 'your_password';

    try {
        $pdo = new PDO($dsn, $username, $password);
        $pdo->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
    } catch (PDOException $e) {
        die('Connection failed: ' . $e->getMessage());
    }
    ?>
    ```

3. **Configure session settings:**

    Ensure the session is properly configured in `includes/config_session.inc.php`:

    ```php
    <?php
    session_start();
    ?>
    ```

## Usage

1. **Start the server:**

    You can use a local development server or a web server like Apache or Nginx. For a simple PHP server, navigate to the project directory and run:

    ```sh
    php -S localhost:8000
    ```

2. **Access the application:**

    Open your web browser and go to `http://localhost:8000` to use the login-signup system.

## File Structure

- `index.php`: The main entry point of the application.
- `includes/`
  - `config_session.inc.php`: Session configuration.
  - `dbh.inc.php`: Database connection handling.
  - `login.model.inc.php`: Login-related database operations.
  - `login.control.inc.php`: Login controller logic.
  - `signup.model.inc.php`: Signup-related database operations.
  - `signup.control.inc.php`: Signup controller logic.
  - `login.view.inc.php`: Login view logic.
  - `signup_view.inc.php`: Signup view logic.
  - `login.inc.php`: Handles login requests.
  - `signup.inc.php`: Handles signup requests.
  - `logout.inc.php`: Handles logout requests.
- `css/`
  - `style.css`: Stylesheet for the application.

## Security

- Passwords are hashed using `password_hash()` and verified using `password_verify()`.
- Sessions are managed securely with session IDs.
- Proper input validation and error handling.

## Contributions

Contributions are welcome! Please fork the repository and submit a pull request for any improvements.
