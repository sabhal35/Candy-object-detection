# Candy Object Detection Project - Complete Setup Guide

Before starting, make sure you have Anaconda or Miniconda installed ([Download here](https://docs.anaconda.com/anaconda/install/))

## Step 1: Download Project

Download the `Candy-object-detection` folder to your computer. Open a terminal/command prompt and navigate to the project directory:

```bash
cd path/to/Candy-object-detection
```

## Step 2: Create Conda Environment

Create and activate the environment from the provided `environment.yml`:

```bash
conda env create -f environment.yml
conda activate candy_detection
```

## Step 3: Download and Prepare the Dataset

The Kaggle dataset is provided here: **Candy Brands for Object Detection** [Kaggle Link](https://www.kaggle.com/datasets/ruopengan/candy-brands-for-object-detection?resource=download)

When you download and extract the Kaggle dataset archive, it contains two main folders:
- `annotation csv files/` — CSV annotation files
- `Images/` — Candy images

### Organize these folders into your project structure:
You will move:
- All images into the `Images/` folder in the project root
- All CSV annotation files into the `Annotation_CSV_Files/` folder

Run the provided data preparation notebook cells to:
- Automatically organize files
- Convert CSV annotations to YOLO format labels
- Create a train/validation split (default 90/10)
- Generate the `data.yaml` configuration file

## Step 4: Launch Jupyter Notebook

Start the Jupyter notebook server:

```bash
jupyter notebook
```

Open `Candy_Object_Detection.ipynb` and run the setup and data preparation cells.

## Step 5: Run Cells in the Main Notebook

### Setup and Data Preparation
- Moves images and CSVs to correct folders
- Converts CSV annotations to YOLO .txt format
- Splits dataset into training and validation sets
- Creates `data.yaml` for YOLO training

### Model Training
- Trains YOLOv8 model (default 20 epochs, change to 100 for full training)
- Saves trained model weights in `runs/detect/candy_detection/weights/`

### Testing and Evaluation
- Loads the trained model
- Tests on validation or new images
- Displays and saves detection results

## Project Folder Structure

```
Candy-object-detection/
├── Candy_Object_Detection.ipynb    # main notebook
├── classes.txt                     # candy class names
├── data.yaml                       # dataset config for YOLO
├── environment.yml                 # conda environment dependencies
├── yolov8n.pt                      # pretrained YOLOv8 base model
├── requirements.txt                # python dependencies
├── Annotation_CSV_Files/           # original CSV annotations (from Kaggle)
├── Images/                         # candy images
├── labels/                         # YOLO format labels (.txt)
├── dataset/                        # train/val splits
│   ├── images/train/
│   ├── images/val/
│   ├── labels/train/
│   └── labels/val/
├── runs/                           # training outputs
└── test_results/                   # detection result outputs
```

## Dataset Source

Images and annotations are from the Kaggle dataset **Candy Brands for Object Detection**:
https://www.kaggle.com/datasets/ruopengan/candy-brands-for-object-detection?resource=download

## Candy Classes Detected

- 100_Grand
- 3_Musketeers
- Baby_Ruth
- Butterfingers
- Crunch
- Midnight_Milky_Way
- Milky_Way
- Snickers
- Twix