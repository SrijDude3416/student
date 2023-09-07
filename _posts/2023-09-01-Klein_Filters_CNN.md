---
toc: true 
comments: true 
layout: default 
title: KNN's and their Application 
description: An overview of the application of Klein filters to CNN's to increase generalizability of these networks during low data scenarios.
type: hacks 
courses: { compsci: {week: 2} }
---

# TCNN's: What Are They? Why?

TCNN's, or Topological Convolutional Neural Networks is a type of convolutional neural network that utilizes geometric objects as filters in convolutions to improve the interpretability and generalizability of models. 

## The KNN:


Created by Dr. Carlsson et. al, the KNN (Klein Neural Network) is a TCNN that utilizes filters derived from the geometry of the edges of the Klein bottle. Carlsson et. al found that intermitten placement of these layers in Deep CNN networks greatly increases generalizability in image classification problems. 


## Why the Klein Bottle?


First, it's important to understand that it's been found that deep CNN's, on aggregate, organize their learned features in a way that reflects meaningful spatial relationships. As such, it's also been found that patches within these natural images cluster around the edges of Klein Bottles. Due to this, using these edges as weights provided to the CNN's not only provides a more reliable "pathway" for the model to build through, it also increases interpretability of the model. It does so by showing exactly which edges or features the model is looking for. 


<img src="/student/images/kleinfilterimage.png">
_Sample of a Traditional CNN filter vs. Circle filter (CF) vs. Klein filter (KF):_


## Great but why is this on your blog?
I'm currently conducting an independent project, trying to see if this approach can be extrapolated to the field of semantic segmentation and improve upon currently existing networks such as ResNet, to improve performance in similar low-data fields. 

