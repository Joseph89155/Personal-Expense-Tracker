# Personal Expense Tracker
---
## Overview

The Personal Expense Tracker is a web application designed to help individuals manage their financial transactions efficiently. This application allows users to create, view, and manage their transactions in one central place. Additionally, users can visualize their spending and income trends through intuitive charts, providing a comprehensive overview of their financial habits.

### Why Use This Application?

Keeping track of your expenses and income, whether through credit cards or cash, can be challenging. The Personal Expense Tracker simplifies this process by giving you:

- **A personal profile**: Securely manage and access your financial data.
- **Transaction tracking**: Record your income and expenses with relevant categories and descriptions.
- **Transaction visualization**: Gain insights into your spending habits through charts.
- **Improved financial overview**: Get a complete picture of your finances in one place.

---

## Features

### 1. User Profiles
- Secure authentication and personal account management.
- User-specific data storage to ensure privacy.

### 2. Transaction Management
- Add, update, and delete transactions easily.
- Categorize transactions for better organization (e.g., salary, bills, food, vacation).
- Filter transactions based on date range, category, or type (income/expense).

### 3. Data Visualization
Dynamic charts for analyzing:
  - Income vs. Expenses.
  - Spending trends over time.
  - Breakdown by categories.

### 4. Import/Export Functionality
Import and export transactions in csv format, registered for external use or record-keeping.

### 5. Responsive Design
Responsive interface for use on desktop.

---

## Project Structure

The project follows the **Model-View-Template (MVT)** architecture of Django. Below is an overview of the structure:

### 1. **`expenses` App**
This is the core app that handles all functionalities related to expense tracking.

- **`models.py`**: Defines the database models (e.g., `Transaction`, `Category`).
- **`views.py`**: Contains the business logic for handling requests and rendering templates.
- **`forms.py`**: Handles form creation and validation for transaction input.
- **`urls.py`**: Routes URLs to the corresponding views.
- **`resources.py`**: Handles export logic for CSV files.
- **`templates/`**: Contains the HTML templates used for rendering pages. It is divived in main template and partials.
  - `base.html`: The base template used across the app.
  - `transactions.html`: Page for listing and managing transactions.
  - `charts.html`: Page for visualizing financial data.
  - `home.html`: Homepage of the website with an overview.
  - `signup.html`: Page for signign up.
  - `welcome.html`: Page to log in.
  - `feedback.html`: Page to give a feedback about the platform and with contact section.
  -  **`partials/`**: Contains all the partial HTML templates relative to main ones, plus the ones related to the functionalities of the platform such as import,export...

### 2. **Static Files**
- **CSS**: Custom styles and scripts to enhance the UI/UX.
- **Images**: Used for storing the logo.

### 3. **Middleware and Security**
- CSRF protection for form submissions.
- Authentication middleware to restrict access to personal data.

---
Loging and Signup Page
![Login and Sign up page](https://github.com/user-attachments/assets/f6ac21fb-849f-4ad6-8190-42987b37d486)

Sing up Page
![Sign up](https://github.com/user-attachments/assets/5f390f0f-7c56-4158-ae6d-3e4cc094cfc4)

Login Page
![Login](https://github.com/user-attachments/assets/6a8315a6-8bbb-4030-8311-439cfc5a6590)

Homepage
![1](https://github.com/user-attachments/assets/fbe9fc1b-9563-47ed-a9ae-61f976dda8fd)

## How to Use

### 1. Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/martinaserandrei/expense_tracker.git
   ```
2. Navigate to the project directory:
   ```bash
   cd expense_tracker
   ```
3. Create and activate a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate
   ```
4. Enter in expense_tracker and install dependencies:
   ```bash
   cd expense_tracker
   pip install -r requirements.txt
   ```

### 2. Run the Server
1. Apply database migrations:
   ```bash
   python manage.py migrate
   ```
2. Start the development server:
   ```bash
   python manage.py runserver
   ```
3. Open the application in your browser at `http://127.0.0.1:8000/` (browser compatible: Google Chrome).
4. Create a user by navigating to the signup page in the application.
5. Log in with the newly created user account to access the application.

### 3. Generate Categories
1. Stop the development server by pressing `Ctrl+C` in the terminal.
2. Run the following command to generate default categories:
   ```bash
   python manage.py generate_categories
   ```
3. Restart the development server:
   ```bash
   python manage.py runserver
   ```

After completing these steps, you will be able to choose categories when uploading a file from your banking service!.


### 4. Usage
- **Log in**: Access your dashboard.
- **Manage transactions**: Add, update, and delete transactions.
- **Visualize data**: Use the charts section to analyze your finances.
- **Give a feedback**: Leave a feedback or report an issue.
- **Export data**: Export your transaction in a .csv file.
- **Import files**: Import files in two ways: either by using a recognized format (.csv) or by selecting the 'Banking Service' option to access files from your banking service, if it is among the supported ones.

*Remark*: If you want to try the 'Upload a file' option in the parent folder there is a file called 'new_transactions.csv' that you can upload and it should work!

---

## Technologies Used

- **Backend**: Django (Python)
- **Frontend**: HTML, HTMX, CSS, Bootstrap, JavaScript
- **Database**: SQLite
- **Visualization**: Plotly.js
