---
layout: default
title: Datasets
nav_order: 6
---

# Datasets
{: .no_toc }

---

## Data Generation
For this work, we curated two datasets for performing the Indic-to-Indic decoding and English-to-Indic decoding tasks across the 7 Indic languages used in the study. The first dataset contains Indic words obtained from the work by Goldhahn et al. (2012) along with corresponding coordinate sequences depicting the path traced on an Indic character smartphone keyboard to input the word. The second dataset contains Indic-English transliteration pairs scraped from Wikidata along with corresponding coordinate sequences for the path traced on an English character keyboard. We use the principle that human motor control tends to maximise smoothness in movement to develop a synthetic path generation technique that models the gesture typing trajectory as a path that minimises the total jerk (Quinn and Zhai, 2018).

For simulating the path between two characters, a minimum jerk trajectory is first plotted between the character locations. We then add two types of noise to the path. The first type adds noise to the starting and ending positions of the path. The (x, y) coordinates for these positions are sampled from a 2D Gaussian distribution centred at the middle of the corresponding key on the keyboard. The second type adds noise to the path between the characters. To perform this, we first sample a coordinate pair (x′, y′) from the uniform distribution of points bounded by the x and y coordinates of the starting and ending points of the path. Following this, we sample points on a path of minimum jerk passing through the 3 points uniformly over time (Wada and Kawato, 2004). This process is repeated for every pair of adjacent characters in the word to obtain a sequence of coordinates that describes the trace. Figure 1(b) shows the trace created for the word budhi using this method. Apart from the (x, y) coordinate pair, we augment the input features for each sampled point with the x and y derivatives at the point and a one-hot vector with value 1 at the index i corresponding to the character on which the point lies on the keyboard.

#### Example
{: .no_toc }

```scss
// Print-only styles.
@media print {
  .side-bar, .page-header { display: none; }
  .main-content { max-width: auto; margin: 1em;}
}
```

