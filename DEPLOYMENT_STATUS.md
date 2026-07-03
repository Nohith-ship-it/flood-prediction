# Flood Prediction Model - Deployment Ready

This project is fully prepared for cloud deployment.

## Files Included:
- `Procfile` - Render deployment configuration
- `requirements.txt` - All Python dependencies with gunicorn
- `app.py` - Flask API with CORS enabled
- `public/index.html` - Firebase-hosted frontend
- `flood_xgb_model.pkl` - Trained XGBoost model
- `scaler.pkl` - Data scaler for predictions

## Current Status:
✅ Flask backend: Running locally on http://192.168.29.231:5000
✅ Firebase frontend: https://raising-waters.web.app (deployed)
✅ Model: XGBoost with 96.55% accuracy
✅ CORS headers: Configured

## Issue:
The local Flask backend can't serve HTTPS requests through ngrok due to CORS restrictions on the free tier.

## Solution:
Deploy the Flask backend to Render.com (cloud platform with free HTTPS).

See `RENDER_DEPLOY.md` for step-by-step instructions.

## Quick Stats:
- Model Accuracy: 96.55%
- ROC-AUC: ≥ 0.99
- Training Data: 2,500 years of rainfall records
- Features: 6 (ANNUAL, Jan-Feb, Mar-May, Jun-Sep, Oct-Dec, YEAR)
- Algorithm: XGBoost Classifier
