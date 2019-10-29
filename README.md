# TED Talk Structure

### Main data planned to use: 
1. transcript of speech (cleaned text, or text with sentence level timestamp)  
2. audience rating (inspiring, beautiful, long-winded ... )  
3. machine extracted features (pos/neg emotion, use of pronoun, voice energy ... )

Many more types of data available at Datasets: Metadata, Tone scores, Voice features

### Inspirations:
A. "Awe the Audience: How the Narrative Trajectories Affect Audience Perception in Public Speaking" - CHI 2018

### Methods:
1. Use IBM Watson Tone Analyzer to extract sentence-wise emotion, language, and social scores. 
2. Construct narrative trajectories of stories using the tone scores mentioned above. 
3. Cluster trajectories to find if there exist common trajectory patterns.
4. Do pair-wise regression between tone scores and subjective ratings, identify trajectories that correlates with specific ratings.

### Findings:
1. Possible to predict (AUC = 0.88) the subjective ratings of the audience by analyzing the narrative trajectories. 
2. Some trajectories (for example, a flat trajectory of joy) correlate well with some specific ratings (e.g. “Longwinded”) assigned by the viewers. 

B. "Resonate: Present Visual Stories that Transform Audiences" - Book

The book argues that great speeches organizes its content in a way that attracts audience. Especially switching between "What is" and "What could be" and showing "organizational sign", "question", and "wonderment".
Structure of speech (in terms of how content on "Current state", "Future state" are arranged chronically in a speech) might be the key to great speeches. 

### Key hypothesis:

H1: Structure of speech has predictive power in the viewers' subjective ratings. 
H2: Some structures correlate with some specific ratings assigned by the viewers. 

### Current progress:

Used simple rule-based method to detect the tense of the verb in each sentence. Below are sentence tense trajectory. X-axis is sentence index number (from the first to the last sentence). Y-axis is the past-future dimension (-1 meaning past tense, +1 meaning future tense, 0 means present tense). Yellow and blue lines are rolling means of sentence tense with window size 5 and 10 (sentences) respectively.
The assumption is that when the line is low (meaning sentence tense is mostly past tense), the speaker is likely to be giving examples from the past. When the line is high (meaning mostly future tense), the speaker is probably talking about future prospects and advocate for something. The hope is that "tense trajectory" can be a proxy for the structure of a speech (when speaker gives examples and when speaker advocates for future), so that more tests can be done on whether "good speech structure" exists.

### Difficulty:
Whether this process of detecting tense is robust? Are there better ways to identify structure (using organization word, etc)? Also, clustering algorithm of trajectories need more in-depth study of the original papers that use emotion trajectories.

__________________________________________________________________________

### Another topic with this data: Related talks network 


Node meaning: More blue means published earlier; Bigger size means larger view count; Edge (directed) means related talk relation.

No insights have been extracted from this network so far, not sure what aspect would be meaningful to explore. Many more types of data available at Datasets: Metadata, Tone scores, Voice features which can be used in this graph as well.
