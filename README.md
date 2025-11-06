# Face Recognition Flask App

This project is a simple Flask web app that performs **face detection** and **face recognition** using deep learning models from `facenet-pytorch`. It uses **MTCNN** for detecting faces and **InceptionResnetV1** for generating embeddings to compare against known faces stored in `embeddings.pt`.

## Features

- Detects one or multiple faces in an uploaded image.
- Recognizes faces based on pre-saved embeddings.
- Displays recognition results directly on a web page.
- Lightweight Flask API with a simple upload interface.

## Project Structure

```bash
face-recognition-app/
│
├── app.py
├── face_recognition.py
├── embeddings.pt
├── templates/
│   ├── upload.html
│   └── register.html
├── static/uploads/
├── requirements.txt
└── README.md
```

## Installation

1. Clone this repository:

   ```bash
   git clone https://github.com/yourusername/face-recognition-flask.git
   cd face-recognition-flask

2. (Recommended) Create a clean environment

### Option 1: Using `venv`

```bash
# Create a virtual environment
python -m venv venv

# Activate it
# On Windows:
venv\Scripts\activate
# On macOS/Linux:
source venv/bin/activate

# Then install dependencies
pip install -r requirements.txt
```

### Option 2: Using Conda

```bash
# Create a new conda environment
conda create -n faceapp python=3.10

# Activate it
conda activate faceapp

# Then install dependencies
pip install -r requirements.txt
```

3. Run the Flask app:

```bash
python app.py
```

4. Open your browser and navigate to:

```bash
http://127.0.0.1:5000
```

## Model Details

Face Detector: MTCNN (Multi-task Cascaded Convolutional Networks)

Embedding Model: InceptionResnetV1 pretrained on VGGFace2

Embedding Storage: embeddings.pt (list of tuples: (embedding_tensor, person_name))

## Example Usage

Upload an image from the web UI.

The app detects faces and compares them to known embeddings.

The result shows the recognized person's name or "Unknown".

## Future Improvements

Add camera-based live recognition.

REST API for programmatic access (/api/recognize).

Docker support for easy deployment.

## License

MIT License — free to use and modify.
