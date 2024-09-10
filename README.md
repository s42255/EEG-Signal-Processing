The Dataset used for the project: 10.3389/fnhum.2024.1304311

# EEG Data Analysis Using MNE and Autoreject

This project is focused on the preprocessing, visualization, and analysis of EEG (Electroencephalography) data using Python. The analysis is carried out using the *MNE-Python* library, a powerful tool for analyzing electrophysiological data, and *Autoreject*, which aids in automatically identifying and correcting artifacts in EEG signals. The notebook is designed to be run in *Google Colab*, where the EEG data is loaded, cleaned, and visualized.

## Project Overview:
The goal of this project is to facilitate the handling of raw EEG data through a streamlined workflow. By leveraging advanced tools like MNE and Autoreject, the notebook performs several key operations, including loading EEG data in .set format, detecting and rejecting artifacts, and visualizing the cleaned data.

### Key Features:
#### 1. *Google Colab Setup for EEG Analysis:*
The project is built to run in Google Colab, and it begins by mounting the user’s Google Drive to load EEG datasets. Colab’s environment is extended using a variety of Python libraries essential for EEG analysis. These include:
   - *MNE*: A comprehensive package for handling and analyzing EEG, MEG, and other electrophysiological data.
   - *Autoreject*: A package built to automate the process of artifact detection and rejection in EEG data.
   - *Seaborn and Matplotlib*: For creating visual representations of the EEG signals and any subsequent analyses.
   - *Plotly*: To generate interactive visualizations, aiding in the exploration of EEG signals.

#### 2. *Data Importation and Error Handling:*
The notebook supports EEG data in .set (EEGLAB) and .fdt file formats. A robust error-handling mechanism is implemented via a try/except loop to ensure the successful loading of data, which addresses potential issues such as sampling inconsistencies or file reading errors that can occur during import.

The primary function used for importing EEG data is:
```python
raw1 = mne.io.read_raw_eeglab(eeg_file, preload=True)
```
### 3. Artifact Detection and Rejection with Autoreject
EEG data is highly susceptible to various artifacts caused by muscle movement, eye blinks, or electrical interference. Handling these artifacts is critical for accurate interpretation. The `Autoreject` library is integrated into the workflow to automate the rejection of these artifacts.

Autoreject performs automatic thresholding and cross-validation to determine which EEG channels or segments need correction. It simplifies a traditionally complex and manual process, making the dataset cleaner for further analysis.

The notebook includes plans to utilize Independent Component Analysis (ICA) for identifying and separating out noise sources, although this section is referenced but not fully implemented in the current version.

### 4. Data Visualization
Visualizing EEG data is essential for verifying the preprocessing steps and gaining insights into the temporal and spectral characteristics of brain activity. The notebook includes rich visualizations, generated through:

- `Matplotlib` and `Seaborn` for creating detailed static plots.
- `Plotly` for interactive plots that allow the user to explore the dataset dynamically.

Example visualization plots include:
- Raw EEG signals (before and after artifact rejection)
- Power spectral density (PSD) plots, showing the distribution of signal power across different frequency bands

### Libraries and Dependencies
The following Python libraries are integral to this project:

- `MNE`: For handling EEG data, filtering, and performing various preprocessing steps.
- `Autoreject`: To automate the detection and rejection of artifacts in EEG recordings.
- `Seaborn` and `Matplotlib`: For creating a wide array of data visualizations, from simple line plots of EEG signals to more complex statistical representations.
- `Plotly`: For generating interactive visualizations, offering users the ability to zoom in and explore EEG signals in depth.
- `NumPy` and `Pandas`: For efficient data manipulation, especially when working with large EEG datasets.

