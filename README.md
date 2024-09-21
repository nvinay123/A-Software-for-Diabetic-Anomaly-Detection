# A-Software-for-Diabetic-Anomaly-Detection
The system is a Flask-based web application that allows users to detect potential anomalies in diabetic patient data. It supports both single-instance and batch analysis via an autoencoder model. Users must be authenticated to use the system, with options to register or log in. The front-end utilizes Bootstrap for styling and responsiveness.

1. HTML Templates:
10.html (Analyze Single Instance):

This template provides a form for analyzing a single instance of patient data. The form collects various inputs such as pregnancies, glucose level, blood pressure, insulin, BMI, etc., and submits them to the server for analysis.
11.html (Analysis Result):

This template displays the results of the single instance analysis, showing whether the instance is anomalous or not based on Mean Squared Error (MSE).
index.html (Home Page):

Acts as the landing page of the application with options to analyze a single instance or upload a dataset for batch analysis. It also includes navigation elements for user authentication (Login, Logout).
login.html:

A login page where users can input their username and password to access the system.
register.html:

A registration page where new users can create an account.
result.html (Analysis Results):

Displays the results of the dataset analysis, marking rows with anomalies and suggesting further diagnosis for those cases.
2. Backend (app.py):
Flask Application:

Manages routing, form processing, and rendering templates. It also handles user authentication (login, registration), dataset processing, and anomaly detection.
Forms:

Uses Flask-WTF to define forms for login, registration, and analysis inputs.
Example: AnalyzeInstanceForm collects inputs for analyzing a single instance.
Machine Learning:

The system uses an Autoencoder Neural Network to detect anomalies in patient data. The model is trained using TensorFlow/Keras and uses a pre-determined threshold for determining anomalies.
Anomaly Detection Logic:

The app loads a dataset, scales the features using MinMaxScaler, and uses the autoencoder to reconstruct the input data. It calculates Mean Squared Error (MSE) to detect anomalies. If the error exceeds a certain threshold, it flags the instance as anomalous.
File Uploads:

The user can upload a CSV file containing patient data, which is then processed and analyzed for anomalies in batch mode.
3. User Authentication:
Users can register and log in to the system using hashed passwords (generate_password_hash, check_password_hash). Sessions are used to track logged-in users.
