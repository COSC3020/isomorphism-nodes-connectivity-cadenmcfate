[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/ppBU16qM)
# Isomorphism

Prove that if two graphs $A$ and $B$ have the same number of nodes and are
completely connected, they must be isomorphic. I have started with the formal
definition of isomorphism below. Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$G_1=(V_1 , E_1)$ is isomorphic to $G_2 = (V_2, E_2)$ if there exists a
one-to-one and onto function (bijection) $f: V_1 \rightarrow V_2$ such that $(u,v)
\in E_1$ iff $(f(u),f(v)) \in E_2$.

## Answer

Let $A = (V_A , E_A)$ and $B = (V_B , E_B)$ be two completely connected graphs where $n=|V_A|=|V_B|$. 
We know that each node has a connection to every other node. You can get to any node from any node, you can traverse any combination of nodes you please, and with this fact we can say that no node is unique when stripped of its arbitrary label. Thus, the bijective function that we seek is simply a relabeling of the nodes as follows:

$$
\begin{align}
  f: V_A &\to V_B \\
  a_1 &\mapsto b_1 \\
  a_2 &\mapsto b_2 \\
  &\cdots \\
  a_n &\mapsto b_n
\end{align}
$$

Where $V_A = [a_i]$ for $i = 1...n$ and $V_B = [b_i]$ for $i = 1...n$.
However, the ordering of the vertices is irrelevent. 
In fact, there are $n!$ possible bijections that will work, one for each permutation of $V_A$ mapping to $V_B$.

So, let $f$ be one of these bijections. We have the following:


$$
\begin{align}
  & (u,v) \in E_A \\
  \Rightarrow & f(u),f(v) \in V_B \quad \text{(f is onto)} \\
  \Rightarrow & (f(u),f(v)) \in E_B  \quad \text{(B is completely connected)}
\end{align}
$$

And the other direction,

$$
\begin{align}
  & (f(u),f(v)) \in E_B \\
  \Rightarrow & u,v \in V_A \quad \text{(f is 1-1)} \\
  \Rightarrow & (u,v) \in E_A \quad \text{(A is completely connected)}
\end{align}
$$
