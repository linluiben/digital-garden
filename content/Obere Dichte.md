---
publish: true
created: 2026-11-08T17:20:40.417Z
modified: 2026-11-09T17:01:24.837Z
---

Sei ${}A \subseteq \mathbb{N}{}$. ${}A{}$ besitzt Dichte ${}d(A){}$ falls der Grenzwert ${}d(A) := \lim_{ n \to \infty } \frac{1}{n} |A \cap [1,n]|{}$ existiert.

#### (1) ${}\bar{d}(A) > 0 \implies \exists m \in \mathbb{N} (\bar{d}(A \cap (A-m)) >0){}$

> [!lemma]+ Lemma: Subadditivität von ${}\bar{d}{}$
> ${}\text{Für } X,Y \subseteq \mathbb{N} \ \text{gilt:} \ \bar{d}(X \cup Y) \leq \bar{d}(X) + \bar{d}(Y){}$
>
> > [!proof]-
> > Seien ${}x_{n} := \frac{1}{n} |X \cap [1,n]|, y_{n} := \frac{1}{n} | Y \cap [1,n]|, Z := X \cup Y, z_{n} := \frac{1}{n} | Z \cap [1,n] |{}$ .
> > Dann gilt für alle ${}n{}$:
> >
> > $$
> > \begin{align}
> > |Z \cap [1,n]| &  \le |X \cap [1,n]| + |Y \cap [1,n]| \\
> > \iff z_{n}  & \le x_{n} + y_{n} \\
> > \implies \overline{\lim_{ n \to \infty }} z_{n}  & \le \overline{\lim_{ n \to \infty }} (x_{n} + y_{n}) \le \overline{\lim_{ n \to \infty }} x_{n}  + \overline{\lim_{ n \to \infty }} y_{n} \tag*{$\square$}
> > \end{align}
> > $$

> [!korollar]+ Korollar: Endliche Subadditivität
> Für $k \in \mathbb{N}$ und $X_1, \dots, X_k \subseteq \mathbb{N}$ gilt
> $\bar{d}\Big(\bigcup_{i=1}^{k} X_i\Big) \le \sum_{i=1}^{k} \bar{d}(X_i).$
>
> > [!proof]-
> > Induktion über $k$:
> >
> > - **Induktionsanfang** $k = 1$: Klar, da beide Seiten gleich $\bar{d}(X_1)$ sind.
> > - **Induktionsschritt** $k \to k+1$: Die Aussage gelte für ein $k \in \mathbb{N}$. Mit $Y := \bigcup_{i=1}^{k} X_i$ folgt
> >   $\bar{d}\Big(\bigcup_{i=1}^{k+1} X_i\Big) = \bar{d}(Y \cup X_{k+1}) \overset{\text{Lemma}}{\le} \bar{d}(Y) + \bar{d}(X_{k+1}) \overset{\text{IV}}{\le} \sum_{i=1}^{k} \bar{d}(X_i) + \bar{d}(X_{k+1}) = \sum_{i=1}^{k+1} \bar{d}(X_i). \qquad \square$

Seien ${}\varepsilon > 0, \quad \beta := \lceil \frac{1}{\bar{d}(A)} \rceil + 1, \quad B_{m} := A \cap (A-m) \ | \ 1 \le m \le \beta{}$.
Seien zudem ${}\bigcup_{i=1}^{\beta} B_{i} =: B \subseteq A{}$ und ${}Q:= A\setminus B{}$, also ${}A = B \sqcup Q{}$.
Angenommen ${}\bar{d}(B) = 0{}$:
Dann gelten: ${}\bar{d}(A) \le \bar{d}(B) + \bar{d}(Q) = \bar{d}(Q) {}$ wegen des Lemmas, zudem\
${} \forall n_{1} < n_{2} \in Q (n_{2}-n_{1} > \beta){}$ wegen ${}Q \cap B = \emptyset{}$ und somit für alle ${}n : |Q \cap [1,n]| \le \frac{n}{\beta} + 1{}$.

> [!proof]-
> Angenommen ${}\exists n_{1}, n_{2} \in Q \subseteq A ( n_{1} < n_{2} \land n_{2}-n_{1} \le \beta){}$:
> Dann gilt:
>
> $$
> \begin{gather}
> \exists m (1 \le m  \le \beta \land m = n_{2}-n_{1}) \implies n_{1} \in B_{m} \subseteq B \implies n_{1} \in B \cap Q = \emptyset \tag*{$\bot$}
> \end{gather}
> $$
>
> Der kleinste Abstand zweier Elemente von ${}Q{}$ muss also grösser als ${}\beta{}$ sein. In jedem Intervall von ${}\beta{}$ aufeinanderfolgenden natürlichen Zahlen gibt es demnach maximal ein Element von ${}Q{}$ und im Intervall ${}[1,n]{}$ maximal ${}n \pmod{\beta} + 1 \le \frac{n}{\beta} + 1{}$ Elemente von ${}Q{}$ (${}+1 {}$ für das angefangene Intervall).
>
> $$
> \tag*{$\square$}
> $$

${}\bar{d}(Q){}$ lässt sich also auf folgende Art abschätzen:

$$
\bar{d}(Q) = \overline{\lim_{ n \to \infty }} \frac{1}{n} | Q \cap [1,n]| \le \frac{1}{\beta} = 
%%\frac{1}{\beta} = %%
\frac{1}{\left\lceil  \frac{1}{\bar{d}(A)}  \right\rceil +1} < \frac{1}{\frac{1}{\bar{d}(A)}} = \bar{d}(A)
$$

Demnach gilt: ${}\bar{d}(A) \le \bar{d}(Q) < \bar{d}(A){}$, ein Widerspruch.

Also war unsere Annahme falsch und wegen des Korollars gilt:

$$
\begin{gather}
\bar{d}(B) > 0 \implies \exists m \le \beta : \bar{d}(B_{m}) > 0 
\tag*{$\square$}
\end{gather}
$$

#### (2) Reicht eine positive obere Dichte?

Ja, ${}\bar{d}(A) > 0{}$ reicht, da wir im Beweis von ${}(1){}$ nie die (untere) Dichte von ${}A{}$ verwendet haben, sondern nur ${}d(A) > 0 \implies \bar{d}(A) > 0{}$.
