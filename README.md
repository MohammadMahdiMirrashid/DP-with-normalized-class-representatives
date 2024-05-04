# DP-with-normalized-class-representatives

This is an ongoing research project. We investigate the release of one frozen embedding (or more?) per class and create a simple differentially private model to predict labels for new data instances. Each sample is classified to the class representative with the highest cosine similarity, which takes an extremely short amount of time compared to training a new classifier with differential privacy on top of the frozen embeddings. Interestingly, while the non-dp version of such an approach performs worse than non-dp fine-tuning, the performance at high privacy guarantees (epsilon < 0.5) is significantly better. The simplicity of this approach allows for theoretical investigations as well. 

We have focused our attention on frozen self-supervised pretrained models (SimCLR, Dino, etc.) that directly encourage higher cosine similarity between similar concepts. The normalization of data instances in such models discards the need for vector clipping, as each embedding is typically projected onto the unit hypersphere by default. Our preliminary results are promising (Dino and SimCLRv2 for vision and SimCSE for NLP), and we are continuing our experiments to possibly write a research paper in the near future, and publicly release the full code.


I wrote the code and developed the main current ideas. For inquiries, email me at amirmm379@gmail.com 
