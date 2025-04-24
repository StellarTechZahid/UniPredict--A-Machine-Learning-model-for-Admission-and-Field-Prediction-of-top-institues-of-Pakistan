# UNI Predict — Machine Learning Model for University Admissions and Program Prediction

UNI Predict is a machine learning model designed to predict university admissions and program selections based on academic records for 8 top universities in Pakistan.

Using **Logistic Regression** for admissions and **Random Forest** for program prediction, the model achieves **90+% accuracy**. It is trained on over **10,000 data points** with **44 features**, collected from top institutes.

A fully functional UI is developed and running locally, with a public release coming soon.

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Dataset](#dataset)
- [Model Architecture](#model-architecture)
- [Installation](#installation)
- [Usage](#usage)
- [UI Integration & Architecture](#ui-integration--architecture)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## Overview

UNI Predict is built on top of advanced ML algorithms designed to provide actionable insights to students looking to apply to universities in Pakistan. The model aims to guide prospective students by predicting their chances of admission and helping them choose the right program based on their academic records.

The project consists of two main components:
1.  **Admission Prediction**: Using **Logistic Regression**, the model predicts whether a student will be admitted to a particular university.
2.  **Program Prediction**: Using **Random Forest** classification, the model predicts which program (out of more than 80 available programs) a student is most likely to enroll in.

The model is trained on data from 8 prestigious universities across Pakistan, ensuring a diverse and comprehensive dataset.

## Features

-   **Admission Prediction**: Predicts the likelihood of a student being admitted to a specific university based on academic performance, including grades, subjects, and other parameters.
-   **Program Prediction**: Predicts the program that a student is most likely to select or be admitted to, considering available program offerings.
-   **High Accuracy**: The model has achieved **90+% accuracy** on local machines, making it a highly reliable tool for prospective students.
-   **Data-Driven Decisions**: Provides students with predictions based on their academic history, helping them make more informed decisions regarding their university applications.

## Technologies Used

-   **Algorithms:**
    -   **Logistic Regression** (for admissions prediction)
    -   **Random Forest Classifier** (for program selection prediction)
-   **Libraries & Frameworks:**
    -   **scikit-learn**: For implementing machine learning algorithms.
    -   **Pandas**: For data manipulation and analysis.
    -   **NumPy**: For numerical computations and array manipulations.
    -   **Matplotlib / Seaborn**: For data visualization.
    -   **Jupyter Notebook**: For development and testing of the model.
-   **Programming Language:** Python

## Dataset

The model is trained on a diverse dataset consisting of **10,042 rows** and **44 columns** of academic records from students applying to the top universities in Pakistan. The features include:
-   **Student Information**: Gender, high school grades, university entrance exam scores, etc.
-   **University Data**: Admission requirements, program preferences, etc.
-   **Target Output**: Admission status (1 for admitted, 0 for not admitted) and the program selected by the student.

This data provides rich insights that enable the model to make accurate predictions based on various factors influencing admissions and program selection.

## Model Architecture

1.  **Data Preprocessing**:
    The dataset was thoroughly cleaned, with missing values imputed and categorical data encoded appropriately. We ensured that the features used for prediction were both relevant and comprehensive.

2.  **Logistic Regression for Admission Prediction**:
    Logistic Regression is used to predict the probability of admission to each of the 8 universities based on a set of input features, such as student grades, entrance exam scores, and more.

3.  **Random Forest Classifier for Program Prediction**:
    A Random Forest Classifier is employed to predict the specific program (out of 80+ programs) a student is most likely to enroll in. This model is well-suited for handling complex and non-linear relationships in the data.

4.  **Model Evaluation**:
    The models were evaluated using accuracy, precision, recall, and F1-score to ensure they perform reliably. Cross-validation was also used to reduce overfitting and improve generalizability.

## Installation

To set up the project on your local machine, follow these steps:

### Prerequisites:
-   **Python 3.x**: Ensure that Python is installed on your system.
-   **pip**: Python package manager for installing dependencies.

### Steps to Install:

1.  Clone the repository:
    ```bash
    git clone [https://github.com/username/uni-predict.git](https://github.com/username/uni-predict.git)
    ```
2.  Navigate to the project directory:
    ```bash
    cd uni-predict
    ```
3.  Install the required packages:
    ```bash
    pip install -r requirements.txt
    ```
    *(Note: You may need to create a `requirements.txt` file listing pandas, numpy, scikit-learn, matplotlib, seaborn, etc.)*

## Usage

1.  **Prepare your data**: Ensure your input data matches the format used during training (e.g., a CSV file or DataFrame with the required 44 features).
2.  **Load the models**: Load the trained Logistic Regression and Random Forest models (e.g., using `joblib` or `pickle`).
3.  **Run Predictions**:
    -   Use the Logistic Regression model for admission prediction.
    -   Use the Random Forest model for program prediction.
    *(Refer to the Jupyter Notebooks or Python scripts in the repository for detailed usage examples.)*

##  UI Integration & Architecture
A fully functional and sleek User Interface (UI) has been developed to provide a seamless experience for users to interact with the UNI Predict system. The UI is currently live on the local machine and will be deployed publicly soon.

### UI Stack
The UI has been built using modern web technologies:

-   **Next.js** – React-based framework for fast, SEO-friendly frontend performance.
-   **Tailwind CSS** – For utility-first responsive and clean styling.
-   **HTML, CSS, JavaScript** – Core technologies for layout and interaction.
-   **REST APIs** – For backend integration and communication between the frontend and machine learning model.

### UI Features
-   **Clean & User-Friendly Design**: The interface follows a minimal, intuitive layout focused on ease of input and understanding.
-   **Interactive Form**: Users can enter their academic details including grades, entrance test scores, and other relevant metrics.
-   **Prediction Display**: After submitting academic details, the system instantly displays admission and program predictions in visually appealing card layouts below the form.
-   **Real-Time Feedback**: Predictions are generated and displayed in real time through REST API calls that fetch model output from the backend.

### Backend & Prediction Architecture
The core architecture of the system comprises the following flow:

1.  **Frontend Form Submission (Client Side)**
    -   Users fill in a detailed academic profile form on the frontend (developed in Next.js and Tailwind CSS).
    -   Upon submission, the data is structured into a JSON object and sent to the backend via a RESTful API.
2.  **API Layer (Server Side)**
    -   The backend API, developed using Python (e.g., Flask/FastAPI), receives the request, validates the data, and routes it to the ML prediction engine.
3.  **Model Invocation (ML Engine)**
    -   **Admission Prediction Engine:**
        -   Uses 8 separate Logistic Regression models, one per university.
        -   Each model processes the academic record and returns a binary prediction (1 for admit, 0 for reject).
    -   **Program Prediction Engine:**
        -   Uses Random Forest classifiers for each university.
        -   These models perform multi-class classification to identify the most likely program among 80+ options.
4.  **Response Formation & Delivery**
    -   The backend aggregates all predictions and returns a structured response to the frontend. The data includes:
        -   Predicted admission status per university
        -   Predicted program name per university
        -   Confidence scores (if applicable)
5.  **Frontend Display**
    -   The frontend dynamically renders the prediction results using stylized card components, showing each university’s admission and predicted program in a compact, readable format.

### Live Preview & Future Scope
**⚙️ Current Status:**
-   The entire UI + Backend prediction system is functioning locally and producing real-time results with high accuracy. Integration between frontend and ML models is complete.

** Next Steps:**
-   Public deployment via platforms like Vercel (frontend) and Render/Heroku or AWS Lambda (for backend ML APIs).
-   Adding data validation, error handling, and confidence visuals to enhance trust and transparency.

** Vision:**
-   Enable high school and intermediate students in Pakistan to make data-driven decisions about university applications using state-of-the-art AI models through a beautiful, intuitive interface.

## Contributing

Contributions are welcome! If you'd like to contribute to the project, please follow these steps:
1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/your-feature-name`).
3.  Make your changes and commit them (`git commit -m 'Add some feature'`).
4.  Push to the branch (`git push origin feature/your-feature-name`).
5.  Open a Pull Request.

Please ensure your code follows the project's coding standards and includes appropriate tests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. *(Note: You need to create a LICENSE file, typically containing the standard MIT License text)*

## Contact

For questions, feature requests, or general inquiries, please contact:
Email: [ahmadzahid50100@gmail.com]
LinkedIn: [(https://www.linkedin.com/in/ahmad-z-a97896286/)]
GitHub: [(https://github.com/StellarTechZahid)]
