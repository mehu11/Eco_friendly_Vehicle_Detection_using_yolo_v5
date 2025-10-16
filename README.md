
The increase in carbon emissions from vehicles has raised serious environmental concerns,
prompting the need for advanced systems that can monitor and mitigate pollution. This project
centers around the development of eco-friendly vehicle detection and carbon emission analysis
through the utilization of yolo (you only look once), a cutting-edge deep learning model designed
for real-time object detection. The system is created to categorize vehicles according to their fuel
type—electric, hybrid, or conventional—by examining visual characteristics and identifying
emission indicators. By combining image processing and deep learning techniques, the model
successfully identifies different types of vehicles and estimates their carbon emissions. The
gathered data can be utilized to evaluate pollution levels in urban regions, offering valuable
insights for sustainable transportation planning. The system's real-time monitoring features allow
for quick assessment, empowering government agencies and environmental organizations to
implement timely measures to support green mobility. This method helps minimize
environmental harm by enabling informed decision-making for cleaner transportation systems
through data analysis.



# Eco-friendly Vehicle Detection & Carbon Emission Analysis 🌍🚗


A B.Tech final year project that leverages the YOLOv5s model to detect vehicles and classify them as eco-friendly or non-eco-friendly to perform a real-time carbon emission analysis.



---

## 📋 Table of Contents
- [About The Project](#about-the-project)
- [Features](#-features)
- [Getting Started](#-getting-started)
  - [Prerequisites](#prerequisites)
  - [Installation](#installation)
- [Usage](#-usage)
- [Methodology](#-methodology)
- [Results](#-results)
- [Acknowledgments](#-acknowledgments)
- [License](#-license)

---

## 📖 About The Project

This project aims to address environmental concerns by providing a tool to monitor vehicle traffic and estimate carbon emissions in real-time. By using the powerful **YOLOv5s object detection model**, this system can process video streams or images to identify various types of vehicles.

The core idea is to:
1.  **Detect** all vehicles in a given frame.
2.  **Classify** them into 'eco-friendly' (e.g., bicycles) and 'non-eco-friendly' (e.g., cars, buses, trucks).
3.  **Estimate** the carbon emissions based on the count and type of non-eco-friendly vehicles detected.

This project was developed as a major project for the B.Tech in Computer Science program, utilizing the **COCO 2017 val dataset** for object classes.

---

## ✨ Features

* **Real-time Vehicle Detection**: Identifies multiple vehicle classes with high accuracy.
* **Eco-Friendly Classification**: Differentiates between polluting and non-polluting vehicles.
* **Carbon Emission Estimation**: Provides a simplified, real-time analysis of CO₂ emissions.
* **High Performance**: Built on the lightweight and fast **YOLOv5s** model.
* **Extensible**: Easy to modify for different video sources or to add more vehicle classes.

---


## 🚀 Getting Started

Follow these steps to get a local copy up and running.

### Prerequisites

Make sure you have Python and pip installed on your system.

### Installation

1.  **Clone the repository:**
    ```sh
    git clone [https://github.com/YOUR_USERNAME/YOUR_REPO.git](https://github.com/YOUR_USERNAME/YOUR_REPO.git)
    cd YOUR_REPO
    ```

2.  **Install the required packages:**
    It's recommended to use a virtual environment.
    ```sh
    # Create and activate a virtual environment (optional but recommended)
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`

    # Install dependencies
    pip install -r requirements.txt
    ```

---

## 💨 Usage

You can run the detection script on various sources like images, videos, or a live webcam feed.

1.  **To run on an image:**
    ```sh
    python detect.py --source path/to/your/image.jpg
    ```

2.  **To run on a video:**
    ```sh
    python detect.py --source path/to/your/video.mp4
    ```

3.  **To use your webcam:**
    ```sh
    python detect.py --source 0
    ```
The output will be saved in the `runs/detect/exp` directory by default.

---

## 🔬 Methodology

The project follows a three-step pipeline:

1.  **Detection**: The pre-trained YOLOv5s model, which was trained on the COCO dataset, is used to detect objects. We filter for vehicle-related classes such as `car`, `bus`, `truck`, `motorcycle`, and `bicycle`.

2.  **Classification**: After detection, a simple rule-based logic is applied to classify the vehicles:
    * **Eco-Friendly**: Objects classified as `bicycle`.
    * **Non-Eco-Friendly**: Objects classified as `car`, `bus`, `truck`, `motorcycle`.

3.  **Carbon Emission Analysis**: A simplified model is used to estimate emissions. The total emission $E$ in a frame is calculated as:
    $$E (\text{g/s}) = \sum_{i \in \text{classes}} (N_i \times C_i)$$
    Where:
    -   $N_i$ is the number of vehicles of class $i$.
    -   $C_i$ is the average emission coefficient (in grams per second) for a vehicle of class $i$.
    -   Example coefficients used: `Car`: 0.05 g/s, `Bus`: 0.12 g/s, `Truck`: 0.15 g/s.
    
    *Note: These coefficients are illustrative and can be adjusted for more accurate real-world scenarios.*

---

## 📊 Results

This section showcases some of the results from the project. You can add your own images, GIFs, or videos here.

**(Example Screenshot)**
*A screen capture of the model running on a busy street, with bounding boxes and emission data displayed.*

<img width="896" height="650" alt="ProcessingData" src="https://github.com/user-attachments/assets/bfc29b98-241b-4040-8572-2d525cbb176e" />

---

## 🙏 Acknowledgments

* This project is heavily inspired by and utilizes the **YOLOv5** repository by **Ultralytics**. A huge thank you to them for their incredible work. You can find their repository [here](https://github.com/ultralytics/yolov5).
* The model was trained on the **COCO Dataset**.

---

## 📄 License

This project is licensed under the MIT License. See the `LICENSE` file for more details.
