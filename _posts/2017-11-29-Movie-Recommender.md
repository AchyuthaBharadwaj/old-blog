---
title: "Movie Recommendation System"
date: 2017-11-29
tags: [Machine Learning, Movie Recommender, Recommendation System, Python]
excerpt: "Implemented a Personalized Movie Recommendation system using collaborative filtering/probabilistic relevance feedback techniques." 
mathjax: "true"
toc: true
---

[link to repository](https://github.com/theskullcrusher/MWDBProject)

## Abstract

The goal of this project is to Implement a Personalized Movie Recommendation system using collaborative filtering/probabilistic relevance feedback techniques and an r nearest neighbor movie classification system, decision tree, random forest, n-ary SVM, LSH using database from IMDB-MovieLens with PCA, SVD, LDA and CPD models.

## Phase 1
Implemented a program which considers,
* all the movies an actor played,
* a given genre,
* all movies watched by a user,  

and creates and stores a weighted tag vector for each using TF, TF-IDF, TF-IDF-DIFF, P-DIFF1, P-DIFF2 models.  

## Phase 2
* Generating and identifying top latent semantics using PCA, SVD and LDA.
* CP decomposition of Tensors to identify non-overlapping groups based on their degree of memberships to the top 5 latent semantics.
* Implemented Personalized PageRank algorithm with RandomWalk and ReStarts to identify related movies/actors.
* Based on these techniques, built a minimal version of movie recommender that with given watched movies can identify related movies to recommend. 

## Pahse 3
Implemented a Personalized Movie Recommendation system using collaborative filtering/probabilistic relevance feedback techniques and an r nearest neighbor movie classification system, decision tree, random forest, n-ary SVM, LSH using database from IMDB-MovieLens with PCA, SVD, LDA and CPD models.