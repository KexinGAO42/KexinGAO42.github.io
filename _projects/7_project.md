---
layout: page
title: Model Fine-tuning for Enhanced Accent Recognition
description: Finetune wav2vec2.0-based model with relatively small amount of within-speaker African American English(AAE) speech data.
img:
importance: 3
category: course
---

**Keyword:** ASR, Fine-tuning, Deep Learning, Responsible AI

## Abstract

•	Fine-tuned Wav2Vec (ASR model) with CORAAL dataset to improve model performance on recognizing African American English accent.
•	Preprocessed data by segmenting audio and normalizing transcription text; transformed data into JSON format.
•	Leveraged the PyTorch Lightning Flash framework to streamline model fine-tuning processes, strategically freezing the backbone model until a specified epoch to optimize training stability; achieved a significant improvement from 0.4 to 0.2 using small amount of within-speaker speech data.


## Code

[link](https://github.com/KexinGAO42/Fine-tuning-avc2vec2.0-with-AAE-speech-data)

