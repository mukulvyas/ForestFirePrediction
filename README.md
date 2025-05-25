# 🔥 Wildfire Risk Prediction Web App

This is a Flask-based web application that uses a pre-trained Ridge Regression model to predict wildfire risk based on environmental parameters.

## 📁 Project Structure

```
├── app.py
├── models
│   ├── ridge.pkl
│   └── scaler.pkl
├── templates
│   ├── index.html
│   └── home.html
├── README.md
```

## 🧠 Model Details

- **Model:** Ridge Regression
- **Scaler:** StandardScaler
- The model and scaler are pre-trained and stored in the `models/` directory.

## 📌 Features

- Input form for wildfire-related environmental data
- Scales input using `StandardScaler`
- Predicts using a Ridge Regression model
- Displays prediction result on a result page

## 🔢 Input Parameters

| Feature     | Description                       |
|-------------|-----------------------------------|
| Temperature | Ambient temperature (°C)          |
| RH          | Relative Humidity (%)             |
| Ws          | Wind speed (km/h)                 |
| Rain        | Rainfall (mm)                     |
| FFMC        | Fine Fuel Moisture Code           |
| DMC         | Duff Moisture Code                |
| ISI         | Initial Spread Index              |
| Classes     | Fire class/category (numeric)     |
| Region      | Region code (numeric)             |

## 🔢 Input Data Format

The model expects the following input features:

| Feature     | Type    | Description                        | Example Value |
|-------------|---------|------------------------------------|--------------|
| Temperature | float   | Ambient temperature (°C)           | 25.3         |
| RH          | float   | Relative Humidity (%)              | 45.0         |
| Ws          | float   | Wind speed (km/h)                  | 12.5         |
| Rain        | float   | Rainfall (mm)                      | 0.0          |
| FFMC        | float   | Fine Fuel Moisture Code            | 85.6         |
| DMC         | float   | Duff Moisture Code                 | 26.7         |
| ISI         | float   | Initial Spread Index               | 7.2          |
| Classes     | float   | Fire class/category (numeric)      | 1 or 0         |
| Region      | float   | Region code (numeric)              | 1 or 0       |

**Note:** All values should be numeric. The model uses these features to scale and predict wildfire risk.

## 💻 How to Run the App

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/wildfire-risk-predictor.git
   cd wildfire-risk-predictor
   ```

2. **Create and activate virtual environment**

   ```bash
   python -m venv venv
   source venv/bin/activate        # Windows: venv\Scripts\activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Ensure model files are present**

   * Place `ridge.pkl` and `scaler.pkl` inside the `models/` folder.

5. **Run the Flask app**

   ```bash
   python app.py
   ```

6. **Open in browser**
   Navigate to `http://127.0.0.1:5000/`

## 📝 File Descriptions

| File/Folder  | Description                                 |
| ------------ | ------------------------------------------- |
| `app.py`     | Main Flask application script               |
| `models/`    | Contains the serialized ML model and scaler |
| `templates/` | HTML templates for frontend pages           |