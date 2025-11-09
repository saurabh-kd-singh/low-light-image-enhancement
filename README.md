# 🌙 Low Light Image Enhancement

**Project:** Deep-learning based low-light image enhancement.

---

## 📁 Contents

- `code_v1.ipynb`, `code_v2.ipynb` — training/inference notebooks  
- `best_model.keras` — trained model *(consider removing large models from repo)*  
- `data_root/` — dataset *(not recommended to include large datasets in repo)*  
- `inference_results/`, `training_runs/`, `training_log_plot.png`

---

## ⚙️ Setup

### 1️⃣ Create and activate a virtual environment

```bash
# Using venv
python3 -m venv .venv
source .venv/bin/activate      # Linux/macOS
# OR
.venv\Scripts\activate         # Windows

# Using Conda (optional)
conda create -n lowlight python=3.10
conda activate lowlight

# Install requirements
pip install --upgrade pip
pip install -r requirements.txt


🚀 Usage
Run Jupyter notebooks and Inference
# Launch Jupyter Notebook
jupyter notebook

# Open:
#   - code_v1.ipynb → original version (training + testing)
#   - code_v2.ipynb → improved version with enhanced architecture/training

# Example Inference Command
python inference.py --model best_model.keras --input_dir data_root/sample_images --output_dir inference_results



🧠 Project Structure
.
├── code_v1.ipynb
├── code_v2.ipynb
├── best_model.keras
├── data_root/                # (ignored by git)
├── inference_results/         # model output images
├── training_runs/             # logs / checkpoints
├── training_log_plot.png
├── requirements.txt
└── README.md




📊 Description
🔸 Model

U-Net-like encoder–decoder architecture with skip connections

Convolutional layers for feature extraction

Deconvolution / upsampling layers for image reconstruction

🔸 Loss Function

Reconstruction Loss: Mean Squared Error (MSE) between enhanced and ground-truth images

Perceptual Loss: Feature-space loss using pretrained VGG network

Optional weight term: λ = 1×10⁻² to balance structural vs perceptual fidelity




# Framework: TensorFlow / Keras
# Image preprocessing: normalization to [0,1]
# Optimizer: Adam (learning rate ≈ 1e-4)
# Metrics: PSNR, SSIM, MSE
# Logs: saved in training_runs/
# Best model saved as: best_model.keras






# Ignore large files in .gitignore:
#   - best_model.keras
#   - dataset folders
#   - intermediate outputs

# To track large files with Git LFS:
git lfs install
git lfs track "best_model.keras"
git add .gitattributes
git add best_model.keras
git commit -m "Track model with Git LFS"
git push







Author: Saurabh K.D. Singh
Contact: sksingh5087@gmail.com
