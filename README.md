Modern differentially private (DP) training methods—most notably DP-SGD—suffer severe performance degradation under tight privacy budgets (ε < 1). This degradation is particularly damaging in low-resource or multi-class settings, where gradient noise overwhelms the learning signal.

At the same time, self-supervised representation learning (SSL) models such as SimCLR, DINO, and SimCSE produce normalized embeddings where semantically similar inputs naturally cluster in cosine space. These representations already encode substantial class structure without requiring supervised training.

This work investigates a radically simple alternative to DP fine-tuning:

Release a small, DP-protected set of normalized class representatives (prototypes) on top of frozen SSL embeddings, and classify new examples via cosine similarity.

This removes the need for DP training entirely, reduces DP cost to a one-shot perturbation of class prototypes, and leverages the geometric properties of SSL embeddings (normalization, cosine contrastive losses) to avoid clipping and gradient-noise accumulation.

We ask:

Can a prototype-based DP classifier achieve competitive accuracy in the strict privacy regime (ε < 0.5)?

How does the trade-off between number of prototypes, sensitivity, and privacy budget affect performance?

What theoretical guarantees can be derived for error rates when classification reduces to nearest-prototype selection on the unit hypersphere?

To what extent do SSL representations amplify or stabilize DP noise relative to traditional supervised features?

We provide empirical and theoretical evidence that this approach significantly outperforms DP fine-tuning in the tight-privacy regime, while requiring orders of magnitude less computation.
