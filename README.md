# Deep Learning Model Deployment with Docker

## Description
In this lab, I successfully deployed a deep learning object detection application using Docker. I packaged the FastAPI-based application along with a YOLOv3-tiny model and containerized it for production deployment. The model has now moved out of the Jupyter notebook environment and is exposed to external traffic, just like real-world applications!

## Project Overview
This project demonstrates the complete pipeline of deploying a machine learning model from development to production using Docker containerization. The application provides object detection capabilities through a FastAPI web service that can handle external requests.

## Technologies Used
- **Python 3.11** - Base runtime environment
- **Docker** - Containerization platform
- **FastAPI** - Web framework for building APIs
- **Uvicorn** - ASGI server for running FastAPI
- **YOLOv3-tiny** - Pre-trained object detection model
- **CVLib** - Computer vision library for model inference

## Project Structure
```
mlepc1w1_cloud/
├── app/
│   ├── __init__.py          # Module initialization
│   └── main.py              # FastAPI application with endpoints
├── .cvlib/                  # Pre-trained YOLOv3-tiny model
├── requirements.txt         # Python dependencies
├── Dockerfile              # Docker container configuration
└── README.md               # Project documentation
```

## Features Implemented
- ✅ **Object Detection API**: RESTful endpoints for image processing
- ✅ **FastAPI Integration**: Modern, fast web framework with automatic API documentation
- ✅ **Docker Containerization**: Complete application packaging with dependencies
- ✅ **Pre-trained Model**: YOLOv3-tiny for efficient object detection
- ✅ **Interactive API Documentation**: Built-in Swagger UI at `/docs`
- ✅ **Production Ready**: Configured for external traffic handling

## Installation & Deployment

### Prerequisites
- Docker installed and running
- Git (for cloning the repository)

### Quick Start
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/mlepc1w1_cloud.git
cd mlepc1w1_cloud

# Build the Docker image
docker build -t w1_lab .

# Run the container
docker run -d --name w1_lab -p 80:80 w1_lab

# Verify container is running
docker ps
```

### Access the Application
- **Main Application**: http://localhost:80
- **API Documentation**: http://localhost:80/docs
- **Alternative Docs**: http://localhost:80/redoc

## Container Management

### Start/Stop the Container
```bash
# Stop the container
docker stop w1_lab

# Start the container
docker start w1_lab

# Remove the container (when stopped)
docker remove w1_lab
```

### View Running Containers
```bash
docker ps
```

## Usage
1. Navigate to http://localhost:80 in your web browser
2. Use the FastAPI interface at http://localhost:80/docs to interact with the API
3. Upload images through the web interface to test object detection
4. The application will process images and return detected objects with bounding boxes

## Docker Hub
The Docker image is also available at: `YOUR_DOCKERHUB_USERNAME/w1_lab:latest`

```bash
# Pull and run from Docker Hub
docker pull YOUR_DOCKERHUB_USERNAME/w1_lab:latest
docker run -d --name w1_lab -p 80:80 YOUR_DOCKERHUB_USERNAME/w1_lab:latest
```

## Development Notes
- The application uses a YOLOv3-tiny model for efficient object detection
- FastAPI provides automatic API documentation and validation
- The container exposes port 80 for HTTP traffic
- All dependencies are packaged within the Docker container

## Key Learning Outcomes
- **Containerization**: Successfully packaged a complete ML application with Docker
- **API Development**: Implemented RESTful endpoints for model serving
- **Production Deployment**: Moved from notebook development to production-ready service
- **Dependency Management**: Handled complex ML dependencies through containerization
- **Service Architecture**: Built a scalable web service for model inference

## Real-World Applications
This deployment pattern is commonly used in:
- Production ML model serving
- Microservices architecture
- Cloud deployments (AWS, GCP, Azure)
- CI/CD pipelines for ML models
- Scalable inference services

## Troubleshooting
If you encounter issues:
1. Ensure Docker is running properly
2. Check if port 80 is available
3. Verify all files are in the correct directory structure
4. Check Docker logs: `docker logs w1_lab`

---

**Note**: This project demonstrates the transition from development (Jupyter notebooks) to production deployment, showcasing essential skills for real-world machine learning applications.
