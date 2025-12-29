YouTube Comment Sentiment Analyzer is an interactive Streamlit web app that turns raw YouTube comments into visual, data-driven insights about how viewers feel.

Overview
This app lets you input or search for a YouTube video, fetch its comments using the YouTube Data API, and run them through a pre-trained sentiment analysis model to classify each comment as Positive, Negative, or Neutral. It then visualizes the results with charts, a word cloud, and highlight cards for the most positive and negative comments.

How it works
You enter a YouTube API key and either paste a video URL or search for a video from within the app.

The app uses the YouTube Data API v3 to fetch top-level comments for the selected video.

Each comment is cleaned (HTML tags, links, and noise removed) and passed to a Hugging Face pipeline("sentiment-analysis") model, which outputs a label and confidence score.

The predictions are mapped into three buckets: Positive, Negative, and Neutral, and stored with metadata like author, likes, and confidence.

Features
Fetch comments by URL or via an in-app search/trending videos panel.

Sentiment classification for each comment with confidence scores.

Sentiment distribution bar chart (Positive vs Negative vs Neutral).

Word cloud showing the most frequent words in analyzed comments.

“Top Comments” section for the most confidently positive and negative comments.

Sample comment cards styled by sentiment (color-coded).

CSV export of analyzed comments for further offline analysis.

Session history to quickly review past analyses.

Tech stack
Frontend & app framework: Streamlit

Data & logic: Python, pandas

APIs: YouTube Data API v3 via googleapiclient

NLP model: Hugging Face Transformers sentiment-analysis pipeline (pre-trained, no extra training in this project)

Visualization: Plotly for charts, wordcloud + Matplotlib for the word cloud

Installation
Install dependencies (example using pip):

bash
pip install streamlit pandas plotly google-api-python-client transformers wordcloud matplotlib
Running the app
From the project directory (where app.py is located), run:

bash
streamlit run app.py
Open the URL shown in the terminal (usually http://localhost:8501) and:

Paste your YouTube Data API key in the sidebar.

Search for a video or paste a YouTube URL.

Click “Analyze Comments” to see the sentiment breakdown, word cloud, and export options.
