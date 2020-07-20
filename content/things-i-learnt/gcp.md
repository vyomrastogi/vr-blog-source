---
title: "Google Cloud Platform"
date: 2020-07-20T00:02:15-04:00
draft: false
weight: 2
---

## GCP AI/ML Services 

### AI Building Blocks 
- AI through simple REST calls 

1. Sight 
	1. Vision API : Derive insights from images 
    2. Video API : content discovery and engaging video experiences

2. Conversation
	1. Dialogflow : to build virtual chat agents and conversational experiences
    2. Cloud Text-to-Speech API : to convert text to human like speech using Wavenet voices 
    3. Cloud Speech-to-Text API : to convert speech to text

3. Language
	1. Translation: to detect and translate between languages 
    2. Natural Language: Reveal the structure and meaning of text through machine learning

4. Structured Data
	1. AutoML Tables: build and deploy machine learning models on structured data
    2. Recommendations AI: delivers personalized recommendations
    3. Cloud Inference API: to run large-scale correlations over time-series datasets

### Cloud AutoML 
- training models on custom data sets 
- custom machine learning models without writing code
- based google's ml algorithms
- AutoML services 
   - Sight
      - Vision
      - Video
   - Language
      - Natual Language
      - Translation 
   - Struture Data
      - Tabular Data

### AI Platform 
- end-to-end ML pipelines on-premises and cloud
- targetted for users who are building custom ml models and want utilize ML pipelines 
- based on Kubeflow, open source ML project based on kubernetes 

General steps in a ML pipeline 

```
Ingest Data
	|
 Prepare
 	|
Pre-Process
	| 
 Discover
 	|
 Develop
 	|
  Train
  	|
Test & Analyze 
	|
 Deploy
```


### AI Hub 
- repository to discover, share and deploy ML Models
- hosted by Google
- hosts plug and play AI components 
- includes components like 
   - Kubeflow Components
   - VM Images
   - Jupyter Notebooks 
   - Trained Models
   - Tensorflow Modules


### Summary

| Product            | Features      | Use Cases  |
| :----------------- |:-------------:| ----------:|
| AI Building Blocks | REST Api Endpoint for vision, language, data| Using AI api in apps |
| Cloud AutoML       | training models based on custom data   |   Training and deploying models on custom datasets |
| AI Platform        | ML pipelines      |   For user to leverage ML pipelines to train and deploy the custom ML models|
| AI Hub| repository for hosting/sharing AI components | Resusing existing components|

