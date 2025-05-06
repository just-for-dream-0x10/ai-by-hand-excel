## Multihead-Attention
===================
Multihead-Attention is a mechanism that allows a model to focus on different parts of the input sequence simultaneously. It is used in the Transformer architecture, which is a deep learning model for natural language processing.

### Advantages
1. It allows the model to focus on different parts of the input sequence simultaneously, which can improve the performance of the model.
2. It can handle longer input sequences, which is important for tasks such as machine translation.
### Disadvantages
1. It can be computationally expensive, especially for large input sequences.
2. It can be difficult to interpret the results, especially for complex tasks.

### Mathematical Principles
#### Attention Formula
$$
Attention(Q, K, V) = softmax(QK^T/√d_k)V
$$

- Q: Query
- K: Key
- V: Value
- d_k: Dimension of Key
- softmax: Softmax function
- /√d_k: Normalization factor

#### Multi-head Calculation
$$
MultiHead(Q, K, V) = Concat(head_1, head_2, ..., head_h)W^O

where head_i = Attention(QW_i^Q, KW_i^K, VW_i^V)
$$

- W_i^Q, W_i^K, W_i^V: Weight matrices for each head
- W^O: Output weight matrix
- Concat: Concatenation function
- h: Number of heads

The multihead attention mechanism is a way to combine multiple attention heads into a single output. This allows the model to focus on different parts of the input sequence simultaneously, which can improve the performance of the model.

###  Computation Process
#### Linear Projection
1. The input sequence is projected into three different spaces: Query, Key, and Value.
Linear Projection: The input sequence is projected into three different subspaces, which are used to calculate the query, key, and value vectors.
2. For each head:
- Calculate the attention weights using the query and key vectors.  $$ Q_h = XW^Q_h \\ K_h = XW^K_h \\ V_h = XW^V_h $$
- Calculate the weighted sum of the value vectors using the attention weights. 
- Concatenate the weighted sums of the value vectors from all heads.


####  Attention Computation
- Culcalte the dot for Q & K $$ QK^T $$
- div the result by √d_k $$ QK^T/√d_k $$
- Apply softmax function to the result $$ softmax(QK^T/√d_k) $$
- Multiply by the value matrix to get the weighted sum

#### Multi-head Concatenation
- Concatenate the output of all headers together
- The final linear transformation is performed by outputting the projection matrix W^O

### Excel File Analysis
####  File Structure
The Excel file shows the complete calculation process of the multi-head attention mechanism through a worksheet, including:

- Input matrix and vector representation
- Linear projection matrix
- Attention score calculation
- Softmax normalization
- Multi-head merging process

#### Key Calculation Steps
1. Input representation: shows the vector representation of the input sequence
2. Linear projection: shows the linear transformation process of Q, K, V
3. Attention score: shows the calculation of Q·K^T/√d_k
4. Softmax normalization: shows the normalization process of attention score
5. Weighted sum: shows the weighted sum of attention score and V
6. Multi-head merging: shows how the output of multiple heads are spliced ​​and projected


### Practical Applications
#### Application Scenarios
- Machine translation
- Text summarization
- Image captioning
- Speech recognition
- etc.

### Comparison with Other Attention Mechanisms
#### Relationship with Self-attention
Multi-head attention is an extension of self-attention, which enhances model capabilities by computing multiple self-attentions in parallel.

#### ### Differences from Traditional Attention
- Traditional attention: usually used in encoder-decoder structure
- Multi-head attention: can be used in various scenarios such as self-attention, encoder-decoder attention, etc.

### Summary
The multi-head attention mechanism captures the relationship in the sequence from different perspectives by computing multiple attention heads in parallel, significantly enhancing the representation ability of the model. It is one of the key factors for the success of the Transformer architecture and has been widely used in various natural language processing and computer vision tasks.