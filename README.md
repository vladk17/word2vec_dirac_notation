
# Word2Vec - Dirac notation

First postulate of QM: physical state of a system is represented by a vector Hilbert space<br>
Hilbert space: normalized square integralable functions

Dirac notation - symbols to represent vectors, inner products and operators 

Ket: $|\Psi>$

Bra: $<\Psi|$ - some form of a conjugate to the Ket vector

Braket : $<\Psi|\Phi>$ inner product within Hilbert space

$d$-dimensional vectors for $V$ many words

Probability to find a word $o$ as a context (in vicinity) of a center word $c$ is defined as 
$$p(o|c)=\frac{exp(U_{o}^{T}V_{c})}{\sum_{w=1}^{V}exp(U_{w}^{T}V_{c})}$$

<br>
we take a big long amount of text, we go through each position in the text, for each position of the text we look at a window of size $2m$, we calculate a probability distribution of a word appearing in a context of a central word 
<br>

The objective function is to maximize (over our big long text) the objective function
$$J^{'}(\theta)=\prod_{t=1}^{T}\prod_{\underset{{j}\neq{o}}{-m<=j<=m}}p(w_{t+j}|w_{t};\theta)$$ 
In other words the probabilities that maximize the $J^{'}(\theta)$ over the long text should represent the correct probabilistic relations between the words in this text


After taking a $log$ and negating the sign, our objective becomes to minimize the negative $log$ likelihood
$$J(\theta)=-\frac{1}{T}\sum_{t=1}^{T}\sum_{\underset{{j}\neq{o}}{-m<=j<=m}}log({p(w_{t+j}|w_{t};\theta))}$$
$\theta$ is a vector representation of the words; $T$ all possible positions of a central word (so, $\frac{1}{T}$ is a "per word" normalization)
