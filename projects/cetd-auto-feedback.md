---
layout: post
title: 'Automated Teacher Feedback'
---


### NOTE: This project page is still under construction

While working for the Emotive Computing Lab at CU Boulder I was responsible for the development and maintenance of the Teacher Talk Automated Feedback Tool. This application would take in audio recordings of teacher classroom sessions and generate formative feedback for teachers to use to improve their classroom discourse. Teachers would record their classroom sessions while wearing a high-quality microphone and upload the recording to a shared dropbox location where it was then processed by the automated feedback pipeline. The recording was first screened to meet basic requirements (appropriate file size, proper naming conventions, etc.) before being automatically transcribed into text via IBM Watson's speech-to-text service. The transcribed speech was then transformed into a proper file format and fed into local BERT models which classified the speech into one of several categories. The results were then stored in a NoSQL database on Google Cloud before being served to the teachers in a website interface. 

My primary role was to develop and maintain the pipeline. This included:
- Adding features to the pipeline
- Monitoring data ingests and fixing processing failures 
- Updating, evaluating, and redeploying BERT language models for prediction
- Being the technical expert for end users and collaborators


A common point of frustration for teachers with respect to their professional development is the scarcity of reliable feedback on their pedagogy. Most teachers receive feedback by way of classroom observations, but due to prohibitive costs, these events are rare at best, happening for many teachers about once a year. With this tool, teachers can gain insight into their classroom speech regularly and reliably. When teachers who had been using the pipeline for 10 sessions were interviewed on their experiences and opinions about the tool, they expressed interest, excitement, and, most importantly, confidence in the Teacher Talk Tool to improve their own pedagogy.
