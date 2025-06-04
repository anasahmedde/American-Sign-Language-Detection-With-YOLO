# American-Sign-Language-Detection-With-YOLO

This project demonstrates the use of YOLOv8 for detecting American Sign Language (ASL) gestures. It includes a Flask application that allows you to test the ASL detection model using image uploads or live webcam feeds. You can also retrain the YOLOv8 model with a custom dataset.

## Project Structure

### Application Directory

The `application` directory contains all the components needed to run the Flask application for ASL detection.

```bash
application/
├── app.py            # The main Flask application file.
├── requirements.txt  # List of dependencies required for the project.
├── templates/        # Directory containing HTML templates.
│   ├── index.html    # Main template for the web interface.
├── static/           # Directory for static files like uploaded images.
│   ├── styles.css    # CSS file for styling the web interface.
│   └── uploads/      # Directory where uploaded images are stored.
├── models/           # Directory containing the trained YOLOv8 model.
│   └── yolov8n.pt    # The YOLOv8 model file used for ASL detection.
├── train/            # Directory containing the training script.
│   └── train.py      # Script to train the YOLOv8 model on a new dataset.
└── README.md         # This documentation file.
```
### Training Directory
The training directory is used for training the YOLOv8 model with your own dataset.
```bash
training/
├── dataset/          # All the dataset files including train, valid, test splits, and the data.yaml file.
│   ├── train/        # Training images.
│   ├── valid/        # Validation images.
│   ├── test/         # Test images.
│   └── data.yaml     # Dataset configuration file.
├── runs/             # Directory to store training runs and results.
│   └── exp/          # Example of a training run folder with results.
├── test.jpg          # An example image used for testing.
├── train.ipynb       # Jupyter notebook for training and experimenting with the YOLOv8 model.
└── yolov8n.pt        # Pre-trained YOLOv8 model used for initializing training.
```

## Project Demo

https://github.com/user-attachments/assets/6564970b-b950-4be9-8606-b2a5b63e0d39

https://github.com/user-attachments/assets/761b9ee4-25b7-4c14-92d2-dd3a8494ceca


## Getting Started

### Prerequisites

Before you begin, ensure you have the following installed on your system:

- **Python 3.8+**
- **Flask**
- **PyTorch**
- **YOLOv8 dependencies**

You can install all necessary packages by navigating to the `application` directory and running:

```bash
cd application
python -m virtualenv venv
venv\Scripts\activate
pip install -r requirements.txt
```

### Dataset

The dataset used for training the YOLOv8 model in this project can be downloaded from the following link:

- [Roboflow ASL Dataset](https://app.roboflow.com/owais-ahmed-xq0js/asl-3i64o/1)

#### Using Your Own Dataset

If you want to use your own dataset for training:

1. **Organize Your Dataset:**
   - Create subdirectories for `train`, `valid`, and `test` inside the `training/dataset` directory.
   - Place your training images in the `train` directory, validation images in the `valid` directory, and test images in the `test` directory.

2. **Update `data.yaml`:**
   - Modify the `data.yaml` file in the `training/dataset` directory to reflect the paths to your dataset.
   - Ensure the `train`, `val`, and `test` fields in `data.yaml` correctly point to the respective directories.

3. **Proceed with Training:**
   - Once your dataset is set up and the `data.yaml` file is configured, you can proceed with training the YOLOv8 model as described in the [Training the Model](#training-the-model) section.

## Running the Flask Application

To test ASL detection using the my pre-trained YOLOv8 model:

1. **Start the Flask Application:**
    Navigate to the application directory and run the Flask server:
    ```bash
    python app.py
    ```
2. **Access the Web Interface:**
    Open your web browser and go to http://127.0.0.1:5000/.
    From here, you can upload an image or use the live webcam feature to detect ASL gestures.

## Acknowledgments
[Roboflow](https://roboflow.com/) provided us with a platform for dataset annotation.

[Ultralytics](https://github.com/ultralytics), for their pre-trained YOLOv8 weights.

## License
This project is licensed under the MIT License. See the LICENSE file for details.

Feel free to contribute to this project by opening issues or submitting pull requests. Happy coding!
