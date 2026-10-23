#K8s_Project

Real-Time Chat Application
Welcome to the Full Stack Realtime Chat App project, where we're building a scalable and secure real-time chat experience using the latest technologies. Whether you're a seasoned developer or a beginner, we invite you to contribute and be a part of this exciting journey!

Table of Contents
Introduction
Features
Tech Stack
Getting Started
Building the Backend
Running the Application
Contributing
Future Plans
License
📝 Introduction
This project aims to provide a real-time chat experience that's both scalable and secure. With a focus on modern technologies, we're building an application that's easy to use and maintain.

✨ Features
Real-time Messaging: Send and receive messages instantly using Socket.io
User Authentication & Authorization: Securely manage user access with JWT
Scalable & Secure Architecture: Built to handle large volumes of traffic and data
Modern UI Design: A user-friendly interface crafted with React and TailwindCSS
Profile Management: Users can upload and update their profile pictures
Online Status: View real-time online/offline status of users
🛠️ Tech Stack
Backend: Node.js, Express, MongoDB, Socket.io
Frontend: React, TailwindCSS
Containerization: Docker
Orchestration: Kubernetes (planned)
Web Server: Nginx
State Management: Zustand
Authentication: JWT
Styling Components: DaisyUI
🔧 Prerequisites
Node.js (v14 or higher)
Docker (for containerizing the app)
Git (to clone the repository)
📝 Environment Configuration
Create a .env file in the root directory with the following configuration:

# Database Configuration
MONGODB_URI=mongodb://root:admin@mongo:27017/chatApp?authSource=admin&retryWrites=true&w=majority

# JWT Configuration
JWT_SECRET=your_jwt_secret_key

# Server Configuration
PORT=5001
NODE_ENV=production
Note:

Replace your_jwt_secret_key with a strong secret key
For local development without Docker, change MONGODB_URI to mongodb://localhost:27017/chatApp
You can use command ```echo "Text what you want" | base64
Clone the Repository
git clone https://github.com/iemafzalhassan/full-stack_chatApp.git
🏗️ Build and Run the Application

Follow these steps to build and run the application:

Build & Run the Containers:
cd full-stack_chatApp
docker-compose up -d --build
Access the application in your browser:
http://localhost
🛠️ Getting Started
Follow these simple steps to get the project up and running on your local Host using docker.

git clone https://github.com/iemafzalhassan/full-stack_chatApp.git
cd full-stack_chatApp
Create a Docker network:
docker network create full-stack
🛠️ Building the Frontend
cd frontend
docker build -t full-stack_frontend .
Run the Frontend container:
docker run -d --network=full-stack  -p 5173:5173 --name frontend full-stack_frontend:latest
The frontend will now be accessible on port 5173.
Run the MongoDB Container:
docker run -d -p 27017:27017 --name mongo mongo:latest
🛠️ Building the Backend
cd backend
Build the Backend image:
docker build -t full-stack_backend .
Run the Backend container:
docker run -d --network=full-stack --add-host=host.docker.internal:host-gateway -p 5001:5001 --env-file .env full-stack_backend
This will build and run the backend container, exposing the backendAPI on port 5001.
Backend API: http://localhost:5001

To Verify the conncetion between backend and databse:
docker-compose logs -f
Once the backend and frontend containers are running, you can access the application in your browser:
Frontend: http://localhost

You can now interact with the real-time chat app and start messaging!
