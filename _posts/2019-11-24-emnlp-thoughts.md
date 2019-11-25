---
layout: post
title:  "emnlp thoughts"
date:   2019-11-24 12:32:45 +0100
categories: blog
---

# EMNLP conference <span style="float:right">hong kong | nov 1-7</span>
There are three major natural language processing conferences every year: ACL, NAACL, and EMNLP. I asked my manager if I could go to the nearest one, EMNLP. To my surprise, he said that Forethought would fully sponsor the trip, so all I had to worry about was learning the most and packing my bags.

<br>

There're a lot of really cool ideas, but I've tried to focus on 3 main ideas,involving semantics, question answering, and pragmatics. I won't cover other impactful and interesting topics like generation/surface realization, linguistics/cognitive modeling, fact verification, translation, morphology, and etc.

## How contextual are contextualized word embeddings? (semantics)
Contextual word embeddings are the state-of-the-art word representations. Unlike lexical (one-hot embedding) and static word embeddings (word2vec, GloVe), contextual word embeddings vary vector representations depending on the surrounding context. For example, say there are two sentences containing a homonym, "the fair lady dressed for the ball" and "the test was not fair". The word "fair" has different meanings, and so require different word embeddings for the same word, Lexical and static word embeddings would treat the word "fair" as the same word. On the other hadn, contextual word embeddings allow you to encode the same words in different word representations depending on the context. Because of this ability, contextualized word embeddings perform state-of-the-art in many tasks.

<br>

Or that's the idea. In ML, there's a antipattern of retroactive explanation. In the above explanation, we assume "word sense", the idea that words have discrete, finite meanings. Since "fair" has 3 meanings (county fair, fair lady, fair trial), we would expect "fair" to have roughly 3 different contextual representations. However, [Kawin's work](https://arxiv.org/pdf/1909.00512.pdf) argues against this. He found that less than 5% of the variance in contextual word embeddings (ELMo, BERT, GPT-2) could be explained by their first principal component. This implies that contextual word representations vary greatly depending on context. Because the variance is so high, it is very unlikely there are only 3 classes of vectors for a particular word like "fair." This argument is strengthened by [Weija's finding](https://arxiv.org/abs/1909.09700) that contextualized word embeddings for the same word are completely different in paraphrased contexts. Kawin and Weija warns us to be careful of our assumptions of what these new, state-of-the-art word embeddings are doing.

## QA is not a task (question answering)
During Matt Gardner's talk about question answering datasets, he mentioned that "question answering is not a task, it's a format." This rang true throughout the conference as many talks focused on a specific type of QA: [multi-hop reasoning](https://arxiv.org/abs/1909.07598), temporal reasoning, [discourse structure](https://arxiv.org/abs/1908.05803), [situational reasoning](https://arxiv.org/abs/1908.05852), [discrete reasoning](https://arxiv.org/abs/1903.00161), etc. Medium articles about the effectiveness of BERT claim that it achieves "superhuman performance" on question answering, but his talk reminds me that the superhuman performance is on the dataset, not the task. We still have a long way to go before we solve question answering.

<br>

Gardner works at AllenNLP. Here's a [link](https://leaderboard.allenai.org/) to their QA datasets.

## Pragmatics and emergent communication (pragmatics)
One of the big questions I had about language is how humans came up with it. I had a fascinating conversation with my conference roommate about this. He's a 5th year linguistics PhD, so he has some knowledge in the field (here's [his bio](https://linguistics.osu.edu/people/king.2138), to anyone interested). He explained that language is used for communcation, and communication is an act of inducing the speaker's mental state in the listener. Yes, I know, that's a thinker.

<br>

Later, I looked up the theory in wikipedia; it's called "linguistic performance." I'd explain it here, but the article does a better job explaining it [link](https://en.wikipedia.org/wiki/Linguistic_performance).

<br>

The cool thing about this theory is that it suggests reinforcement learning can be used to analyze previously unexplainable linguistic phenomenon. Pragmatics is the study of lingustic phenomenon involving everything out of the scope of linguistics. For example, the emergence of deixis, words that can only be disambiguated by additional context, is not explainable with conventional linguistics because linguistics assumes that everyone using a particular language is using the a particular word in the same way. In the real world, this rarely occurs. Unlocking pragmatics would mean unlocking the secrets to language/dialect formation, [deixis](https://en.wikipedia.org/wiki/Deixis), and other unobservable linguistic phenomena.

<br>

A simple experiment for language emergence would be to create two RL agents with different views of the world that can communicate. If they work towards a common goal requiring communication and succeed, they will have formed some way to communicate, aka their own language. It seems like there are already [people interested in this idea in NeurIPS](https://sites.google.com/view/emecom2019).

## And so until next time...
EMNLP was incredible. The quantity and quality of ideas is astounding, and the speed and depth these world-class researchers operate at is next to none. I'll definitely be attending the next conference, hopefully with some research of my own. 

