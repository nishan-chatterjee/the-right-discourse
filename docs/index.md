title: [The 'Right' Discourse on Migration: Analysing Migration-Related Tweets in Right and Far-Right Political Movements]
description: [The rise of right-wing populism in Europe has brought to the forefront the significance of analysing social media discourse to understand the dissemination of extremist ideologies and their impact on political outcomes. Twitter, as a platform for interaction and mobilisation, provides a unique window into the everyday communication of far-right supporters. In this paper, we propose a methodology that uses state-of-the-art natural language processing techniques with sociological insights to analyse the MIGR-TWIT corpus of far-right tweets in English and French. We aim to uncover patterns of discourse surrounding migration, hate speech, and persuasion techniques employed by right and far-right actors. By integrating linguistic, sociological, and computational approaches, we seek to offer cross-disciplinary insights into societal dynamics and contribute to a better understanding of contemporary challenges posed by right-wing extremism on social media platforms.]

<style>
    body {
        background-color: #202124;
        color: white;
    }
</style>

# Topic Modeling
Topic modelling enables the extraction of underlying topic clusters, a task that would be manually impractical and time-consuming. Using the BERTopic framework, the multilingual-e5-large Sentence Transformer model, we find document (in our case, tweet) clusters. We finally use LLAMA2 with a custom prompt and 3 representative docs from each topic to create the topic labels. We restrict the clustering to be limited to 40 topics for each sub-corpus for manual analysis.

### French
<iframe src="https://nishan-chatterjee.github.io/the-right-discourse/topic-clusters-french.html" width=1220 height=770></iframe>

### UK
<iframe src="https://nishan-chatterjee.github.io/the-right-discourse/topic-clusters-uk.html" width=1220 height=770></iframe>

# Evolution of Topics over Time
BERTopic also provides methods to visualize the evolution of topics and their representative keywords over time. By analyzing changes in topic distribution and keyword representation, we gain insights into the shifting discourse landscape and emergent themes in social media conversations.

### French
<iframe src="https://nishan-chatterjee.github.io/the-right-discourse/topic-evolution-french.html" width=1300 height=1020></iframe>

### UK
<iframe src="https://nishan-chatterjee.github.io/the-right-discourse/topic-evolution-uk.html" width=1300 height=1020></iframe>

# Persuasion Comparison
Understanding persuasion strategies in tweets is vital for analyzing the dynamic interplay between social media content from political movements, user engagement, and public attention. We fine-tuned an mBART-50 model (Tang et al., 2020) on the textual subpart of the SemEval 2024 Task 4 data on online disinformation campaigns (Dimitrov et al. 2024) for identifying hierarchically organized persuasion techniques. Our model, achieving a 0.63 hierarchical F1 score on the shared tasks English test set, with a potential decrease of up to 10% for corpora of similar sizes for languages not encountered during training (in this case, French). This additionally offers insights into persuasion strategies employed in tweets across the two groups.

<iframe src="https://nishan-chatterjee.github.io/the-right-discourse/persuasion-comparison-with-examples.html" width=1220 height=820></iframe>
