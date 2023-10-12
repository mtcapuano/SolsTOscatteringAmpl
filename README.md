## Solutions to Scattering amplitudes in Quantum field theory with Mathematica
<a href="https://mcapuano.com/Solutions_to_Scattering_Amplitudes.pdf">Personal solutions</a> to <a href="">Scattering amplitudes in Quantum field theory</a>, with some related Mathematica notebooks. This is a work in progress (last updated: 12-10-2023).

In the pdf you will find personal detailed solutions to each exercise. Some solutions turns out to be very similar to those suggested in the last chapter of the book, some are different.

In this document I describe the Mathematica notebook I have made inspired by the exercises that can be found in this repository.

### Exercise 1.4: calculating traces of SU(N) generators
The exercise 1.4 has motivated me to write a small Mathematica code, as a short practice, to calculate traces of the generators of SU($N$) in their fundamental representation starting from the completeness relation (1.51).

A generator $T^a$ is expressed as `T[a]`, with other two arguments `T[a,i,j]` we express $(T^a)_i^j$.

The Dirac delta over matrix indices is simply defined as the orderless symbol `delta[i,j]`, together with some basic properties. Analogously the Dirac delta over colour indices is defined as `Delta`.

Traces of 3 and 4 matrices are explicitly defined writing `trace[T[a],T[b],...]` in explicit index form. One of the most delicate point in this code is how to define dummy indices. Clearly, at any call, the indices must be different. The most elegant solution is to define a variable incrementing at any call. Here I have defined indices with `RandomReal[]`.

Implementing the completeness relation as `T /: T[a_, i_, j_] T[a_, k_, l_] = 
 delta[i, l] delta[j, k] - 1/N delta[i, j] delta[k, l]`, relations of all sorts can be directly calculated. I give here some examples, more can be found in the notebook, including those relevant for the exercise. Expressions have been checked with those in <a href="http://home.kias.re.kr/MKG/upload/YPschool/Jungillec.pdf">QCD Practice</a>, counting in the different normalization.

 $\text{Tr}[T^aT^a]=N^2-1$
 
 $\text{Tr}[T^aT^b]\text{Tr}[T^aT^b]=N^2-1$

 $\text{Tr}[T^aT^aT^a]=0$

 $\text{Tr}[T^aT^aT^aT^a]=\frac{1}{N}-2N+N^3$
 
$\text{Tr}[T^aT^aT^b]]=0$

$\text{Tr}[T^aT^aT^bT^c]=\left(N-\frac{1}{N}\right)\delta^{ab}$

$\text{Tr}[T^aT^bT^c]\text{Tr}[T^aT^cT^b]=\frac{2}{N}-3N+N^3$

 
