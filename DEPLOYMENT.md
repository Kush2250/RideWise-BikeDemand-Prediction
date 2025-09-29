# Deployment Guide for RideWise

This guide provides instructions for deploying the RideWise bike rental prediction application to various platforms.

## Local Deployment

1. Clone the repository:
   ```
   git clone <your-repository-url>
   cd RideWise
   ```

2. Install dependencies:
   ```
   pip install -r requirements.txt
   ```

3. Run the application:
   ```
   streamlit run app.py
   ```

## Streamlit Cloud Deployment

1. Push your code to GitHub:
   ```
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin <your-github-repo-url>
   git push -u origin main
   ```

2. Go to [Streamlit Cloud](https://streamlit.io/cloud) and sign in with your GitHub account.

3. Click "New app" and select your repository, branch, and the main file (app.py).

4. Click "Deploy" and wait for the deployment to complete.

## Heroku Deployment

1. Create a `Procfile` in the root directory:
   ```
   echo "web: streamlit run app.py --server.port=$PORT" > Procfile
   ```

2. Create a `runtime.txt` file:
   ```
   echo "python-3.9.16" > runtime.txt
   ```

3. Install Heroku CLI and login:
   ```
   heroku login
   ```

4. Create a new Heroku app:
   ```
   heroku create ridewise-app
   ```

5. Push to Heroku:
   ```
   git push heroku main
   ```

## Docker Deployment

1. Create a `Dockerfile`:
   ```
   FROM python:3.9-slim

   WORKDIR /app

   COPY requirements.txt .
   RUN pip install -r requirements.txt

   COPY . .

   EXPOSE 8501

   CMD ["streamlit", "run", "app.py"]
   ```

2. Build and run the Docker image:
   ```
   docker build -t ridewise-app .
   docker run -p 8501:8501 ridewise-app
   ```

## AWS Elastic Beanstalk Deployment

1. Install the EB CLI:
   ```
   pip install awsebcli
   ```

2. Initialize EB application:
   ```
   eb init -p python-3.9 ridewise-app
   ```

3. Create an environment and deploy:
   ```
   eb create ridewise-env
   ```

4. Open the application:
   ```
   eb open
   ```

## Troubleshooting

- If you encounter issues with dependencies, ensure your `requirements.txt` file is up to date.
- For deployment errors, check the logs of the respective platform.
- Ensure that the model files (`ridewise_model.pkl` and `x_columns.pkl`) are included in your repository.