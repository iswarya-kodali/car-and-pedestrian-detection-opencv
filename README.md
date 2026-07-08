# Car & Pedestrian Detection

A simple computer vision project using OpenCV's Haar Cascade classifiers to detect
pedestrians and cars in video footage.

## Features

- **Pedestrian Detection** — detects full-body pedestrians in a video using
  `haarcascade_fullbody.xml`
- **Car Detection** — detects cars in a video using a car Haar cascade classifier

## Project Structure

```
car-pedestrian-detection/
├── car_pedestrian_detection.ipynb   # Main notebook
├── requirements.txt                  # Python dependencies
├── Haarcascades/                     # Haar cascade XML classifiers (add your own)
│   ├── haarcascade_fullbody.xml
│   └── haarcascade_car.xml
├── image_examples/                   # Sample video files (add your own)
│   ├── walking.avi
│   └── cars.avi
└── README.md
```

> **Note:** The Haar cascade XML files and sample videos are not included in this
> repo (large/binary assets). See the **Setup** section below for where to get them.

## Setup

1. Clone the repo:
   ```bash
   git clone https://github.com/<your-username>/car-pedestrian-detection.git
   cd car-pedestrian-detection
   ```

2. Create a virtual environment and install dependencies:
   ```bash
   python -m venv venv
   source venv/bin/activate    # On Windows: venv\Scripts\activate
   pip install -r requirements.txt
   ```

3. Download the required Haar cascade files and place them in a `Haarcascades/` folder:
   - Full body / pedestrian classifier: [haarcascade_fullbody.xml](https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade_fullbody.xml)
   - Car classifier: search for `cars3.xml` / `haarcascade_car.xml` (widely available in
     public OpenCV Haar cascade repositories)

4. Add your own test videos to an `image_examples/` folder (e.g. `walking.avi`, `cars.avi`),
   or use your own footage.

5. Run the notebook:
   ```bash
   jupyter notebook car_pedestrian_detection.ipynb
   ```

## Usage Notes

- The notebook opens a live OpenCV window (`cv2.imshow`), so it must be run **locally**
  (not in a headless environment like Google Colab or a remote server without a display).
- Press **Enter** to close each detection window while a video is playing.
- File paths in the notebook use Windows-style backslashes (`Haarcascades\haarcascade_fullbody.xml`).
  If you're on macOS/Linux, update these to forward slashes
  (`Haarcascades/haarcascade_fullbody.xml`) or use `os.path.join(...)` for cross-platform
  compatibility.

## Requirements

- Python 3.7+
- OpenCV (`opencv-python`)
- NumPy

## License

This project is for educational purposes. Haar cascade classifiers are provided by the
OpenCV project under their respective license.
