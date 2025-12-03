# Markov-Chain-Lyric-Generator
This is a github repository for a my final presentation to repersent Nicki Minaji Lyrics via Markov Chains for the Duke CS232 course(cross listed as Math 240), for fall of 2025. This contains dataset, code, and final presentation.
# PROJECT OVERVIEW:
Comparing the quality of Markov chains with varying word overlap to train an NLP model to create new lyrics. We measure how the number of words in the chain affects creativity vs. memorization ("overfitting").
# OBJECTIVE:
Find the optimal balance between:
Word overlap (context size) - How many previous words the model considers
Sentence length - How long generated lyrics should be
Avoiding overfitting - Ensuring generated text is creative, not just copied
# KEY METRICS:
X-value: Amount of words in the chain (starting at 2 → 10)
Y-value: Percentage of Replicated N-Grams (measures "overfitting")
### MARKOV CHAIN THEORY:
A Markov chain is a stochastic model that predicts the next word based only on the previous 'k' words (the "context"). The "memory" of previous words is limited to this fixed context size.
### PARAMETER EXPLANATION:
k (context size): Number of previous words considered
k=1: No overlap (only current word matters)
k=2: 1-word overlap
k=3: 2-word overlap, etc.
Word overlap = k-1
### EXAMPLE:
If k=3 and we have "I love you", the model learns transitions from context ("I", "love") → next word "you"
### OVERFITTING DEFINITION:
When a model memorizes training data instead of learning patterns. In our case: generated lyrics exactly match training lyrics.
### OVERFITTING SCORE CALCULATION:
Generate many sentences with given parameters (k, L)
Count how many exactly match any training sentence
Percentage = (matches / total_generated) × 100%
GOAL: Low overfitting score (ideally < 5%) High score = model is copying, not creating
## ANALYSIS OF RESULTS:

From our visualizations and data, we can see:
1. Very low overlap (0-1 words) → Too random, no coherent structure
2. Very high overlap (4-5 words) → Too much memorization, high overfitting
3. Medium overlap (2-3 words) → Best balance

Similarly for sentence length:
1. Very short sentences (<3 words) → Incomplete thoughts
2. Very long sentences (>8 words) → Hard to maintain coherence
3. Medium length (4-7 words) → Works best

Based on our results, the optimal parameters are:
k_best = 3 (2-word overlap)
L_best = 6 (4 actual words after removing START/END)
Overfitting: < 1% (excellent - very creative)

WHY THIS WORKS:
2-word overlap captures enough context for coherent flow
4-word sentences match rap lyric structure
Low overfitting means truly generative, not just copying

GENERATED VERSE QUALITY: Verse 3 received the highest ratings from AI evaluators:
Nicki Minaj style: 5/10 (best of all)
Rap quality: 3-4/10 (most structured)
English quality: 4-7/10 (most coherent)
## KEY INSIGHT: 
Markov chains with moderate context (2-3 word memory) are surprisingly effective at mimicking artistic style while maintaining creativity.
## PRACTICAL APPLICATION: 
This methodology can be applied to any artist's lyrics to create stylistically similar but original content.
