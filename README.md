# Image Analysis Project

This project leverages the Azure AI Vision API to perform advanced image analysis and annotation. It includes a Flask-based API server (`app.py`) that integrates functionality from the `image-analysis.py` script. The application can analyze images to generate captions, identify objects, and detect tags, while also creating annotated output images with bounding boxes.

## Features

- **Image Captioning:** Generates captions for uploaded images with confidence scores.
- **Object Detection:** Identifies objects in the image and annotates them with bounding boxes.
- **Tagging:** Extracts descriptive tags for images along with confidence scores.
- **Annotated Image Output:** Saves and returns annotated images with detected objects highlighted.

## Technology Stack

- **Backend Framework:** Flask
- **Image Analysis:** Azure AI Vision API
- **Image Processing:** Python Imaging Library (PIL), Matplotlib
- **Environment Management:** dotenv

## Prerequisites

1. **Azure AI Vision Credentials:**
   - Azure AI Service Endpoint
   - Azure AI Service Key

2. **Python Packages:** Install dependencies with the following command:
   ```bash
   pip install -r requirements.txt
   ```

   Contents of `requirements.txt`:
   ```
   flask
   flask-cors
   azure-ai-vision
   python-dotenv
   Pillow
   matplotlib
   ```

## Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/image-analysis.git
   cd image-analysis
   ```

2. Set up your Azure AI Vision credentials in a `.env` file:
   ```env
   AI_SERVICE_ENDPOINT=your_azure_endpoint
   AI_SERVICE_KEY=your_azure_key
   ```

3. Run the Flask server:
   ```bash
   python app.py
   ```

## Usage

### Endpoints

1. **Analyze Image**
   - **URL:** `/analyze`
   - **Method:** POST
   - **Request Body:** Form-data with an `image` file field.
   - **Response:**
     - JSON containing captions, tags, and detected objects.
     - Annotated image as a downloadable file if objects are detected.

2. **Sample Output:**
   ```json
   {
       "caption": {
           "text": "A street with cars and trees",
           "confidence": 0.98
       },
       "tags": [
           {"name": "street", "confidence": 0.95},
           {"name": "car", "confidence": 0.92}
       ]
   }
   ```
   Annotated images are returned as files if objects are detected.

## File Structure

```
image-analysis/
├── app.py                 # Flask server implementation
├── requirements.txt       # Project dependencies
├── .env                   # Environment variables
└── README.md              # Project documentation
```

## Future Improvements

- Add support for more visual features like dense captions or facial recognition.
- Implement a front-end for a seamless user experience.
- Optimize image processing for larger files.

## Contributing

Contributions are welcome! Please submit a pull request or open an issue to suggest changes or improvements.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

