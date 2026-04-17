# Surrogate Modeling of a Binary Distillation Column using DWSIM and ML

## Project Overview
This project develops a Machine Learning surrogate model to predict the performance of a Benzene-Toluene binary distillation column simulated in DWSIM. 

## Folder Structure
- `Report.pdf` : Detailed project report and methodology.
- `distillation_dataset.csv` : The dataset generated from DWSIM.
- `DWSIM_Flowsheet.dwxmz` : The DWSIM simulation file.
- `Code/ML_DWSIM.ipynb` : Jupyter Notebook containing the ML pipeline.
- `Results_Summary.txt` : Summary of model metrics and findings.
- `README.md` : Instructions to run the project.

## Dataset Details
- 30 samples generated via rigorous DWSIM simulation.
- Operating ranges explored:
  - Feed Temperature: 60°C to 90°C
  - Reflux Ratio: 2.0, 2.5, 3.0
  - Feed Composition (Benzene): 0.3 to 0.7
  - Number of Stages: 10 (Held Constant)

## Best Model Selected
**Artificial Neural Network (ANN)** was selected as the final surrogate model due to its superior accuracy (R² > 0.93 across all outputs) and its ability to handle both linear and non-linear column behaviors without overfitting.

## How to Reproduce the Results
1. **DWSIM Simulation:** Open `DWSIM_Flowsheet.dwxmz` to view the rigorous thermodynamic model (Peng-Robinson).
2. **Machine Learning Pipeline:**
   - Open the `Code/ML_DWSIM.ipynb` notebook using Jupyter or Google Colab.
   - Ensure `distillation_dataset.csv` is in the same directory as the notebook.
   - Run all cells. The script will load the data, split it, scale features, train models (LR, RF, ANN), and output the MAE, RMSE, and R2 metrics to verify the ANN's performance.