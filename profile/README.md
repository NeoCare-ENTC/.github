# NeoCare - Contactless Neonatal Health Monitoring System

## Project Overview
**NeoCare** is a non-invasive, real-time health monitoring system for neonates, utilizing **remote photoplethysmography (rPPG)** to measure vital signs such as **heart rate (HR)**, **blood oxygen saturation (SpO2)**, and **jaundice detection** through facial video analysis. The system integrates advanced **deep learning algorithms**, privacy-preserving **edge computing**, and **mobile application development** to ensure data security, efficiency, and clinical reliability.

## Key Features
- **Contactless Vital Sign Monitoring**: Using rPPG, the system enables heart rate and oxygen saturation estimation from facial video frames.
- **Neonatal Jaundice Detection**: Detects signs of neonatal jaundice through facial image analysis, leveraging advanced color normalization and deep learning models.
- **Privacy-Preserving AI**: On-device processing and encrypted transmission to ensure sensitive neonatal data is handled securely.
- **Mobile Application**: A cross-platform mobile app built with **React Native**, designed for non-contact health monitoring of neonates by parents and healthcare providers.

## System Architecture

The NeoCare system consists of three primary modules:
1. **Video Capture Module**:
   - Uses a camera to capture continuous facial video of the neonate.
   - Video frames are preprocessed and passed through the rPPG and jaundice detection models for analysis.

2. **rPPG and Jaundice Detection Models**:
   - **rPPG Estimation**: Uses **YOLOv11** for face and region-of-interest (ROI) detection, followed by deep learning-based extraction of heart rate and SpO2 signals from facial videos.
   - **Jaundice Detection**: Extracts key facial regions (forehead and cheeks) and normalizes color using techniques like **gray-world correction** and **histogram matching** to detect jaundice.

3. **Mobile Application**:
   - Built with **React Native** to allow users to record videos, capture health data, and receive real-time vital sign analysis.
   - Backend integration with **Node.js** and **PostgreSQL** for data storage and processing.

## Technical Stack
- **Deep Learning Models**:
  - **YOLOv11**: Used for neonatal face detection and region-of-interest (ROI) detection.
  - **MobileNetV2** and **EfficientNet**: Lightweight CNN models for jaundice detection, trained on custom datasets of neonatal images.
  - **PhysMamba** and **PhysNet**: Models for estimating heart rate and SpO2 from rPPG signals, with a focus on neonatal adaptation.

- **Signal Processing**:
  - **rPPG Signal Extraction**: Utilizes motion-correction algorithms to isolate the pulsatile signal from facial video, followed by heart rate and oxygen level estimation.
  - **Color Normalization**: Employs color space transformations (e.g., RGB to HSV, YCbCr) to minimize lighting and skin tone variations in the jaundice detection system.

- **Privacy and Data Security**:
  - **On-Device Processing**: All sensitive data, including facial video, is processed on the mobile device to minimize data transmission risks.
  - **Encryption**: Data is encrypted using AES encryption for secure transmission and storage.
  - **Region Masking**: Facial regions are masked to prevent re-identification and ensure privacy.

## Phases of Development

### Phase 1: Algorithm Enhancement and Design
- **Objective**: Improve the accuracy and performance of heart rate, SpO2, and jaundice detection algorithms, ensuring minimal computational load for mobile deployment.
- **Tasks**:
  - Enhancement of existing deep learning models for neonatal HR and SpO2 estimation.
  - Algorithm optimization for real-time mobile application deployment.
  - Design and testing of video preprocessing techniques, including ROI stabilization and color normalization.

### Phase 2: Dataset Collection and Ground Truth Acquisition
- **Objective**: Collect high-quality datasets for training and validating the algorithms.
- **Tasks**:
  - Collect 1-minute video samples from neonates, along with synchronized HR, SpO2, and jaundice data.
  - Develop a dataset specifically for jaundice detection, including images of neonates under various lighting conditions.
  - Ensure ethical approval and participant consent through De Soysa Hospital.

### Phase 3: Edge Deployment and Privacy-Preserving Implementation
- **Objective**: Integrate the algorithms into a mobile application with privacy-preserving measures and efficient data handling.
- **Tasks**:
  - Implement the trained models into the React Native mobile application.
  - Optimize the system for low power consumption and real-time processing.
  - Implement secure data handling using edge computing, ensuring compliance with healthcare data protection standards.

## Dataset Overview
- **VideoPulse Dataset**: Includes facial video data for heart rate and SpO2 estimation.
- **NBHR Dataset**: Neonatal heart rate and SpO2 data used for training rPPG models.
- **NJN Dataset**: Neonatal images with and without jaundice for training jaundice detection models.
- **NeoCare Dataset**: Clinical data from neonates in Sri Lanka for validating system performance in real-world settings.

## Privacy-Preserving Techniques
- **Face-Region Masking**: Only forehead and cheek areas are used for rPPG and jaundice detection, ensuring privacy by masking the rest of the face.
- **Data Anonymization**: No facial videos are stored; only anonymized physiological data (HR, SpO2, jaundice status) is saved.
- **On-Device Processing**: Video data is processed directly on the mobile device to avoid cloud transmission of sensitive information.

## Ethical Approval
The project has received ethical clearance from the Ethics Review Committees of **University of Moratuwa** and **De Soysa Hospital for Women, Colombo**.

## Team Members
- **A.A.W.L.R. Amarasinghe**  
- **M.K.I.G. Morawakgoda**  
- **S.M.S.M.B. Abeyrathna**  
- **U.M.Y.B. Alahakoon**  

## Future Work
- **Dataset Expansion**: Expand the dataset to include more neonates from different demographic backgrounds.
- **Model Optimization**: Further reduce model size for real-time mobile deployment, including pruning and quantization techniques.
- **Clinical Validation**: Conduct clinical trials to validate the effectiveness of NeoCare in neonatal intensive care units (NICUs).

