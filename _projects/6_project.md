---
layout: page
title: Improving Chinese CLIP Performance on Image Classification with Prompt Engineering
description:
img: assets/img/clip.jpg
importance: 4
category: course
---

**Keywords:** Deep Learning; Neural Model Training; Prompt Engineering; CLIP Model; Image Classification

## Abstract

This project aims to enhance the accuracy of CN CLIP in image classification tasks through three types of prompt engineering methods. All three modified models, along with the baseline, utilize both images and texts as inputs to generate the output, which is measured by accuracy—representing the percentage of predicted labels that match the true labels.

The baseline of our system is to use the pre-trained CN CLIP to do image classification. The input consists of image input (e.g., images from the benchmark dataset) and text input, which are the class labels translated into Chinese. The output is the model's prediction on the class of the input image. We evaluate the performance by calculating the classification accuracy across the whole benchmark dataset. Since our project is prompt engineering, the only thing that is being changed for the following three modified models in the prompt (e.g., the text input).

Our first experiment of prompt engineering is to extend the text input from pure class labels to three other formats: a set of standard prompts in Chinese (e.g., a photo of [class]); GPT-generated descriptions based on a set of questions directed to the Large Language Model ((e.g., Describe [class] in Chinese); and the combination of both. These text input will be vectorized by the original text encoder of CN CLIP for similarity comparison.

The second experiment is, similarly, to change the textual input to 'a photo of [class]' in Chinese. However, inspired by CoOp, we will transform them into context vectors and optimize these vectors through gradient-based learning before feeding them to the text encoder. We will also try removing the textual input, in which the context vectors will be randomly initialized.

Finally, since text encoders re-trained with cross-lingual prompts performs better on multilingual image-text retrieval than those trained only with English input \cite{carlsson-etal-2022-cross}, we believe combining the encoding produced from both Chinese and English might improve the model performance. Hence, for our last modified model, the text input will be prompts in both English and Chinese, both of which will be fed to the text encoder. The average of the two vectors will be taken for similarity comparison with the image vector.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>

