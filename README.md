# Soccer Player Density Analysis in Image Zones

## Overview

This project analyzes the spatial distribution of soccer players within images from a football player segmentation dataset. Instead of attempting to classify players into potentially ambiguous "defensive," "midfield," and "attacking" thirds based on 2D perspective, this project divides each image into a grid of zones and calculates the player density (number of players) within each zone. This approach provides a more robust and directly observable measure of player distribution within the image frame.

## Key Features

* **Data Loading and Parsing:** Efficiently loads image file paths and parses COCO-style annotations for player segmentations.
* **Binary Mask Generation:** Creates binary masks for individual players from the polygon annotations.
* **Image Zoning:** Divides each image into a configurable grid of equal-sized rectangular zones.
* **Player Counting per Zone:** Determines the number of distinct players present in each image zone based on the overlap of their segmentation masks.
* **Image Visualization with Zone Density:** Overlays the original image with the defined zone grid and displays the player count within each zone.
* **Aggregate Density Analysis:** Calculates the average player density for each zone across the entire dataset.
* **Heatmap Visualization:** Presents the average player density across the image zones as a visually intuitive heatmap.

## Technical Stack

* Python
* OpenCV (`cv2`) for image loading and basic manipulation
* NumPy for numerical operations and array handling
* Matplotlib (`matplotlib.pyplot`) for basic image and plot visualization
* PIL (Pillow) for image manipulation (creating masks)
* `glob` for file path manipulation
* `json` for loading annotation data
* Seaborn (`seaborn`) for enhanced heatmap visualization

## Dataset

This project utilizes the "Football Player Segmentation" dataset (available on platforms like Kaggle - [{https://www.kaggle.com/datasets/ihelon/football-player-segmentation)]. The dataset contains images of soccer matches with corresponding annotations providing polygon segmentations for each player.

## Setup and Usage

1.  **Clone the repository:** `git clone https://github.com/felipervm/SoccerPlayerDistributionAnalysis`
2.  **Download the dataset:** Obtain the "Football Player Segmentation" dataset and place the `images` and `annotations` directories within the project's main directory (or adjust the `images_path` and `annotations_path` variables in the code).
3.  **Install dependencies:** Ensure you have the necessary Python libraries installed. You can install them using pip:
    ```bash
    pip install opencv-python numpy matplotlib Pillow glob seaborn
    ```
4.  **Run the analysis:** Execute the Python script (e.g., `python main.py` or the name of your script). The script will:
    * Load the images and annotations.
    * Process a few sample images to display player density per zone.
    * Calculate and print the average player density per zone across all images.
    * Generate and display a heatmap visualizing the average player density.

## Results and Findings

The visualizations and the average density heatmap provide insights into where players tend to be concentrated within the image frame during soccer matches in this dataset. This can be useful for understanding common formations or areas of high activity from a 2D image perspective.

## Potential Improvements

* **Dynamic Zone Size:** Allow the user to specify the number of rows and columns for the image grid.
* **Weighted Density:** Consider the area of each player's mask within a zone to calculate a more nuanced density measure.
* **Temporal Analysis (if applicable):** If the dataset contains video frames or sequential images, analyze how player density in different zones changes over time.
* **Perspective Correction (Advanced):** If camera calibration data were available, attempt to correct for perspective distortion to map image zones to more accurate field regions.

## Author

Felipe Mattos 
https://github.com/felipervm
