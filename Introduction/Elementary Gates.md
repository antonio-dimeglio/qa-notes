The most basic 1-qubit gates are the **Pauli Gates**, which are:
###### Pauli-$X$
The $X$ gate, a.k.a. bit flip gate, represented by the unitary 
$$
X =
\begin{pmatrix}
0 & 1 \\
1 & 0
\end{pmatrix}
$$
I.e., it swaps $\ket{0}$ into $\ket{1}$ and viceversa. 
###### Pauli-$Z$
The $Z$ gate, a.k.a. the phaseflip gate, which puts a $-$ in front of $\ket{1}$ and is represented by
$$
Z = 
\begin{pmatrix}
1 & 0 \\
0 & -1
\end{pmatrix}
$$
#### Phase gate $R_{\phi}$
The $R_\phi$ gate rotates the phase of the $\ket{1}$ state by an angle $\phi$, i.e. 
$$
R_{\phi}\ket{0} = \ket{0} \;\;\;\;
R_{\phi}\ket{1} = e^{i\phi}\ket{1}
$$
this transformation corresponds to the unitary matrix
$$
R_{\phi}
\begin{pmatrix}
1 & 0 \\
0 & e^{i\phi}
\end{pmatrix}
$$
Pauli$-Z$ is a special case of $R_\phi$ because $e^{i\pi} = -1$.
#### Hadamard gate $H$ 

The Hadamard gate is probably the most important $1$-qubit gate, which performs the Hadamard transform, that is:
$$
\begin{array} 
- H\ket{0}=\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}) \\
 H\ket{1}=\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})
\end{array}
$$
The unitary matrix is
$$
\frac{1}{\sqrt{2}}
\begin{pmatrix}
1 & 1 \\
1 & -1
\end{pmatrix}
$$
What happens if we apply $H$ to $\ket{0}$ and then measure the probability of observing $\ket{0}$? 
By applying the Born rule we have
$$
P(\ket{0}) = |\bra{0}\ket{\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})}|^2 
$$
$$
P(\ket{0}) = |
\frac{1}{\sqrt{2}}
\begin{pmatrix}1, 0\end{pmatrix}
\begin{pmatrix}1 \\ 1\end{pmatrix}
|^2= \frac{1}{2}
$$
i.e. there is 50% probability of observing $\ket{0}$.

To simplify some mathematical passages we can express qubit $\ket{0}$ and $\ket{1}$ to which the hadamard gate has been applied using the hadamard base, where $H\ket{0} = \ket{+}$ and $\ket{1} = \ket{-}$.

What happens if we re apply $H$ to $\ket{+}$?

$$
H(\frac{1}{\sqrt{2}}\ket{0} + \frac{1}{\sqrt{2}}\ket{1}) = 
\frac{1}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})+\frac{1}{\sqrt{2}}(\ket{0}-\ket{1})) = \ket{0}
$$

the opposite amplitudes of $\ket{1}$ have canceled each other out, this is known as **destructive interference**.


#### $\text{CNOT}$
The $\text{CNOT}$ is a 2-qubit register which uses two qubits, depending on the value of the first qubit the second is negated, i.e. 
$$

\begin{array}
- \text{CNOT}\ket{0}\ket{b}= \ket{0}\ket{b} \\
\text{CNOT}\ket{1}\ket{b}= \ket{1}\ket{1 - b}
\end{array}
$$
where the first qubit is called the control qubit and the second is the target qubit.
The unitary matrix of this gate is 
$$
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 \\
\end{pmatrix}
$$
More in general, if $U$ is some $n-$qubit unitary matrix then the controlled$-U$ operation corresponds to the following $2^{n+1} \times 2^{n+1}$ unitary matrix:
$$
\begin{pmatrix}
I & 0 \\
0 & U
\end{pmatrix}
$$
where $I$ is the $2^n$-dimensional identity matrix and the two 0s denotes $2^n \times 2^n$ all-0 matrices.