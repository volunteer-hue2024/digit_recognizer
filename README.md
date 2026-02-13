 
# Image based Deep Learning projects
  
a. classification 
b. generation - Goto GAN repo

## a) IMAGE CLASSIFICATION PROJECTS

## 1. Digit_recognizer
A deep learning model that can classify 0-9 digits
builds models from **scratch** for a simpler dataset.

## 2. Fashion-MNIST (10 distinct classes)
Builds models from **scratch** for a simpler dataset.
1. ANN (image is flattened at the input layer)
2. CNN (convolution layers)

## 3. CIFAR-100 (100 distinct classes) 
Focuses on **Transfer Learning** using high-level pre-trained models

[ The dataset loading and preprocessing steps differ significantly due to their distinct objectives: one focuses on **Transfer Learning** using high-level pre-trained models, while the other builds models from **scratch** for a simpler dataset. ]

### Comparison of Dataset Loading and Preprocessing

| Feature | **Pretrained_Image_Classification_CIFAR.ipynb** | **Digit_Recognizer_from_Scratch_ANN_CNN.ipynb** |
| --- | --- | --- |
| **Dataset Used** | CIFAR-100 (100 distinct classes) | Fashion-MNIST (10 distinct classes) |
| **Loading Method** | `keras.datasets.cifar100.load_data()` | `keras.datasets.fashion_mnist.load_data()` |
| **Normalization** | Uses architecture-specific `preprocess_input` functions (e.g., for ResNet50, VGG16, MobileNetV2). | Manually scales pixel values by dividing by 255.0 to reach a 0–1 range. |
| **Reshaping** | Not explicitly shown as a standalone step; relies on the original 32x32x3 shape required by the pre-trained models. | Explicitly reshapes images to (28, 28, 1) to add a channel dimension for CNN compatibility. |
| **Label Encoding** | Keeps labels as integers for use with `sparse_categorical_crossentropy`. | Converts labels into one-hot encoded vectors using `to_categorical` for `categorical_crossentropy`. |

### Key Differences in Workflow

* **Custom vs. Standard Preprocessing**: In the **CIFAR-100 notebook**, preprocessing is tied to the specific requirements of pre-trained models like ResNet50 or VGG16, which may involve specialized scaling or color-channel adjustments beyond simple normalization. In contrast, the **Fashion-MNIST notebook** uses a standard manual normalization approach.
* **Target Representation**: The **Fashion-MNIST project** one-hot encodes labels into 10-class vectors early in the process. The **CIFAR-100 project** retains sparse integer labels, which is often more memory-efficient when dealing with a larger number of classes (100).
* **Input Requirements**: The CIFAR-100 images are already in a 3nd-order tensor format (32x32x3) suitable for standard CNNs, whereas the Fashion-MNIST images require a manual reshape to include the single grayscale channel dimension before they can be processed by CNN layers.





## b) IMAGE GENERATION PROJECT - Gan
