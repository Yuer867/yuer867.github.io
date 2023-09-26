---
layout: default
title: EMO_Harmonizer
description: Emotion-Driven Melody Harmonization via Melodic Variation and Functional Representation
permalink: /emo_harmonizer/
github_link: https://github.com/Yuer867/EMO_Harmonizer
---

## Introduction

In this paper, we propose a novel **functional representation** designed as an alternative to [REMI](https://github.com/YatingMusic/remi), 
a popular event representation that uses note pitch values and chord names to encode symbolic music.

<div align="center">
  <img src="../figures/emo_harmonizer/representation.png" width=500 alt="">
  <figcaption><strong>Fig.1</strong> Illustration of (a) REMI and (b) the proposed functional
representation, differing in note pitch and chord name events.</figcaption>
</div>

This new method takes **musical keys** into account, 
recognizing their significant role in shaping music’s emotional character through major-minor tonality. 

<div align="center">
  <img src="../figures/emo_harmonizer/key_distribution.png" width=500 alt="">
  <figcaption><strong>Fig.2</strong> Key histogram of high/low valence clips from EMOPIA.</figcaption>
</div>

Specifically, our method represents both melody notes and chords with Roman numerals relative to musical keys, 
a **functional format** considering the relationships between notes, chords and scales (major or minor). 

<div align="center">
  <img src="../figures/emo_harmonizer/switch.png" width=400 alt="">
  <figcaption><strong>Fig.3</strong> Illustration of the conversion between letters and Roman numerals in the cases of C major / c minor. The solid line represents a direct one-to-one conversion, while the dotted line stands for a random conversion to either one of them.</figcaption>
</div>

It also allows for melodic variation with respect to keys and addresses the problem of data scarcity for better emotion modeling. 

A Transformer is employed to harmonize key-adaptable melodies, allowing for keys determined in rule-based or model-based manner.

## Harmonization Samples

<h3>Negative Variants for Positive Pieces (Original)</h3>

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>Original</th>
    <th>REMI (trans)</th>
    <th>REMI (rule)</th>
    <th>Ours (rule)</th>
    <th>Ours (model)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sample#1</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/Q1__SJQaaRzD-A_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1__SJQaaRzD-A_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#2</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/Q1_mX-xs3OVhTs_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_mX-xs3OVhTs_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#3</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/Q1_s5b8viFsVJE_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q1_s5b8viFsVJE_2/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#4</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/Q4_22S3w4idugs_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_22S3w4idugs_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Sample#5</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/Q4_cXxGBDgFCs8_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q4_cXxGBDgFCs8_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>


<h3>Positive Variants for Negative Pieces (Original)</h3>

<table class="audio-table">
  <thead>
    <tr class="header">
    <th></th>
    <th>Original</th>
    <th>REMI (trans)</th>
    <th>REMI (rule)</th>
    <th>Ours (rule)</th>
    <th>Ours (model)</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Sample#1</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/Q3_fuCxYrru2S4_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_fuCxYrru2S4_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#2</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/Q3_ii1Jw1-7Ka4_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q3_ii1Jw1-7Ka4_2/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#3</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/Q2_0v2N1ROvEI0_1.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_0v2N1ROvEI0_1/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
    <tr>
      <td>Sample#4</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/Q2_5CEAeMiXKaA_0.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_5CEAeMiXKaA_0/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Sample#5</td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/Q2_jIKX3ShvLxo_2.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/transpose.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/transpose_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/relative_switch.wav" type="audio/mpeg" /></audio></td>
      <td><audio controls=""><source src="../assets/audio_samples/emo_harmonizer/Q2_jIKX3ShvLxo_2/relative_begin.wav" type="audio/mpeg" /></audio></td>
    </tr>
  </tfoot>
</table>

## Authors and Affiliations

* Jingyue Huang  
Research Assistant @ National Taiwan University / Master student @ New York University  
jh8522@nyu.edu  
 
* Yi-Hsuan Yang  
Professor @ National Taiwan University / Joint-Appointed Researcher @ Academia Sinica  
yhyangtw@ntu.edu.tw, affige@gmail.com  
[website](https://affige.github.io/)   

[jekyll-organization]: https://github.com/jekyll
