# LucidGlass, build roadmap

This document is the detailed record of how LucidGlass was planned and built, phase by phase. The README has a short version of this, this is the fuller story.

## Phase 0, design system

Before any machine learning logic existed, the visual language was defined first. Color tokens, a type scale using Space Grotesk for display text and Inter for body copy, a spacing scale, and the frosted glass panel treatment that the whole app is named after. This produced a standalone reference page rather than any working feature, on purpose, so every later screen would pull from the same set of decisions instead of improvising component styles one screen at a time.

## Phase 1, core loop

The first working version. CSV upload with drag and drop, automatic column type detection across numeric, categorical, boolean, and date columns, target column selection, and two algorithms, K Nearest Neighbors and Decision Tree, both implemented from scratch in JavaScript. Results showed accuracy and feature importance. This phase also introduced the column rail, replacing an early flat table that overflowed badly once a dataset had more than five or six columns, and later tuned so peripheral columns stayed bright and legible rather than fading out.

## Phase 2, explainability and polish

Plain English summaries after every training run, a confidence caption describing whether a pattern found was strong, moderate, or weak, and a one page PDF export of the results. This phase also added Linear Regression for continuous targets and Logistic Regression for clean two class problems, along with automatic detection of whether a chosen target was a fair classification problem or actually a continuous number in disguise. A seeded random number generator was added here too, so the same target, algorithm, and dataset combination always produces the same result instead of a new random split on every click.

## Phase 3, depth

Random Forest, built as fifteen bootstrapped Decision Trees with random feature subsampling at every split, voting together on a final prediction. A data health score on the upload screen, scoring missing values, duplicate rows, and heavily imbalanced columns before a target is even chosen. The three sample datasets, Titanic, Iris, and Wine Quality, were also expanded from small slivers into properly sized sample data.

## Phase 4, data insights

An exploratory view of the dataset itself, independent of any target or model. Per column statistics and histograms for numeric columns, top value breakdowns for categorical columns, a correlation grid across every numeric column, and a short plain English list of what stands out, the strongest relationship found, the column with the widest spread, and any missing data. Exportable as its own one page PDF.

## Phase 5, comparison mode and refinement

A compare mode allowing two classification algorithms to be trained on an identical train and test split and viewed side by side. The correlation grid was also corrected here, from a single hue scale that only encoded magnitude, to a proper diverging scale that shows the sign of a relationship, blue for positive, amber for negative, which is the actual data science convention. This phase closed with mobile layout fixes, a favicon, and social share metadata ahead of the first beta push.

## What is intentionally not built yet

KNN and Decision Tree remain classification only, a numeric target routes to Linear Regression instead of forcing a poor fit through a classifier. There is no server side component of any kind, the privacy pitch depends on that staying true. There is no authentication or saved history between sessions, every session starts fresh with a fresh upload.
