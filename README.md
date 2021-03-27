# hpa-deep-learning

This project is about detecting single cells from HPA kaggle competition

## Project file details
* `pre-process-non-image\pre-process-non-image-eda.ipynb` has EDA related information about the training dataset.
* `extract-single-images-from-samples.ipynb` has the code to convert training image files to cell image files
    * The code expects a training directory with 4 image files for each sample. For each sample the files have id and postfixed by `_blue`,`_red`, `_yellow` and `_green`. First 3 files are used by segmentator tool build binary masks for the cells. The masks are used on the `_green` image to extract single images.

* `*-file-details.ipynb` files have code to provide breakouts on the files by the cell type
* `model-based*.ipynb` files have individual modeling for the 12 classes. The file prefixed with `19` includes all the cells images for the models.
    * This project uses `vgg16`, `resnet101`, `EfficientNetB6` models.
* `train.csv` has the initial training sample data captured from kaggle competition.
* `data` folder expected to have all the image and saved model data.

## Technology
* Extraction is using pytorch while the modeling used tensorflow 2.4

## Tools uses
* Cell segmentation is taken from [here](https://github.com/CellProfiling/HPA-Cell-Segmentation) 