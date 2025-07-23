# Candy Object Detection Project - Complete Setup Guide

Before starting, make sure you have Anaconda or Miniconda installed ([Download here](https://docs.anaconda.com/anaconda/install/))

## Step 1: Download Project

1. Download or clone the Candy-object-detection folder to your computer
2. Open a terminal (macOS/Linux) or Command Prompt/Anaconda Prompt (Windows)
3. Navigate to the project folder:
```bash
cd path/to/Candy-object-detection
```

## Step 2: Set Up the Conda Environment

Create a new environment using the included `environment.yml` file:

```bash
conda env create -f environment.yml
conda activate candy_detection
```
This installs all necessary packages defined in the `environment.yml` file

## Step 3: Download the Dataset

The Kaggle dataset is provided here: **Candy Brands for Object Detection** [Kaggle Link](https://www.kaggle.com/datasets/ruopengan/candy-brands-for-object-detection?resource=download)

After extracting the downloaded ZIP file, you will see:
- `annotation csv files/` — CSV annotation files
- `Images/` — Candy images

### Move these folders into your project:

* Put all images into the `Images/` folder in the project root
* Put all CSV files into the `Annotation_CSV_Files/` folder

## Step 4: Launch Jupyter Notebook

Start Jupyter from the terminal or prompt:

```bash
jupyter notebook
```

In your browser, open the file `Candy_Object_Detection.ipynb`

## Step 5: Run Cells in the Notebook

Go through the notebook cells in order 

They will:
* Move files to the correct locations
* Convert CSV annotations to YOLO .txt format
* Split the dataset into training and validation sets
* Generate the data.yaml file for training

Then, continue with model training and testing

## Project Structure

Your folder should look like this after setup:

```
Candy-object-detection/
├── Candy_Object_Detection.ipynb    # main notebook
├── classes.txt                     # list of candy classes
├── data.yaml                       # YOLO config file
├── environment.yml                 # conda environment file
├── yolov8n.pt                      # pretrained YOLO model
├── requirements.txt                # python dependencies
├── Annotation_CSV_Files/           # CSV files from Kaggle
├── Images/                         # raw images
├── labels/                         # YOLO label files
├── dataset/                        # train/val splits
│   ├── images/train/
│   ├── images/val/
│   ├── labels/train/
│   └── labels/val/
├── runs/                           # training results
└── test_results/                   # results from model testing
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
