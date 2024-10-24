# Sentiment-Analysis-for-Agent-Performance-Improvement

![Python](https://img.shields.io/badge/python-3.x-blue)
![Transformers](https://img.shields.io/badge/transformers-4.x-green)
![BERT](https://img.shields.io/badge/BERT-multilingual-brightgreen)
![Google-API](https://img.shields.io/badge/Google_Speech_API-active-red)

## Introduction

This repository provides an implementation of a system that performs **real-time sentiment analysis** on call recordings. The system transcribes speech from audio files, analyzes the sentiment using a pre-trained **BERT model**, and provides actionable feedback based on the sentiment trends in the conversation. 

The system uses **Google Speech Recognition API** and **Hugging Face's Transformers** library for sentiment analysis.

## Prerequisites

To execute this system, several Python libraries are required. These libraries facilitate handling deep learning models, processing audio files, converting speech to text, and analyzing sentiments.

### Required Libraries

- **Transformers**: A library for loading pre-trained models for natural language processing tasks, including sentiment analysis.
- **Pydub**: Used for handling and manipulating audio files.
- **SpeechRecognition**: A tool for converting speech into text using APIs like Google Speech Recognition.
- **Torch**: A framework to run machine learning models, particularly those using deep learning techniques.

To install the required dependencies, run:

```bash
pip install transformers pydub speechrecognition torch
```
## Code Overview
### 1.Importing Libraries :
The necessary libraries for processing audio, performing speech-to-text transcription, and running sentiment analysis are imported.

### 2. Loading the Sentiment Analysis Model :
The system utilizes a pre-trained BERT model **(nlptown/bert-base-multilingual-uncased-sentiment)** to classify the sentiment of transcribed text into five categories, ranging from 1 to 5 stars. This model supports multilingual input, making it well-suited for analyzing call conversations in multiple languages.

### 3. Speech-to-Text Function :
The system uses **Google’s Speech Recognition API** to transcribe audio chunks into text. If the transcription fails due to unintelligible speech or errors with the API, the system gracefully handles the issue by skipping the affected chunk and moving to the next one.

### 4. Real-Time Sentiment Analysis :
The real-time sentiment analysis function processes the audio file in small chunks, usually of 10 seconds. For each chunk:

- The speech is extracted and transcribed into text.
- The sentiment of the transcribed text is analyzed using the sentiment analysis model.
- Actionable feedback is generated based on the detected sentiment.
  
### Actionable Feedback Generation:
The system generates actionable feedback to guide agents during live calls. If the sentiment is negative (indicated by 1 or 2 stars), the system suggests calming the customer and acknowledging their concerns. If the sentiment is positive (indicated by 4 or 5 stars), the system advises maintaining the positive engagement.

## Usage Example
The system processes an input audio file in real-time, analyzing it in 10-second chunks. Each chunk is transcribed, analyzed for sentiment, and evaluated to provide actionable feedback based on the detected sentiment. The history of sentiments and feedback is stored for further analysis to help improve customer service practices.
```bash
audio_file = "/content/InboundSampleRecording-VEED.wav"
sentiment_history, actionable_insights = analyze_sentiment_in_real_time(audio_file)
```
## Conclusion
This **real-time sentiment analysis tool** offers a powerful solution for analyzing customer interactions during calls. By combining speech-to-text conversion, sentiment analysis using a BERT model, and actionable feedback generation, the system enables agents to adapt their behavior in response to customers' emotions, improving the overall quality of service.
