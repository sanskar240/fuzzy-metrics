# Fuzzy Kappa Annotation Evaluation for Temporal Validity

This project implements the **Fuzzy Kappa** evaluation metric to measure the agreement between multiple annotators on temporal validity annotations. The annotations are based on temporal axes that describe different aspects of events in sentences. The evaluation is performed using a **similarity matrix** to account for the degree of agreement between annotators' label assignments.

## Temporal Axes

Each subtext in a sentence is assigned one of the following temporal axes:

1. **Main Axis**: Represents verifiable events along a timeline.
2. **Intention Axis**: Describes someone's intention, desire, or plan.
3. **Opinion Axis**: Represents subjective viewpoints, expectations, or beliefs.
4. **Hypothetical Axis**: Describes conditional or hypothetical events.
5. **Negation Axis**: Identifies events explicitly stated as not occurring.
6. **Generic Axis**: Refers to general truths or recurring phenomena.
7. **Static Axis**: Captures static states or recurring patterns.

Each annotator assigns a temporal axis to each subtext in a sentence, and the **Fuzzy Kappa** score is used to evaluate the agreement between multiple annotators.

## Fuzzy Kappa Metric

The Fuzzy Kappa score is calculated based on the **similarity matrix**, which defines the degree of similarity between pairs of axes. The metric computes the observed agreement (\(P_o\)) and the expected agreement (\(P_e\)) between the annotators, and the Fuzzy Kappa score is given by the formula:

\[
\kappa = \frac{P_o - P_e}{1 - P_e}
\]

Where:
- \(P_o\) is the observed agreement, based on the similarity of the labels assigned by the annotators.
- \(P_e\) is the expected agreement, calculated using the distribution of labels across the annotators.

### Similarity Matrix

The similarity matrix defines the level of agreement between each pair of axes. For example, the similarity between the **Main Axis** and **Intention Axis** might be 0.6, while the similarity between the **Main Axis** and **Hypothetical Axis** might be 0.4. These values are used in the Fuzzy Kappa formula to calculate the agreement between annotators.

| From\To      | Main Axis | Intention Axis | Opinion Axis | Hypothetical Axis | Negation Axis | Generic Axis | Static Axis |
|--------------|-----------|----------------|--------------|-------------------|---------------|--------------|-------------|
| Main Axis    | 1.0       | 0.6            | 0.5          | 0.4               | 0.3           | 0.5          | 0.7         |
| Intention Axis | 0.6     | 1.0            | 0.7          | 0.5               | 0.3           | 0.6          | 0.4         |
| Opinion Axis | 0.5       | 0.7            | 1.0          | 0.6               | 0.4           | 0.5          | 0.3         |
| Hypothetical Axis | 0.4  | 0.5            | 0.6          | 1.0               | 0.5           | 0.4          | 0.3         |
| Negation Axis | 0.3      | 0.3            | 0.4          | 0.5               | 1.0           | 0.4          | 0.2         |
| Generic Axis | 0.5       | 0.6            | 0.5          | 0.4               | 0.4           | 1.0          | 0.6         |
| Static Axis  | 0.7       | 0.4            | 0.3          | 0.3               | 0.2           | 0.6          | 1.0         |

The similarity matrix is used to calculate the **observed agreement** (\(P_o\)) between the two annotators, and the **expected agreement** (\(P_e\)) is calculated based on the distribution of labels.

## Usage

To calculate the Fuzzy Kappa score for temporal validity annotation, the following steps are performed:

1. **Prepare the Dataset**: The dataset should contain the sentences being annotated along with the temporal axes assigned by each annotator.
2. **Run the Script**: Use the provided Python script to load the dataset and compute the Fuzzy Kappa score. The script will calculate the observed and expected agreements using the similarity matrix, then compute the final Fuzzy Kappa score.
3. **Interpret the Result**: The resulting Fuzzy Kappa score indicates the level of agreement between the annotators. A score closer to 1 means higher agreement, while a score closer to 0 indicates lower agreement.

This approach provides a more nuanced evaluation of annotation consistency, accounting for partial agreement between the assigned temporal axes.

## Conclusion

The Fuzzy Kappa metric is an effective way to evaluate inter-annotator agreement in temporal validity tasks. By incorporating a similarity matrix to quantify the degree of agreement between axes, it allows for a more precise and flexible evaluation of annotation consistency.

