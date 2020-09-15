---
layout: default
title: Datasets
nav_order: 6
---

# Datasets
{: .no_toc }

## Table of contents
{: .no_toc .text-delta }

1. TOC
{:toc}

---
## Indic-to-Indic Dataset

This dataset contains keyboard traces for 193,658 words across 7 Indic languages. The input is a trace applied over a keyboard of Indic characters and the output is the intended Indic word. 

| Language | Size | Dataset Link | Simulation Code | 
| :------- | :-------- | | :----- |
| Hindi  | 32415 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-arabic.jar) | 4.1.0 |
| Tamil | 24094 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-chinese.jar) | 4.1.0 |
| Bangla | 15320 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-english.jar) | 4.1.0 |
| Telugu | 28996 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-english-kbp.jar) | 4.1.0 |
| Kannada | 26551 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-french.jar) | 4.1.0 |
| Gujrati | 30024 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-german.jar) | 4.1.0 |
| Malayalam | 36258 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-spanish.jar) | 4.1.0 |

## English-to-Indic Dataset

This dataset contains keyboard traces for 104,412 words across 7 Indic languages. The input is a trace applied over a keyboard of English characters and the output is the phonetically similar word in the specified Indic language.

| Language | Size | Dataset Link | Simulation Code | 
| :------- | :-------- | | :----- |
| Hindi  | 29074 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-arabic.jar) | 4.1.0 |
| Tamil | 21523 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-chinese.jar) | 4.1.0 |
| Bangla | 17332 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-english.jar) | 4.1.0 |
| Telugu | 12733 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-english-kbp.jar) | 4.1.0 |
| Kannada | 4877 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-french.jar) | 4.1.0 |
| Gujrati | 8776 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-german.jar) | 4.1.0 |
| Malayalam | 10097 | [download](http://nlp.stanford.edu/software/stanford-corenlp-4.1.0-models-spanish.jar) | 4.1.0 |

## Data Generation
For this work, we curated two datasets for performing the Indic-to-Indic decoding and English-to-Indic decoding tasks across the 7 Indic languages used in the study. The first dataset contains Indic words obtained from the work by Goldhahn et al. (2012) along with corresponding coordinate sequences depicting the path traced on an Indic character smartphone keyboard to input the word. The second dataset contains Indic-English transliteration pairs scraped from Wikidata along with corresponding coordinate sequences for the path traced on an English character keyboard. We use the principle that human motor control tends to maximise smoothness in movement to develop a synthetic path generation technique that models the gesture typing trajectory as a path that minimises the total jerk (Quinn and Zhai, 2018).

For simulating the path between two characters, a minimum jerk trajectory is first plotted between the character locations. We then add two types of noise to the path. The first type adds noise to the starting and ending positions of the path. The (x, y) coordinates for these positions are sampled from a 2D Gaussian distribution centred at the middle of the corresponding key on the keyboard. The second type adds noise to the path between the characters. To perform this, we first sample a coordinate pair (x′, y′) from the uniform distribution of points bounded by the x and y coordinates of the starting and ending points of the path. Following this, we sample points on a path of minimum jerk passing through the 3 points uniformly over time (Wada and Kawato, 2004). This process is repeated for every pair of adjacent characters in the word to obtain a sequence of coordinates that describes the trace. Figure 1(b) shows the trace created for the word budhi using this method. Apart from the (x, y) coordinate pair, we augment the input features for each sampled point with the x and y derivatives at the point and a one-hot vector with value 1 at the index i corresponding to the character on which the point lies on the keyboard.


