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
## Skills Usage

This project leverages a variety of technical and analytical skills, including:

1. **Natural Language Processing (NLP)**:
   - Utilized **Hugging Face's Transformers** to load a pre-trained BERT model for sentiment analysis of multilingual text from call transcriptions.
   - Applied sentiment classification to categorize call sentiments into 5-star ratings, enabling real-time analysis of customer interactions.

2. **Speech-to-Text Conversion**:
   - Employed **Google Speech Recognition API** to transcribe audio data from real-time call recordings.
   - Preprocessed and managed audio files with the **Pydub** library for seamless audio chunking and transcription.

3. **Deep Learning**:
   - Used **PyTorch** to execute the BERT-based sentiment analysis model, enabling efficient inference on transcribed text.
   - Applied model fine-tuning techniques to ensure high accuracy in detecting sentiment during live calls.

4. **Python Programming**:
   - Developed real-time processing pipelines using Python for audio input, transcription, and sentiment classification.
   - Implemented exception handling to manage issues like failed transcriptions due to poor audio quality.

5. **Data Pipeline Design**:
   - Built a real-time processing pipeline to handle audio chunking, speech recognition, and sentiment analysis in sequential steps.
   - Designed the system to provide **actionable feedback** to customer service agents, helping them adjust their responses based on the real-time sentiment of the conversation.

6. **Multilingual Support**:
   - The BERT model used is **multilingual**, making the system capable of analyzing conversations in multiple languages, suitable for global customer service applications.

7. **Real-time Feedback Generation**:
   - Developed an adaptive feedback mechanism that provides real-time suggestions to agents based on the sentiment of customer interactions, helping them enhance service quality.
   
8. **Version Control & Collaboration**:
   - Managed project development using **Git** and hosted the repository on **GitHub**, ensuring collaboration, version control, and seamless integration of code.
   
9. **API Integration**:
   - Integrated third-party APIs like **Google Speech Recognition API** for converting speech to text, providing real-time transcription capabilities.

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
