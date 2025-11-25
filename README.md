<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>House Price Prediction - Google Colab</title>
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <style>
    body {
      font-family: Arial, sans-serif;
      line-height: 1.6;
      margin: 0;
      padding: 0;
      background-color: #f7f7f7;
      color: #222;
    }
    .container {
      max-width: 900px;
      margin: 30px auto;
      background: #fff;
      padding: 25px 30px;
      border-radius: 8px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.08);
    }
    h1, h2, h3 {
      color: #333;
    }
    h1 {
      text-align: center;
      margin-bottom: 15px;
    }
    hr {
      border: none;
      border-top: 1px solid #ddd;
      margin: 20px 0;
    }
    code {
      background-color: #eee;
      padding: 2px 4px;
      border-radius: 3px;
      font-family: Consolas, monospace;
    }
    pre {
      background-color: #111;
      color: #f5f5f5;
      padding: 12px;
      border-radius: 6px;
      overflow-x: auto;
      font-size: 0.9rem;
    }
    table {
      border-collapse: collapse;
      width: 100%;
      margin: 10px 0 20px 0;
    }
    table, th, td {
      border: 1px solid #ccc;
    }
    th, td {
      padding: 8px 10px;
      text-align: left;
    }
    .badge {
      display: inline-block;
      padding: 4px 8px;
      border-radius: 4px;
      font-size: 0.8rem;
      margin-right: 5px;
      background: #e3f2fd;
      color: #0d47a1;
    }
    .section-title {
      margin-top: 25px;
    }
    .highlight {
      background: #fff9c4;
      padding: 4px 6px;
      border-radius: 4px;
    }
    ul {
      margin: 0 0 0 22px;
    }
  </style>
</head>
<body>
  <div class="container">
    <h1>🏠 House Price Prediction (Google Colab)</h1>
    <p style="text-align:center;">
      <span class="badge">Machine Learning</span>
      <span class="badge">Linear Regression</span>
      <span class="badge">Google Colab</span>
    </p>

    <hr />

    <h2 class="section-title">📌 Project Overview</h2>
    <p>
      This project implements a <strong>House Price Prediction Model</strong> using
      <strong>Linear Regression</strong> in <strong>Google Colab</strong>. The model predicts
      the price of a house based on multiple input features such as area, bedrooms,
      bathrooms, and parking.
    </p>
    <p>
      The main objectives of this project are:
    </p>
    <ul>
      <li>Load and explore a house price dataset from Kaggle.</li>
      <li>Perform data cleaning and preprocessing.</li>
      <li>Select important features for prediction.</li>
      <li>Train and evaluate a Linear Regression model.</li>
      <li>Use the trained model to predict house prices for new inputs.</li>
    </ul>

    <h2 class="section-title">📊 Dataset Information</h2>
    <p>
      The dataset is taken from <strong>Kaggle</strong> and contains various features that
      affect house prices. Typical columns include:
    </p>
    <table>
      <thead>
        <tr>
          <th>Feature</th>
          <th>Description</th>
        </tr>
      </thead>
      <tbody>
        <tr>
          <td><code>area</code></td>
          <td>Size of the house (in square feet)</td>
        </tr>
        <tr>
          <td><code>bedrooms</code></td>
          <td>Number of bedrooms</td>
        </tr>
        <tr>
          <td><code>bathrooms</code></td>
          <td>Number of bathrooms</td>
        </tr>
        <tr>
          <td><code>stories</code></td>
          <td>Number of floors/stories</td>
        </tr>
        <tr>
          <td><code>parking</code></td>
          <td>Number of parking spaces</td>
        </tr>
        <tr>
          <td><code>price</code></td>
          <td><strong>Target variable</strong> – house price</td>
        </tr>
      </tbody>
    </table>

    <h2 class="section-title">🛠️ Technologies Used</h2>
    <ul>
      <li><strong>Python</strong> (3.x)</li>
      <li><strong>Google Colab</strong></li>
      <li><strong>Pandas</strong> &amp; <strong>NumPy</strong> for data handling</li>
      <li><strong>Matplotlib</strong> / <strong>Seaborn</strong> for visualization</li>
      <li><strong>scikit-learn</strong> for Linear Regression &amp; metrics</li>
    </ul>

    <h2 class="section-title">🔎 Workflow in Google Colab</h2>
    <ol>
      <li><strong>Import required libraries</strong></li>
      <li><strong>Load dataset</strong> (from Kaggle or uploaded CSV)</li>
      <li><strong>Explore data</strong> (head, describe, info, correlations)</li>
      <li><strong>Handle missing values</strong> (drop/fill as needed)</li>
      <li><strong>Feature selection</strong> and optionally feature scaling</li>
      <li><strong>Train-test split</strong> using <code>train_test_split</code></li>
      <li><strong>Train Linear Regression model</strong></li>
      <li><strong>Evaluate model</strong> with MAE, MSE, and R² score</li>
      <li><strong>Predict prices</strong> for new input data</li>
    </ol>

    <h2 class="section-title">🚀 How to Run in Google Colab</h2>
    <ol>
      <li>Open <span class="highlight">https://colab.research.google.com</span>.</li>
      <li>Click <strong>File &gt; Upload notebook</strong> and select your
        <code>.ipynb</code> file, or create a new notebook.</li>
      <li>Upload the dataset (<code>.csv</code>) to the Colab environment:
        <ul>
          <li>Click on the folder icon on the left sidebar.</li>
          <li>Click the upload icon and choose your dataset file.</li>
        </ul>
      </li>
      <li>Update the dataset path in the notebook if necessary.</li>
      <li>Run each cell in order using <strong>Shift + Enter</strong>.</li>
    </ol>

    <h2 class="section-title">🧠 Model Description</h2>
    <p>
      The project uses a <strong>Linear Regression</strong> model from
      <code>sklearn.linear_model</code>.
    </p>
    <p>
      General form of the model:
    </p>
    <pre>
Price = b₀ + b₁ × area + b₂ × bedrooms + b₃ × bathrooms + ...</pre>

    <h2 class="section-title">✅ Evaluation Metrics</h2>
    <p>The model is evaluated using:</p>
    <ul>
      <li><strong>Mean Absolute Error (MAE)</strong></li>
      <li><strong>Mean Squared Error (MSE)</strong></li>
      <li><strong>R² Score</strong></li>
    </ul>
    <p>Example (dummy) output:</p>
    <pre>
R² Score: 0.85
Mean Squared Error: 23452.65
Mean Absolute Error: 110.32
</pre>

    <h2 class="section-title">🏡 Sample Prediction Code</h2>
    <p>Example of predicting the price for a single house:</p>
    <pre><code class="language-python">
# Example order: [area, bedrooms, bathrooms, stories, parking]
sample_input = [[3000, 3, 2, 2, 1]]
predicted_price = model.predict(sample_input)
print("Predicted House Price:", predicted_price[0])
    </code></pre>

    <h2 class="section-title">📁 Project Structure</h2>
    <pre>
House-Price-Prediction/
│
├── House_Price_Prediction.ipynb   # Main Colab notebook
├── dataset.csv                    # Kaggle dataset
└── README.html                    # This HTML README
    </pre>

    <h2 class="section-title">🌟 Possible Improvements</h2>
    <ul>
      <li>Try other models: Random Forest, XGBoost, etc.</li>
      <li>Perform hyperparameter tuning for better accuracy.</li>
      <li>Create a simple web app using Flask or Streamlit.</li>
      <li>Deploy the model using Render/Heroku/Streamlit Cloud.</li>
    </ul>

    <h2 class="section-title">📞 Contact / Usage</h2>
    <p>
      For help with the full Google Colab code, report, or PPT, you can extend this
      project and document your own details here (name, email, GitHub, etc.).
    </p>
    <p>
      Example:
      <br />
      <em>Created by: Your Name<br />
      GitHub: @yourusername<br />
      Email: youremail@example.com</em>
    </p>
  </div>
</body>
</html>
