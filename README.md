# Bubble Detection and Instance Segmentation Using YOLO

Object Detection · Instance Segmentation · Deep Learning · Computer Vision

Academic Project | October 2025 – January 2026  
Polytech Clermont – Mathematical Engineering and Data Science  
Authors: Andréa Gélie and Camille Rivière

## 🇬🇧 English

### Project Overview

This academic project investigates the use of deep learning and computer vision techniques to detect and segment gas bubbles in bioreactor images.

Bubble analysis is important for understanding gas–liquid mass transfer processes. In particular, accurately identifying bubble boundaries, sizes and orientations can contribute to more reliable bubble size distribution measurements.

The project compares two approaches based on the YOLO framework: object detection using bounding boxes and instance segmentation using pixel-level masks.

### Objectives

- Detect and localize bubbles in images, including overlapping bubbles.
- Compare object detection and instance segmentation approaches.
- Evaluate the performance of YOLO models across different bubble categories.
- Investigate the impact of small object sizes and class imbalance on model performance.
- Explore how instance segmentation can support more accurate bubble shape and orientation analysis.

### Dataset

The experiments were conducted on a dataset of 512 × 512 pixel images containing annotated gas bubbles.

The dataset included:

- 98 training images.
- 10 validation images.
- Four main bubble categories: back, bord, fore and full.
- Bounding-box annotations for object detection.
- Polygon annotations for instance segmentation.

An additional unidentified class was observed in a small number of training annotations.

### Methodology

#### 1. Data Exploration

Analysis of the distribution of bubble categories, object sizes and annotations to identify potential challenges for model training.

#### 2. Object Detection — YOLO-Det

Training of the YOLO11n model using the Ultralytics framework to detect and classify bubbles through bounding boxes.

The model was trained for 40 epochs with an input image size of 512 pixels.

#### 3. Instance Segmentation — YOLO-Seg

Training of the YOLO11n-seg model to predict individual segmentation masks for each detected bubble.

The model was trained for 55 epochs with an input image size of 512 pixels.

Instance segmentation was investigated as a potential basis for extracting bubble contours and estimating orientation through ellipse fitting.

#### 4. Model Evaluation

Comparison of detection and segmentation performance using:

- Precision and Recall.
- Mean Average Precision (mAP).
- Precision–Recall curves.
- Confusion matrices.
- Training performance curves.

### Key Results

The models achieved different performances depending on the bubble category.

| Bubble category | YOLO-Det mAP50 | YOLO-Seg mAP50 (Mask) |
|---|---:|---:|
| Full | 0.921 | 0.927 |
| Bord | 0.758 | 0.815 |
| Back | 0.134 | 0.256 |
| Fore | 0.085 | 0.177 |

Instance segmentation generally achieved better results than object detection for the evaluated categories.

However, both approaches struggled to distinguish overlapping bubbles, particularly the back and fore categories.

These limitations were associated with the small size of many bubbles, visual similarities between categories and imbalanced class distributions.

### Technologies and Skills

Python · YOLO11 · Ultralytics · Deep Learning · Convolutional Neural Networks · Object Detection · Instance Segmentation · Image Analysis · Model Evaluation

### Repository Contents

This repository presents the methodology, experimental results and conclusions of the project.

- README.md: Project overview, methodology and key findings.
- Project Report: Detailed literature review, experimental setup, model evaluation and results (in French).

### Limitations and Future Improvements

The models successfully localized many bubbles, but classification performance remained uneven across categories.

Potential improvements include:

- Improving the balance between training classes.
- Increasing the number of annotated examples for underrepresented categories.
- Investigating alternative class definitions for visually similar bubbles.
- Further evaluating contour extraction and orientation estimation using segmentation masks.

---

## 🇫🇷 Français

### Présentation du projet

Ce projet académique étudie l'utilisation du Deep Learning et de la vision par ordinateur pour détecter et segmenter des bulles de gaz dans des images de bioréacteurs.

L'analyse des bulles joue un rôle important dans l'étude des transferts de masse gaz-liquide. La caractérisation précise de leurs contours, tailles et orientations contribue notamment à l'analyse de leur distribution de taille.

Le projet compare deux approches reposant sur le framework YOLO : la détection d'objets par boîtes englobantes et la segmentation d'instances par masques de pixels.

### Objectifs

- Détecter et localiser les bulles, y compris lorsqu'elles se chevauchent.
- Comparer les approches de détection d'objets et de segmentation d'instances.
- Évaluer les performances des modèles YOLO selon les catégories de bulles.
- Étudier l'influence de la petite taille des objets et du déséquilibre des classes.
- Explorer l'utilisation de la segmentation pour améliorer l'analyse de la forme et de l'orientation des bulles.

### Jeu de données

Les expériences reposent sur des images annotées de bulles de gaz, de dimensions 512 × 512 pixels.

Le jeu de données comprend :

- 98 images d'entraînement.
- 10 images de validation.
- Quatre catégories principales : back, bord, fore et full.
- Des annotations par boîtes englobantes pour la détection.
- Des annotations polygonales pour la segmentation.

Une classe supplémentaire non identifiée a également été observée dans certaines annotations d'entraînement.

### Méthodologie

#### 1. Exploration des données

Analyse de la répartition des catégories, des tailles des bulles et des annotations afin d'identifier les principales difficultés d'apprentissage.

#### 2. Détection d'objets — YOLO-Det

Entraînement du modèle YOLO11n avec Ultralytics pour localiser et classifier les bulles à l'aide de boîtes englobantes.

Le modèle a été entraîné pendant 40 époques avec des images de 512 pixels.

#### 3. Segmentation d'instances — YOLO-Seg

Entraînement du modèle YOLO11n-seg pour générer des masques de segmentation individuels correspondant aux bulles détectées.

Le modèle a été entraîné pendant 55 époques avec des images de 512 pixels.

La segmentation a été étudiée comme une approche permettant d'extraire les contours des bulles et d'envisager une estimation de leur orientation par ajustement d'ellipse.

#### 4. Évaluation des modèles

Comparaison des performances à partir des indicateurs suivants :

- Précision et rappel.
- Mean Average Precision (mAP).
- Courbes Précision–Rappel.
- Matrices de confusion.
- Courbes d'évolution des performances pendant l'entraînement.

### Principaux résultats

Les performances varient selon les catégories de bulles.

| Catégorie | YOLO-Det mAP50 | YOLO-Seg mAP50 (Mask) |
|---|---:|---:|
| Full | 0,921 | 0,927 |
| Bord | 0,758 | 0,815 |
| Back | 0,134 | 0,256 |
| Fore | 0,085 | 0,177 |

La segmentation d'instances obtient globalement de meilleurs résultats que la détection d'objets sur les catégories évaluées.

Cependant, les deux approches rencontrent des difficultés pour distinguer les bulles qui se chevauchent, particulièrement les catégories back et fore.

Ces difficultés sont notamment liées à la petite taille des objets, à la similarité visuelle entre certaines catégories et au déséquilibre du jeu de données.

### Technologies et compétences

Python · YOLO11 · Ultralytics · Deep Learning · Réseaux de neurones convolutifs · Détection d'objets · Segmentation d'instances · Analyse d'images · Évaluation de modèles

### Contenu du dépôt

Ce dépôt présente la méthodologie, les résultats expérimentaux et les conclusions du projet.

- README.md : Présentation du projet, méthodologie et principaux résultats.
- Rapport de projet : État de l'art, protocole expérimental, évaluation des modèles et résultats détaillés (en français).

### Limites et perspectives

Les modèles permettent de localiser de nombreuses bulles, mais les performances de classification restent inégales selon les catégories.

Plusieurs pistes d'amélioration peuvent être envisagées :

- Rééquilibrer les classes d'entraînement.
- Augmenter le nombre d'exemples annotés pour les catégories minoritaires.
- Étudier une redéfinition des catégories présentant de fortes similarités visuelles.
- Approfondir l'extraction des contours et l'estimation de l'orientation à partir des masques de segmentation.
