#Simulation of the SarsCov-19 Virus 🦠

##Introduction
Beginning in the end of 2019 the SarvCov Virus, also known as the Corona Virus started to have a immense effect on the lives of billions of people in the world. While many people took effort in helping in any way they could, it became clear, that simulating the Virus and it's spread around the globe can become quite useful in different use-cases.

In this short Repo i'll try to implement with given models the virus and it's possible spreading.

##Math
Like everything with sense, we first have to find out what to implement. We define these _variables_ with which we will work as _Nodes_ in the sum $N = \sum \textit{variables}$ which are all dependent from time $t$:

$$
\begin{align}
\small\text{change in Number of healthy people:  }  \frac{\delta g(t)}{\delta(t)} = -\alpha g(t) \cdot a(t)\\
\small\text{change in Number of abnormals:  }  \frac{\delta a(t)}{\delta(t)} = \alpha g(t) a(t) - \frac1qa(t)\\
\small\text{change in Number of sick prople:  }  \frac{\delta k(t)}{\delta(t)} = \frac\kappa q a(t) - \frac1p k(t)\\
\small\text{change in Number of recovered people:  }  \frac{\delta w(t)}{\delta(t)} = \frac{1-\kappa}q a(t) - \frac{1-\Theta}pk(t)\\
\small\text{change in Number of dead people:  }  \frac{\delta v(t)}{\delta(t)} = \frac{\Theta}p k(t)\\
\end{align}
$$

With the parameters

$$
\begin{align*}
\text{Number of people infected per person: } \sigma \\
\text{Infectionrate: } \alpha = \sigma / N > 0 \\
\text{Sicknessrate: } \kappa \in \lbrack0,1\rbrack \\
\text{Deathrate: } \alpha = \Theta> 0 \\
\text{Duration of sickness: } p \\
\end{align*}
$$

The Model in visual Form:

$$
\begin{array}{ccccc}
&& \text{G} && \\
&& {\downarrow}  &&\\
&& \text{A} &&\\
&& \downarrow & \searrow & \\
&& \text{K} &\rightarrow& \text{W} \\
&&\downarrow&& \\
&&\text{V}&&\\
\end{array}
$$

We see that the key value is $\sigma$; if the value i.e. is 1 then everybody gets infected. Which means that the number of infected persons remain the same.
