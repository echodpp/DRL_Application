---

## Theoretical Integration in DRL Recommender System

### Background
The DRL recommender system is enhanced by integrating methodologies from two significant works in the field:

- **Supervised Advantage Actor-Critic for Recommender Systems**: Introduces Supervised Negative Q-learning (SNQN) and Supervised Advantage Actor-Critic (SA2C), which use negative sampling to address biases in Q-value estimation within RL frameworks for RS. This improves recommendation quality, especially where reward signals are sparse.

- **Temporal-Contextual Recommendation in Real-Time**: Proposes the use of Hierarchical Recurrent Neural Networks (HRNN) for capturing both intra-session and inter-session user dynamics. The HRNN-meta model further incorporates item features and metadata, significantly improving recommendations for "cold-start" items and adapting to real-time user behavior.

### Implementation
The modified DRL model leverages item features through a dense layer, feeding into the existing state representation used for scoring and decision-making. This aligns with the HRNN-meta structure, which combines user and item features for contextual recommendations. The update in loss computation ensures the model learns effectively from both positive and sampled negative interactions, embodying principles from SNQN and SA2C to normalize advantages and mitigate biases.

---
![Screenshot 2023-11-23 at 11 28 36 PM](https://github.com/echodpp/DRL_Application/assets/90811429/d6cf0bb8-0766-4a88-90c0-3e7b4b27b2b1)

## Modifications to the DRL Recommender System

### Overview
The Deep Reinforcement Learning (DRL) recommender system has been modified to incorporate item features for addressing the cold start problem. These modifications aim to enhance the model's ability to recommend items even when limited interaction data is available.

### Changes Made

#### 1. Feature Placeholder
A new placeholder for item features was introduced:

```python
self.feature_vector = feature_vector
```
**Purpose:** This placeholder allows the network to take additional item features as input, which is crucial for generating recommendations for new items (cold start items) that lack sufficient interaction history.

#### 2. Update Scoring Mechanism
The scoring mechanism was updated to integrate item features into the final score calculation:

```python
self.w_f = tf.compat.v1.layers.dense(
    self.feature_vector,
    self.hidden_size,
    use_bias=True,
    activation=None,
)
self.phi_2 = tf.matmul(
    self.states_hidden, self.w_f, transpose_b=True
)
self.final_score = (
    1 - self.lambda_score
) * self.output2 + self.lambda_score * self.phi_2
```
**Purpose:** By blending the original scores (`self.output2`) with the scores derived from item features (`self.phi_2`), the model can leverage additional information about items, enhancing its recommendation capabilities, especially for new items.

#### 3. Cross-Entropy Loss Update
The cross-entropy loss was modified to use the updated final scores:

```python
ce_loss = tf.nn.sparse_softmax_cross_entropy_with_logits(
    labels=self.actions, logits=self.final_score
)
```
**Purpose:** This change ensures that the loss computation aligns with the updated scoring mechanism, allowing the model to learn effectively from the enhanced item representations.

#### 4. Prediction in Evaluation Function
The evaluation function was updated to use the new final scores for predictions:

```python
prediction = sess.run(QN_1.final_score, ...)
```
**Purpose:** To evaluate the model's performance with the new scoring mechanism, ensuring that the item features are utilized during the prediction phase.

#### 5. Feature Matrix in Network Initialization
The network initialization was modified to include the feature matrix:

```python
QN_1 = QNetwork(
    ...
    feature_vector=feature_matrix,
)
QN_2 = QNetwork(
    ...
    feature_vector=feature_matrix,
)
```
**Purpose:** This ensures that the item feature matrix is appropriately passed to the model during initialization, allowing the model to utilize these features right from the start of the training.

### References and Theoretical Background
arXiv:2111.03474 [cs.LG]
Yifei Ma, Balakrishnan (Murali) Narayanaswamy, Haibin Lin, and Hao Ding. 2020. Temporal-Contextual Recommendation in Real-Time. In Proceedings of the 26th ACM SIGKDD International Conference on Knowledge Discovery & Data Mining (KDD '20). Association for Computing Machinery, New York, NY, USA, 2291–2299. https://doi.org/10.1145/3394486.3403278

---
