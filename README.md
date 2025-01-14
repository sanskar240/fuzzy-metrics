# Fuzzy Kappa Annotation Evaluation for Temporal Validity

This repository implements the **Fuzzy Kappa** evaluation metric to assess the agreement between multiple annotators in the task of temporal validity annotation. The metric is computed based on the similarity of the axes assigned to different subtexts in the provided sentences. The goal is to measure the consistency of temporal validity annotations across different annotators.

## Table of Contents

1. [Overview](#overview)
2. [Setup](#setup)
3. [Data](#data)
4. [Fuzzy Kappa Metric](#fuzzy-kappa-metric)
5. [Usage](#usage)
6. [License](#license)

## Overview

In the task of temporal validity, sentences are split into smaller subtexts and each subtext is assigned to one of the following temporal axes:

- **Main Axis**: Represents verifiable events along a timeline, representing objective truths.
- **Intention Axis**: Represents someone's intention, desire, or plan.
- **Opinion Axis**: Represents subjective viewpoints, expectations, or beliefs.
- **Hypothetical Axis**: Represents conditional or hypothetical events.
- **Negation Axis**: Identifies events explicitly stated as not occurring.
- **Generic Axis**: Refers to general truths or recurring phenomena.
- **Static Axis**: Captures static states or recurring patterns.

The Fuzzy Kappa score is calculated to evaluate the agreement between two annotators' assignments of axes to subtexts.

## Setup

1. Clone this repository:
   ```bash
   git clone https://github.com/yourusername/fuzzy-kappa-temporal-validity.git
   cd fuzzy-kappa-temporal-validity
