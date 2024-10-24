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
