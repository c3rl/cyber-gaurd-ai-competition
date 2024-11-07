# Cyber Gaurd AI
<hr/>
Categorization of cyber-complaints into various predefined categories.

### The Idea
<hr/>
Vector embeddings are the most interesting product/concept that came to true life in the recent AI boom. A vector embedding, an array of a large number of real numbers, represents the position of the given text in a vector space. The dimension of this vector space is usually large, like 768 or 3072, i.e. an array of 768 or 3072 real numbers. The main selling point of this vector array is that it represents the position of the given text in the vector space contextually, semantically, and in terms of meaning. That means a similar text will also reside around the same position in the space.
<br />
<br />
This enables vector embeddings to be very useful for search, recommendations, classification, etc.
<br />
<br />
The idea of vector embeddings is old but the recent development in the field of AI particularly Deep Neural Networks has enabled vector embedding models to extract the meaning and context of the given text.
<br />
<br />
So, our method of solving text classification of user written complaints will extensively use the new age DNN vector embedding models.

### The Method
<hr />
We have written two methods to try to solve the challenge.
<ol>
<li>Embedding the text (user complaint) directly and indexing it in a vector database collection together with the category and sub-category metadata.
<li>Summarising a batch of texts (user complaints) from a similar category and sub-category using an LLM and then indexing it in a different vector database collection together with the category and sub-category metadata.
<li>Calculating average embedding of every category and subcategory pair and using these embeddings for predicting category and subcategory. It is the fastest method.
</ol>
The next step is to perform a near vector search and retrieve the 10 nearest documents and use the metadata to guess which category and subcategory the input text (user complaint) might belong to.

### Findings
<hr />
It can be seen that in some cases when the predicted categories and subcategories do not match the expected values (when using test data), the predicated can either FIT or the predicted category and subcategories are a BETTER FIT than the expected values. 
<br />
The time to predict the classification is always less than 400 milliseconds. In production, it can possibly reach to only 10s milliseconds. 

### Further Development
<hr />
Using DNN vector embedding models has enabled a huge future development prospect. The following steps can be taken in the future for better results.
<ol>
<li> Fine tuning available embedding models like nvidia/NV-Embed-v2 and jinaai/jina-embeddings-v3.
<li> More detailed summarization with manual human intervention.
<li> Transforming the user complaints using prompt engineering methods for better feature extraction. 
</ol>