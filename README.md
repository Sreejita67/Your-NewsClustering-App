# Your-NewsClustering-App
This Flutter-based mobile app aims to automate the categorization of online news articles based on their content using advanced Natural Language Processing (NLP) and Machine Learning (ML) techniques. The core objective is to build a system that can fetch news articles, preprocess the text using BERT (Bidirectional Encoder Representations from Transformers), and generate semantic embeddings. These embeddings are then clustered using multiple unsupervised learning algorithms such as K-Means, Gaussian Mixture Models (GMM), Agglomerative Clustering (AGNES), and Spectral Clustering.The system also incorporates Sentiment Analysis to gauge the emotional tone of each article and Trend Analysis to observe genre-wise news frequency over time. Users can select a country of interest, upon which the app fetches regional news, performs clustering, and displays results including:

1. Predicted genre/category 

2. Scores from different clustering algorithms
    
3. Sentiment Analysis of the article
   
4. Trend chart for current hot genres**

# Technologies used
# **💻 Frontend (Mobile App)**

**Flutter** – Cross-platform UI toolkit for building natively compiled mobile apps.

**Dart** – Programming language used to develop the Flutter app.

**HTTP** – Dart package for API integration.

# **🌐 Backend (API and ML Models)**

**Flask**– Lightweight Python web framework used to serve ML models through a REST API.

**Gunicorn** – WSGI HTTP server for deploying the Flask app.

# 🤖 **Machine Learning & NLP**

**sentence-transformers** -	For generating BERT-based sentence embeddings using all-MiniLM-L6-v2.

**Scikit-learn** – For clustering algorithms (K-Means, GMM, Agglomerative Clustering, Spectral Clustering).

**Pandas & NumPy** – For data manipulation and preprocessing.

**NLTK** – For additional text preprocessing (if used).

**sumy** - Text Summarization using LSA Algorithm

# **News and Content Extraction**

**requests** - For making HTTP requests to fetch news from NewsAPI.

**newspaper3k (newspaper)** - For scraping and parsing full text from news URLs.

**NewsAPI** - External API used to fetch real-time top headlines based on country

# 😊**Sentiment Analysis**

**BERT (Pretrained model)** – For context-aware sentiment classification.

# 🧪 **Development & Testing Tools**

**Postman** – For testing API endpoints.

**VS Code** – IDEs for backend and ML development.

**Android Studio** – IDE for Flutter app development.

# **Model Deployment **

**ngrok** - For exposing the Flask API to the app

# How to Install and Run it?

# **1. Clone the Repository**

git clone <your-repo-url>

cd <your-project-folder>
________________________________________
**# 🧪 2. Set Up Python Backend (Flask + ML)**

# ✅ **a. Create and Activate Virtual Environment (Recommended)**

python -m venv venv

source venv/bin/activate        # For Linux/macOS

venv\Scripts\activate           # For Windows

**# 📦 b. Install Required Python Packages**

pip install -r requirements.txt

Make sure requirements.txt includes:

Flask

requests

newspaper3k

sentence-transformers

scikit-learn

transformers

sumy

nltk

**# 🔑 c. Set Up NewsAPI Key**

In app/services/config.py, add:

NEWS_API_KEY = "your_actual_api_key_here"

**# 📂 d. Download NLTK Resources (if not already present)**

These are required for summarization:

import nltk

nltk.download('punkt')

nltk.download('wordnet')

nltk.download('omw-1.4')

**#▶️e. Run the Flask Server**

python app/main.py      
________________________________________
**# 📱3. Set Up Flutter App (Frontend)**

**# 🧰 a. Install Flutter SDK**

**# 📥 b. Navigate to the Flutter Project Folder**

cd  flutter_app_folder

**📦 # c. Install Dependencies**
flutter pub get

**▶️ # d. Run the Flutter App**
flutter run

Make sure a device/emulator is connected or running.
________________________________________
# **🔄 4. Connecting Flutter with Flask Backend**

•	Ensure your mobile app uses the correct API base URL (your Flask server's IP or domain).

•	For local testing:

o	Use 10.0.2.2 for Android Emulator.

o	Use your PC's local IP address for real devices.

Example:

final baseUrl = "http://10.0.2.2:5000";
________________________________________
# **🧪 Test Workflow** 
1.	User provides URL of a news article
2.	Extracts and summarizes article content.
3.	Generates BERT embeddings.
4.	Runs clustering algorithms (K-Means, GMM, AGNES, Spectral).
5.	Performs sentiment analysis.
6.	Displays results in the app.
   
# **🧪 Test Workflow ( for Trend Analysis)**
1.	Select a country in the app.
2.	App fetches news articles using NewsAPI.
3.	Extracts and summarizes article content.
4.	Generates BERT embeddings.
5.	Runs clustering algorithms (K-Means, GMM, AGNES, Spectral).
6.	Performs sentiment analysis.
7.	Displays results in the app.

# **Key Features of the App**

# **1. Fetch News by Country (Trend Analysis)**

•	Allows users to select a country.

•	Retrieves top headlines using NewsAPI.

•	Supports fallback for India if data is unavailable.

# **2. BERT-Based Embedding**

•	Uses Sentence-BERT (all-MiniLM-L6-v2) to convert article content into semantic embeddings.

•	Enables deeper understanding of news content beyond just keywords.

# **3. Multi-Algorithm Clustering**

•	Applies four powerful clustering algorithms to group news:

o	K-Means

o	AGNES (Agglomerative Clustering)

o	Spectral Clustering

o	GMM (Gaussian Mixture Model)

•	Helps discover topic-based clusters or genres automatically.

# **4. Clustering Evaluation Metrics**

•	Calculates quality of clustering using:

o	Silhouette Score

o	Davies-Bouldin Index

o	Calinski-Harabasz Score

•	Allows comparison of algorithm performance.

# **5. Sentiment Analysis**

•	Performs BERT-based sentiment analysis on each article.

•	Labels articles as Positive, Negative, or Neutral.

•	Gives users an emotional overview of current news.

# **6. News Summarization**

•	Summarizes each news article using Latent Semantic Analysis (LSA) from sumy.

•	Presents users with quick summaries for faster reading.

# **7. News Translation**

•	User can translate the summarized news into any desired language

# **8. Text-to-Voice**

•	User can listen to the summarised voice

# **8. Users - Feedback System**

•	Collects feedbacks from users for improvements.

# **9. Mobile Interface (Flutter)**

•	Simple and intuitive Flutter-based frontend.

•	Allows users to:

o	Select country

o	View headlines

o	Read summaries

o	View clustering results and sentiments

# **10. Backend Integration via Flask**

•	ML processing (BERT, clustering, metrics) is handled via a Flask backend.

•	Ensures fast and scalable processing for real-time results.

# Target Customers / Users

# 1. General News Readers

•	Users who want a personalized, categorized news experience

•	People interested in exploring news by genre rather than just chronological order

# 2. Journalists & Media Professionals

•	Useful for identifying trends and sentiment in public news content

•	Helps monitor how news stories are framed and received across genres and regions

# 3. Researchers & Students (NLP, ML, Media Studies)

•	A practical tool to study text clustering, genre classification, and public sentiment

•	Helps in exploring news bias, genre-based framing, and regional trends

# 4. Data Scientists & Developers 

•	Beneficial for those looking to understand real-world ML/NLP integration 

•	Can inspire similar applications for text clustering and sentiment analysis

# 5. Policy Analysts / NGOs
•	Those monitoring media discourse and public sentiment on critical issues (e.g., healthcare, politics, climate)

•	Helps in identifying regional news patterns and sentiment

# 6. Content Aggregators / Curators
•	Use the clustering mechanism to filter, group, and re-publish news content
•	Enhances automated content curation workflows

# Demonstration of the App

Click on the link : https://1drv.ms/p/c/d5a13b7f69c80c3f/EceTQ3FtL3BFulD-xBC9iaoBr_hqQY6UYT-mP6gg32DHwg?e=y28pF4

# Authors

Sreejita Deb - (https://github.com/Sreejita67)

Rounak Saha - (https://github.com/Rounak36)

Barno Sarkar - (https://github.com/barno-2025)

Ishika Banerjee - (https://github.com/Ishikaban)

Purba Pal - (https://github.com/purba20)
