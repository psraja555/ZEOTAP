# ZEOTAP
Application 1: Rule Engine with AST
Description
This application implements a rule engine that determines user eligibility based on attributes like age, department, income, and spend. It uses an Abstract Syntax Tree (AST) to represent and evaluate rules dynamically.

Features
Create rules from string expressions.
Combine multiple rules into one AST.
Evaluate user data against rules.
Modify existing rules dynamically.
Tech Stack
Backend: Python
API: Flask (Optional)
Database: PostgreSQL or MongoDB
Version Control: GitHub
Setup Instructions
Clone the Repository:

bash
git clone https://github.com/yourusername/rule-engine-ast.git
cd rule-engine-ast
Install Dependencies:

bash

pip install -r requirements.txt
Database Setup:

PostgreSQL:
**sql**

CREATE TABLE rules (
    id SERIAL PRIMARY KEY,
    rule_string TEXT,
    ast_json JSONB
);
MongoDB: Configure the connection in config.py.
Run the Application:

bash

python app.py
Run Tests:

bash

python -m unittest test_rule_engine.py
Build Script
To package the application for deployment, use the provided Makefile:

bash

# To install dependencies
make install

# To run the application
make run

# To run the tests
make test
Configurations
Database and API configurations are stored in config.py. Customize these settings before deployment:
python

DB_TYPE = 'postgresql'  # Change to 'mongodb' if using MongoDB
DB_HOST = 'localhost'
DB_PORT = 5432
Security & Performance Enhancements
Input Validation: Ensure that rule strings are properly sanitized to prevent injection attacks.
Authentication: Add JWT-based token authentication for API calls (for Flask API).
Performance Optimization: Use database indexes for faster querying on the rule evaluation.

-------------------------------------------------------------------------------------------------------------------------------------------------------

Application 2: Real-Time Data Processing System for Weather Monitoring
Description
This system fetches real-time weather data for Indian metros from the OpenWeatherMap API, calculates daily weather summaries, and triggers alerts based on configurable thresholds.

Features
Fetches weather data at configurable intervals.
Converts temperature from Kelvin to Celsius (or Fahrenheit).
Calculates daily summaries (average, max, min temperature).
Configurable alert thresholds.
Visualizes weather trends.
Tech Stack
Backend: Python
API: OpenWeatherMap API
Database: PostgreSQL or MongoDB
Visualization: Matplotlib, Plotly, or Dash
Version Control: GitHub
Setup Instructions
Clone the Repository:

bash

git clone https://github.com/yourusername/weather-monitoring-system.git
cd weather-monitoring-system
Install Dependencies:

bash

pip install -r requirements.txt
Database Setup:

PostgreSQL:
**sql**

CREATE TABLE weather_summary (
    id SERIAL PRIMARY KEY,
    city VARCHAR(50),
    date DATE,
    avg_temp FLOAT,
    max_temp FLOAT,
    min_temp FLOAT,
    dominant_condition VARCHAR(50)
);
MongoDB: Configure the connection in config.py.
Configure API Key:

Sign up at OpenWeatherMap.
Add your API key to config.py:
**python**

API_KEY = 'your_api_key_here'
Run the Application:

bash

python weather_monitor.py
Run Tests:

bash

python -m unittest test_weather_monitor.py
Build Script
To package the application for deployment, use the provided Makefile:

bash

# To install dependencies
make install

# To run the application
make run

# To run the tests
make test
Configurations
API key, thresholds, and database configurations are in config.py:
**python**

API_KEY = 'your_api_key_here'
DB_TYPE = 'postgresql'
TEMP_THRESHOLD = 35.0
Security & Performance Enhancements
API Key Management: Use environment variables to store the OpenWeatherMap API key (dotenv library).
Rate Limiting: Ensure that the API is called within the free-tier limits to avoid excessive requests.
Alerts via Email: Integrate with an email service (e.g., SMTP or SendGrid) to send alerts via email.
Non-Functional Requirements
Security
Input Validation: Sanitize all inputs (API calls, rule strings) to prevent injection attacks.
Authentication: Use OAuth or JWT for API authentication.
Sensitive Data: Use environment variables for sensitive data like API keys and database credentials.
Performance
Efficient Data Storage: Use database indexing to improve query performance for large datasets.
Caching: Implement caching for repeated API calls to reduce load on the weather API.
Scalability: Design the system to handle higher request loads by using multi-threading or asynchronous requests for fetching weather data.
