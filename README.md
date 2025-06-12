# Soil-Classification-Dataset

This repository contains comprehensive datasets for soil classification and recognition research. The **Original Dataset** comprises soil images sourced from various online repositories, which have been meticulously cleaned and preprocessed to ensure data quality and consistency. To enhance the dataset's size and diversity, we employed Generative Adversarial Networks (GANs), specifically the **CycleGAN** architecture, to generate synthetic soil images. This augmented collection is referred to as the **CyAUG Dataset**. Both datasets are specifically designed to advance research in soil classification and recognition using state-of-the-art deep learning methodologies.

<blockquote>
This dataset was curated as part of the research paper titled "<em>An advanced artificial intelligence framework integrating ensembled convolutional neural networks and Vision Transformers for precise soil classification with adaptive fuzzy logic-based crop recommendations</em>" by Farhan Sheth, Priya Mathur, Amit Kumar Gupta, and Sandeep Chaurasia, published in <b>Engineering Applications of Artificial Intelligence</b>.
</blockquote>

### Links

- **Paper**: [An advanced artificial intelligence framework integrating ensembled convolutional neural networks and Vision Transformers for precise soil classification with adaptive fuzzy logic-based crop recommendations](https://doi.org/10.1016/j.engappai.2025.111425)
- **Code**: [Development Code (model and recommendation system)](https://github.com/Phantom-fs/Agro-Companion-Modules)

Application produced by this research is available at:

- **Agro Companion**: [Agro Companion](https://github.com/Phantom-fs/Agro-Companion)
- **Server Code**: [Agro Companion Server](https://github.com/Phantom-fs/Agro-Companion-Application-Server)

### **Note**: If you are using any part of this project; dataset, code, application, then please cite the work as mentioned in the [Citation](#citation) section below.

### Abstract
<blockquote>
This study introduces an advanced Artificial Intelligence (AI) framework for soil classification and crop recommendation, combining Convolutional Neural Networks (CNNs) and Vision Transformers (ViTs) in an ensemble approach, alongside an adaptive fuzzy logic-based decision system for crop suggestions. While existing research typically addresses soil classification or crop recommendation in isolation, this work integrates cutting-edge deep learning models and fuzzy logic to enhance both tasks. The methodology is divided into two phases: Phase 1 covers data collection, preprocessing, and augmentation using Cycle Generative Adversarial Networks (CycleGAN) to expand the curated dataset of 1189 soil images to 8,413, while Phase 2 focuses on training CNN and ViT models, ensembling these models, and developing a fuzzy logic system that considers soil type, nutrients, potential of hydrogen (pH), and climatic conditions for crop recommendations. Experimental results indicate models achieve classification accuracies of up to 89.32 % on the original dataset, improving to 91.01 % with augmented data. On the CycleGAN-augmented (CyAUG) dataset, EfficientNet v2 Large and ViT-Large/16 attain accuracies of 99.60 % and 99.73 %, respectively. Furthermore, an ensemble of these architectures achieves a perfect accuracy of 100 %. The results are also validated by K-fold cross-validation. The research also presents 'Agro Companion,' an AI-powered tool that assists farmers in soil identification and crop selection based on geological and environmental data. This framework addresses key agricultural challenges in India, offering a high-accuracy, practical solution for improving both soil classification and crop recommendation. This research delivers state-of-the-art soil classification performance and a robust AI-based crop recommendation tool to support sustainable agricultural practices.
</blockquote>

## Table of Contents

- [Dataset](#dataset)
- [Dataset Details](#dataset-details)
  - [Original Dataset Details](#original-dataset-details)
  - [CyAUG Dataset Details](#cyaug-dataset-details)
- [Getting Started](#getting-started)
- [Citation](#citation)
- [License](#license)
- [Acknowledgements](#acknowledgements)

## Dataset

Both dataset consists of images of **7** different soil types. 

The **Soil Classification Dataset** is structured to facilitate the classification of various soil types based on images. The dataset includes images of the following soil types:

- **Alluvial Soil**
- **Black Soil**
- **Laterite Soil**
- **Red Soil**
- **Yellow Soil**
- **Arid Soil**
- **Mountain Soil**

The dataset is organized into folders, each named after a specific soil type, containing images of that soil type. The images vary in resolution and quality, providing a diverse set of examples for training and testing classification models. More specifically, the structure of the dataset is as follows:

```text
Soil-Classification-Dataset/
    Alluvial Soil/
        image1.jpg
        image2.jpg
        ...
    Black Soil/
        image1.jpg
        ...
    ...
```

### Download

The dataset is also available to be downloaded from the following sites:

- **Kaggle:** [Comprehensive Soil Classification Datasets](https://www.kaggle.com/datasets/ai4a-lab/comprehensive-soil-classification-datasets)
- **HuggingFace:** Coming soon

## Dataset Details

Dataset statistics for the original and augmented datasets from the research paper are as follows:

| Soil Type | Original Dataset | CyAUG Dataset|
|-----------|------------------|---------------|
| Alluvial Soil | 52 | 837 |
| Black Soil | 255 | 1885 |
| Laterite Soil | 219 | 831 |
| Red Soil | 109 | 1430 |
| Yellow Soil | 69 | 1593 |
| Mountain Soil | 201 | 761 |
| Arid Soil | 284 | 1076 |
| **Total** | **1189** | **8413** |

NOTE: For the CyAUG dataset, the training set is further augmented using noise, rotation, and flipping techniques to enhance model robustness. The CyAUG dataset given here is without training set augmentation, for simplicity and ease of use. The training set augmentation can be done using the code provided in the [Agro Companion Modules](https://github.com/Phantom-fs/Agro-Companion-Modules). If you want the augmented version of the CyAUG dataset, please contact the repository owner.

### Original Dataset Details

- **Total Images:** 1189 images
- **Image Format:** JPEG
- **Image Size:** Varies
- **Source:** Collected from various online repositories and cleaned for consistency.

### CyAUG Dataset Details

- **Total Images:** 5097 images
- **Image Format:** JPG
- **Image Size:** Varies
- **Source:** Generated using CycleGAN to augment the original dataset, enhancing its size and diversity.

### Input and Output Parameters

- **Input Parameters:**
  - **Image:** The images of the soils (JPG format).
  - **Label:** The labels are in the format 'soil types' (folder names).
- **Output Parameter:**
  - **Classification:** The predicted class (soil type) based on the input image.

## Getting Started

To use this dataset for your research or project:

1. **Clone the repository:**

   ```sh
   git clone https://github.com/Phantom-fs/Soil-Classification-Dataset.git
   ```

2. **Download the dataset:**
   - Download from Kaggle or HuggingFace (links above), or use the files in this repository.

3. **Dataset structure:**
   - Each folder is named after a soil type and contains images of that soil type.

4. **Usage example (Python):**

   ```python
   import os
   from PIL import Image

   dataset_path = 'Soil-Classification-Dataset'
   for soil_type in os.listdir(dataset_path):
       soil_folder = os.path.join(dataset_path, soil_type)
       if os.path.isdir(soil_folder):
           for img_file in os.listdir(soil_folder):
               img_path = os.path.join(soil_folder, img_file)
               img = Image.open(img_path)
               # process image
   ```

    Check the **[Code](https://github.com/Phantom-fs/Agro-Companion-Modules)** for detailed usage.

## Citation

If you are using any of the derived dataset, please cite the following paper:

```bibtex
@article{SHETH2025111425,
    title = {An advanced artificial intelligence framework integrating ensembled convolutional neural networks and Vision Transformers for precise soil classification with adaptive fuzzy logic-based crop recommendations},
    journal = {Engineering Applications of Artificial Intelligence},
    volume = {158},
    pages = {111425},
    year = {2025},
    issn = {0952-1976},
    doi = {https://doi.org/10.1016/j.engappai.2025.111425},
    url = {https://www.sciencedirect.com/science/article/pii/S0952197625014277},
    author = {Farhan Sheth and Priya Mathur and Amit Kumar Gupta and Sandeep Chaurasia},
    keywords = {Soil classification, Crop recommendation, Vision transformers, Convolutional neural network, Transfer learning, Fuzzy logic}
}
```

## License

This project is licensed under:

[Creative Commons Attribution-NonCommercial 4.0 International License][cc-by-nc].

[![CC BY-NC 4.0][cc-by-nc-shield]][cc-by-nc]

[![CC BY-NC 4.0][cc-by-nc-image]][cc-by-nc]

[cc-by-nc]: https://creativecommons.org/licenses/by-nc/4.0/
[cc-by-nc-image]: https://licensebuttons.net/l/by-nc/4.0/88x31.png
[cc-by-nc-shield]: https://img.shields.io/badge/License-CC%20BY--NC%204.0-lightgrey.svg

See the [LICENSE](LICENSE) file for details.

## Acknowledgements

This study is not to be used for commercial purposes. The dataset is intended for research and educational purposes only. This dataset was sourced from online sources and is not intended to infringe on any copyrights. If you have any concerns or requests regarding the dataset, please contact the repository owner.