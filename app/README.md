# Fashion MNIST Classifier Web App

This is a Streamlit web application for classifying Fashion MNIST images using a pre-trained CNN model.

## Features
- Upload a 28x28 grayscale image (PNG or JPG).
- Display the uploaded image.
- Predict the fashion category with confidence score.
- Error handling for invalid images.

## Local Setup and Run

### Prerequisites
- Python 3.9 installed.
- Virtual environment tool (built-in with Python).

### Setup Virtual Environment
You can set up the virtual environment either in the `app` folder (recommended for isolation) or in the root project folder (for sharing with the notebook). You can also set up both if needed, but this is generally not recommended.

#### Option 1: In the `app` folder (Recommended)
1. Navigate to the `app` folder:
   ```
   cd Image-Classification-Fashion-MNIST\app
   ```

2. Create a virtual environment in the `.venv` folder:
   ```
   python -m venv .venv
   ```

3. Delete broken folder: (optional) then rerun step 2
   ```
   Remove-Item -Recurse -Force .venv
   ```  

4. Activate the virtual environment:
   - On Windows: `.venv\Scripts\activate` old, `.\.venv\Scripts\Activate.ps1` new
   - On macOS/Linux: `source .venv/bin/activate`

5. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

#### Option 2: In the root project folder (Shared with notebook)
This option sets up the virtual environment in the root `.venv` folder.
This makes the environment accessible from both the root directory (e.g., for running the notebook) and the `app` subfolder, as long as you activate it from the appropriate location.

1. Navigate to the root project folder:
   ```
   cd Image-Classification-Fashion-MNIST
   ```

2. Create a virtual environment in the `.venv` folder:
   ```
   python -m venv .venv
   ```

3. Activate the virtual environment:
   - On Windows: `.venv\Scripts\activate`
   - On macOS/Linux: `source .venv/bin/activate`

4. Install dependencies:
   ```
   pip install -r app/requirements.txt
   ```

### Run Locally
1. Navigate to the `app` folder if not already there:
   ```
   cd Image-Classification-Fashion-MNIST\app
   ```

2. Ensure the virtual environment is activated.

   - On Windows: `.venv\Scripts\activate`
   - On macOS/Linux: `source .venv/bin/activate`

3. Run the app:
   ```
   streamlit run app.py
   ```
4. Open your browser to `http://localhost:8501`.

## Docker Setup and Run

### Prerequisites
- Docker installed.

### Build and Run
1. Navigate to the `app` folder.
    ```
   cd Image-Classification-Fashion-MNIST\app
   ```

2. Ensure the virtual environment is activated.

   - On Windows: `.venv\Scripts\activate`
   - On macOS/Linux: `source .venv/bin/activate`

3. Ensure the Docker Desktop is activated.

4. Build the Docker image: (Skip this if Docker image have already been built once on your computer)
   ```
   docker build -t fashion-mnist-app .
   ```
5. Run the container:
   ```
   docker run -p 8501:8501 fashion-mnist-app
   ```
6. Open your browser to `http://localhost:8501`.

## Notes
- The pre-trained model (`trained_model.keras`) must be in the `trained_model` folder.
- Ensure uploaded images are 28x28 grayscale for best results; the app will resize and convert them.
- For production, consider adding authentication or rate limiting.
