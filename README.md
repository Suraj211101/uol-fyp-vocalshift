# Neural Style Transfer for Speech Emotion Conversion

This repository contains the code for my **Final Year Project (FYP)**, which explores **neural style transfer in speech prosody**.  
The system converts **neutral speech** into emotional variants (*happy, sad, angry, fearful, disgust*) using **Mel-to-Mel models** trained on emotional speech datasets.

---

## 📌 Features
- Preprocessing audio files from the **RAVDESS** and **CREMA-D** datasets.
- Extracting features: **Mel spectrograms**, **pitch (F0)**, **energy**, **MFCCs**, and **spectral features**.
- Training a **CNN-based emotion classifier** to evaluate the transformed audio files.
- Training **emotion-specific Mel2Mel models** to convert neutral speech into target emotions.
- Using **hyperparameter tuning** and **k-fold cross-validation** for model selection.
- Employing a SpeechBrain **HiFi-GAN vocoder** for waveform reconstruction.

---

## 📂 Project Structure

The source code is split into three Jupyter Notebooks:
- `01_data_preprocessing.ipynb`  
- `02_emotion_classifier.ipynb`  
- `03_emotion_style_transfer.ipynb`

These require the **RAVDESS** and **CREMA-D** datasets (not included due to size).  
Download them here:
- [RAVDESS Emotional Speech Audio](https://www.kaggle.com/datasets/uwrfkaggler/ravdess-emotional-speech-audio)  
- [CREMA-D](https://www.kaggle.com/datasets/ejlok1/cremad) 

Additional project files:
- `.gitignore`  
- `README.md`  
- `requirements.txt`  

Final repo structure:
```bash
.
├── .gitignore
├── 01_data_preprocessing.ipynb
├── 02_emotion_classifier.ipynb
├── 03_emotion_style_transfer.ipynb
├── README.md
├── requirements.txt
```

---

## 🔧 Installation

```bash
git clone https://github.com/Suraj211101/uol-fyp-vocalshift.git
cd <uol-fyp-vocalshift>
pip install -r requirements.txt
```

---

## 🚀 Usage

Run the notebooks in order:
1. **`01_data_preprocessing.ipynb`**  
   Extract features and save them as `.npy` files.
2. **`02_emotion_classifier.ipynb`**  
   Train the CNN classifier (`emotion_cnn_best.keras`).
3. **`03_emotion_style_transfer.ipynb`**  
   Train the emotion-specific Mel2Mel models (saved in `saved_models/`).

⚠️ Running the notebooks will produce:
- `csv/` – metadata and logs (from Notebook 01)  
- `npys/` – preprocessed features (from Notebook 01)  
- `saved_models/` – trained emotion transfer models (from Notebook 03)  
- `tuner_logs/` – tuning logs (from Notebook 02)  
- `emotion_cnn_best.keras` – best classifier model (from Notebook 02)  