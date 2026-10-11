Lab 06: Diabetes Prediction Web Application

Overview
This lab focuses on deploying a machine learning model as a full-stack web application. A pre-trained Logistic Regression model for diabetes classification is served via a FastAPI REST API and accessed through an interactive HTML/JavaScript user interface[cite: 4, 5, 6].

---

Folder Structure

Lab-06/
|
|-- index.html
|-- main.py
|-- Mymdoel.pkl
|
`-- README.md

---

Components

1. Machine Learning Model (Mymdoel.pkl)
- Model Type: LogisticRegression[cite: 6]
- Target Classes: 0 (Not Diabetic) and 1 (Diabetic)[cite: 5, 6]
- Required Input Features:
  - Glucose[cite: 4, 5, 6]
  - BloodPressure[cite: 4, 5, 6]
  - Insulin[cite: 4, 5, 6]
  - BMI[cite: 4, 5, 6]
  - DiabetesPedigreeFunction[cite: 4, 5, 6]
  - Age[cite: 4, 5, 6]

2. Backend API (main.py)
- Framework: FastAPI with Uvicorn[cite: 5]
- Middleware: CORSMiddleware enabled for cross-origin requests[cite: 5]
- Endpoints:
  - GET / : Returns API status and docs link[cite: 5]
  - GET /health : Health check endpoint returning status ok[cite: 5]
  - POST /predict : Accepts clinical input data and returns predicted label, class description, and prediction probability[cite: 5]

3. Frontend Interface (index.html)
- Responsive form with input fields for all 6 clinical features[cite: 4]
- JavaScript fetch function that sends a JSON POST request to http://localhost:8000/predict[cite: 4]
- Displays real-time prediction output directly on the webpage[cite: 4]

---

Setup and Execution Instructions

1. Install Dependencies
pip install fastapi uvicorn pandas scikit-learn

2. Start the Backend API
Run the following command in the Lab-06 directory:
python -m uvicorn main:app --reload --port 8000

The API will start at http://localhost:8000
Interactive documentation is available at http://localhost:8000/docs[cite: 5]

3. Launch the Application
Open index.html in any web browser[cite: 4].
Enter the diagnostic values and click Predict to view the classification result[cite: 4].
