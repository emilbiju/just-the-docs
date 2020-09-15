---
layout: default
title: CTC Path Decoding
parent: Model Architecture
nav_order: 2
---

# CTC Path Decoding
{: .no_toc }

---

## Model

This module processes the input sequence of path coordinates to predict a sequence of English characters (which must be further transliterated into the Indic language) for the English-to-Indic decoding task and a sequence of Indic characters for the Indic-to-Indic decoding task. Consider an input sequence, {x1,x2,x3,...,xT } containing (x,y) path coordinates along with augmented features described in Section 3. As seen in Figure 2(a), the sequence is passed into a Transformer encoder consisting of a multi-head self-attention sub-layer and a position-wise feed forward neural network, followed by a 2-layer Bidirectional LSTM network (Schuster and Paliwal, 1997) to produce an encoded representation of the sequence. The encoded vector at each timestep is then passed through a fully connected layer with softmax activation to generate a sequence of vectors {h1,h2,h3,...,hT }; where hi ∈R|C|+1,hij istheprobabilityofthejthcharacterattimestepiand|C|+1isthenumberofcharacters including a blank character < b >. The model is trained using the CTC loss function which maximises the sum of probabilities of all frame-level alignments of the target sequence. Concretely, the CTC loss function maximises the probability:

<img src="https://render.githubusercontent.com/render/math?math=p(\textbf{y}|\textbf{x}) = \sum_{\hat{\textbf{y}}\epsilon \mathcal{A}_{ctc}(\textbf{y})}^{}p(\hat{\textbf{y}}|\textbf{x})">
