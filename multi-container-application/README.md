This is a simple containerized web application 
app.py file : 
from flask import Flask
app = Flask(__name__)

@app.route("/")
def home():
    return "Hello, Docker!"

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)

------------------------------------------------------------------------------------------

Docker file:

FROM python:3.9
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
EXPOSE 5000
CMD ["python", "app.py"]

--------------------------------------------------------------------------------------------

To run:
1) docker build -t flask-app .
2) docker run -p 5000:5000 flask-app

Note: Docker desktop(deamon) should be running in the background 


