## Influence Ranking in Multi-layered Networks

### Data Structure

$$
\begin{bmatrix}
   M_{11} & M_{12} & \cdots & M_{1g} \\
   M_{21} & M_{22} &        & \vdots \\
   \vdots &        & \ddots &        \\
   M_{g1} & \cdots &        & M_{gg}
\end{bmatrix}
$$

We have size of layer $\alpha = i$ and size of layer $\beta = j$, that $M_{\alpha\beta}$ has the size $i \times j$.

## Cross-layer Connectivity

$$
M_{\alpha\beta}, (\alpha \neq \beta) =
\begin{bmatrix}
W^{\alpha\beta}_{11} & \cdots & W^{\alpha\beta}_{1j} \\
\vdots               & \ddots & \vdots               \\
W^{\alpha\beta}_{i1} & \cdots & W^{\alpha\beta}_{ij}
\end{bmatrix}
$$

## Within-layer Connectivity

$$
M_{\alpha\alpha} =
\begin{bmatrix}
A^{\alpha}_{11} & \cdots & A^{\alpha}_{1i} \\
\vdots          & \ddots & \vdots          \\
A^{\alpha}_{i1} & \cdots & A^{\alpha}_{ii}
\end{bmatrix}
$$
