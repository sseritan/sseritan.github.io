---
layout: post_page
category: blog
img: elem_rank_sparsity.svg
title: Element and Rank Sparsity
description: Why force your computer to do more work than necessary?
---
# Element and Rank Sparsity

Algorithm design courses usually spend a lot of time on concepts such as optimizing hardware use (e.g. utilizing fused multiply-add operations or packing linear algebra into matrix-matrix multiplies) or memory access patterns (e.g. ensuring coalesced reads/writes or reducing cache misses).
However, it is often the case we can exploit certain properties of the data, such as sparsity, to gain additional computational efficiency.

In a nutshell, sparsity implies that there is a more compact representation for the data.
Leveraging this alternate representation allows us to design algorithms that avoid doing more work than necessary.

Below, I discuss how element and rank sparsity can be applied to matrices to demonstrate what these representations look like in practice.

## Element Sparsity

Perhaps the easiest example of sparsity is element sparsity (shown in the top panel of the figure above).
In a matrix that is element sparse, there are only a few large entries and the majority are zero (or small enough to ignore).
Obviously, dense operations like standard matrix-vector or matrix-matrix multiplies involve a lot of wasted effort multiplying or adding 0.

In this case, the alterate representation is fairly straightforward.
Instead of storing the full $$N^2$$ elements, we instead only store the non-zero elements and their indices.
The figure shows an example of a nested list structure, where the inner lists store entries by row (often known as Compressed Sparse Row).
Another common representation is a dictionary or map from the index to the entry (often called Dictionary of Keys).
These data structures are less efficient to traverse, but the savings from skipping the majority of the entries are well worth it.

Things get even more interesting when combining element sparsity with iterative algorithms.
For example, many electronic structure methods rely on a self-consistent procedure to generate the electronic wavefunction.
Conventionally, this procedure takes the result from one iteration as the guess to the next iteration.
However, it is more efficient to try and solve for the *difference* between the last iteration and the current one.
Element sparsity can be greater leveraged in this "incremental" procedure since the differences are much smaller than the entries themselves.


## Rank Sparsity

Rank sparsity can harder to see by eye than element sparsity.
In this case, the matrix may be dense but have some underlying structure;
in other words, the matrix contains a lot of redundant information.

The typical representation of rank sparsity is an outer product between two smaller matrices, as shown in the bottom panel of the figure above.
These smaller matrices are often obtained through the singular value decomposition (SVD), where only the outer products that correspond to large singular values are kept.

In this case, the data structures of the alternate representation are still matrices.
However, exploiting rank sparsity properly can be more challenging algorithmically.
For example, an algorithm that can build each individual entry can not be used since the low-rank representation essentially splits each element into several important contributions.\\
Despite these difficulties, many quantities in electronic structure inherently contain some hidden underlying structure because they are based on the laws of physics;
as a result, rank sparsity plays an important role in many of our algorithms for quantum chemistry.

You can check out [this paper]({{ site.baseurl }}{% post_url /papers/2018-06-11-rrfci %}) to read about my contributions on applying rank reduction techniques to full configuration interaction, an electronic structure method that formally captures electron correlation exactly but scales factorially.
