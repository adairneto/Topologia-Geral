---
title: MA453 Topologia Geral - Exercícios P2
author: Adair Neto
date: \today
header-includes:
   - \usepackage[brazilian]{babel}
   - \usepackage[left=2cm,right=2cm,top=2cm,bottom=2cm]{geometry}
   - \setlength{\parindent}{1.5em}
   - \setlength{\parskip}{0.5em}
   - \usepackage{indentfirst}
   - \usepackage{helvet}
   - \usepackage[bitstream-charter]{mathdesign}
   - \usepackage[T1]{fontenc}
   - \usepackage{textcomp}
   - \usepackage[frenchmath]{mathastext}
---

## Funções Contínuas

### Exercício 4.1

**Questão:** Seja $f : M \longrightarrow \mathbb{R}$. Diremos que

- $f$ é **semicontínua inferiormente** se $f^{-1}(a, +\infty)$ é aberto em $M$ para cada $a \in \mathbb{R}$.

- $f$ é **semicontínua superiormente** se $f^{-1}(-\infty, b)$ é aberto em $M$ para cada $b \in \mathbb{R}$.

Prove que $f$ é contínua se e só se $f$ é semicontínua inferiormente e semicontínua superiormente.

**Resolução:** 

1. $(\Rightarrow)$ Suponha que $f$ é contínua.
    - Como $(a, + \infty)$ e $(-\infty, b)$ são abertos, então $f^{-1}(a, +\infty)$ e $f^{-1}(-\infty, b)$ são abertos.
2. $(\Leftarrow)$ Suponha que $f$ é semicontínua inferiormente e semicontínua superiormente.
    - Seja $(c, d)$ um aberto de $\mathbb{R}$. 
    - Escreva
    $$
        (c,d) = (-\infty, d) \cap (c, +\infty)
    $$
    - Por hipótese, $f^{-1}(c, +\infty)$ e $f^{-1}(-\infty, d)$ são abertos.
    - Assim,
    $$
        f^{-1}(c,d) = f^{-1}[(-\infty, d) \cap (c, +\infty)] = f^{-1}(-\infty, d) \cap f^{-1}(c, +\infty)
    $$
    - Logo, $f^{-1}(c,d)$ é aberto e, portanto, $f$ é contínua.

### Exercício 4.2a

**Questão:** Sejam $(M, \tau)$ e $(N, \tau')$ espaços topológicos. Mostre que se $\mathcal{B}$ é uma base para $\tau'$, então $f : M \longrightarrow N$ é contínua se e só se $f^{-1}(V)$ é aberto em $M$ para cada $V \in \mathcal{B}$.

**Resolução:** 

1. $(\Rightarrow)$ Suponha que $f$ é contínua.
    - Tome $V \in \mathcal{B}$.
    - Como $V$ é aberto de $N$ e $f$ é contínua, $f^{-1}(V)$ é aberto em $M$.
2. $(\Leftarrow)$ Suponha que $f^{-1}(V)$ é aberto em $M$ para cada $V \in \mathcal{B}$.
    - Dado $U \in \tau'$, existe $\mathcal{C} \subset \mathcal{B}$ tal que 
    $$  
        U = \bigcup_{C \in \mathcal{C}} C
    $$
    - Como 
    $$
        f^{-1}(U) = f^{-1} \left( \bigcup_{C \in \mathcal{C}} C \right) = \bigcup_{C \in \mathcal{C}} f^{-1}(C)
    $$
    - Temos que $f^{-1}(U) \in \tau$, porque é união de abertos. 
    - Logo, $f$ é contínua.

### Exercício 4.2b

**Questão:** Prove que uma função $f : M \longrightarrow N$ é contínua se e só se $f(\overline{A}) \subset \overline{f(A)}$.

**Resolução:** 

1. $(\Rightarrow)$ Suponha $f : M \longrightarrow N$ contínua.
    - Lembre que 
    $$
        A \subset f^{-1}(f(A)) \quad \text{ e } \quad f(f^{-1}(B)) \subset B
    $$
    - Usando isso,
    $$
        A \subset f^{-1}(f(A)) \subset f^{-1}(\overline{f(A)})
    $$
    - Como $f$ é contínua, $f^{-1}(\overline{f(A)})$ é fechado.
    - Portanto,
    $$
        \overline{A} \subset f^{-1}(\overline{f(A)})
    $$
    - Logo,
    $$
        f(\overline{A}) \subset f(f^{-1}(\overline{f(A)})) \subset \overline{f(A)}
    $$
2. $(\Leftarrow)$ Suponha $f(\overline{A}) \subset \overline{f(A)}$.
    - Tome $C \in N$ fechado.
    - Temos que
    $$
        f(f^{-1}(C)) \subset C \implies f(\overline{f^{-1}(C)}) \subset \overline{f(f^{-1}(C))} \subset C
    $$
    - Assim,
    $$
        \overline{f^{-1}(C)} \subset f^{-1}(C)
    $$
    - O que implica que $f^{-1}(C)$ é fechado.

### Exercício 4.2e

**Questão:** Se $A \subset M$ e $\chi_A : M \longrightarrow \mathbb{R}$ é dada por
$$
\chi_A(x) = \begin{cases}
1, & x \in A \\
0, & x \notin A
\end{cases}
$$
Então $\chi_A$ é:
1. Semicontínua inferiormente se, e somente se, $A$ é aberto.
2. Semicontínua superiormente se, e somente se, $A$ é fechado.
3. contínua se, e somente se, $A$ é aberto e fechado.

**Resolução:** 

1.
    - Note que
    $$
        \chi_A^{-1}(a, +\infty) = \begin{cases}
            M, & a < 0 \\
            A, & 0 \le a < 1 \\
            \emptyset, & a \ge 1
        \end{cases}
    $$
    - $(\Rightarrow)$ Temos que $\chi_A^{-1}(a, +\infty)$ é aberto para todo $a \in \mathbb{R}$. Portanto, $A = \chi_A^{-1}(0, +\infty)$ é aberto.
    - $(\Leftarrow)$ Por contrapositiva: suponha que existe $a \in \mathbb{R}$ tal que $\chi_A^{-1}(a, +\infty)$ não é aberto. Neste caso, $A$ não é aberto.
2. 
    - Note que
    $$
        \chi_A^{-1}(-\infty, a) = \begin{cases}
            M, & a \le 0 \\
            A, & 0 < a \le 1 \\
            \emptyset, & a > 1
        \end{cases}
    $$
    - Basta ver que $\chi_A^{-1}(-\infty, a)$ é fechado sse. $\chi_A^{-1}(a, +\infty)$ é aberto e aplicar o item anterior.
3. Segue do exercício 4.1 e dos pontos anteriores.
    
### Exercício 4.3

**Questão:** Se $f : X \longrightarrow Y$ é uma função contínua tal que $f(x) = y_0$ para todo $x$ em um denso $D \subset X$ e $Y$ é Hausdorff, então $f(x) = y_0$ para todo $x \in X$.

**Resolução:** 

- Suponha que existe $y \in X$ tal que $f(y) \neq y_0$.
- Como $f$ é contínua, para todo $V \in \mathcal{B}_{f(y)}$, existe $U \in \mathcal{B}_y$ tal que $f(U) \subset V$.
- Como $D$ é denso em $X$, temos que $D \cap U \neq \emptyset$.
- Assim, dado $x \in D \cap U$, temos que $f(x) = y_0$, o que contradiz o fato que $f(U) \subset V$, para todo $V \in \mathcal{B}_{f(y)}$.

### Exercício 4.4

**Questão:** Seja $f : X \longrightarrow Y$ uma função contínua. Se $x$ é o ponto limite de um conjunto $A \subset X$, então $f(x)$ é ponto limite de $f(A)$? 

**Resolução:** 

- A afirmação é falsa. Considere 
$$
f : \mathbb{R} \longrightarrow \mathbb{R}, \quad f(x) = 2, ~\forall ~x \in \mathbb{R}
$$
- Se $A = [0,1]$, temos $A' = [0,1]$. 
- Note que $1$ é ponto de acumulação de $A$.
- Mas $f(1) = 2$ não é ponto de acumulação de $f[0,1] = \{ 2 \}$.
- De fato, se $V$ é uma vizinhança de $2$ em $f(A)$, então
$$
    \left( f(A) \cap V \right) \setminus \{ 2 \} = \emptyset
$$

### Exercício 4.5

**Questão:** Sejam $(X, \tau)$ e $(X, \tau')$ espaços topológicos distintos e $I : (X, \tau') \longrightarrow (X, \tau)$ a função identidade. Mostre que

1. $I$ é contínua sse. $\tau'$ é mais fina que $\tau$.

2. $I$ é homeomorfismo sse. $\tau' = \tau$.

**Resolução:** 

1. $I$ é contínua sse. $\tau'$ é mais fina que $\tau$.
    1. $(\Rightarrow)$ Suponha que $I$ é contínua.
        - Dado $V \in \tau$, temos que $I^{-1}(V) \in \tau'$ porque $I$ é contínua.
        - Como $I$ é a identidade, $I^{-1}(V) = V$, i.e., se $V \in \tau$, então $V \in \tau'$.
        - Ou seja, $\tau'$ é mais fina que $\tau.$

    2. $(\Leftarrow)$ Suponha que $\tau'$ é mais fina que $\tau$.
        - Por hipótese, se $V \in \tau$, então $V \in \tau'$.
        - Assim, $I^{-1}(V) = V$ (porque $I$ é identidade) e, portanto, $I$ é contínua.

2. $I$ é homeomorfismo sse. $\tau' = \tau$.
    1. $(\Rightarrow)$ Suponha que $I$ é homeomorfismo. 
        - Pelo item anterior, $\tau \subset \tau'$.
        - Por outro lado, $I^{-1}$ também é contínua e identidade. Portanto, $\tau' \subset \tau$.
    
    2. $(\Leftarrow)$ Suponha que $\tau' = \tau$.
        - Como $\tau \subset \tau'$, pelo item anterior temos que $I$ é contínua. 
        - Analogamente, $\tau' \subset \tau$ e $I^{-1}$ é contínua.
        - Como $I$ é bijetora por definição, temos que $I$ é homeomorfismo.

### Exercício 4.8

**Questão:** Assuma que $a < b$. Mostre que o conjunto $(a, b) \subset \mathbb{R}$ é homeomorfo a $A = (0,1)$, $B = (-\infty, 0)$, $C = (0, +\infty)$ e $\mathbb{R}$. Conclua que todos os intervalos abertos são homeomorfos entre si. Mostre também que $[a,b] \subset \mathbb{R}$ é homeomorfo a $[0,1]$.

**Resolução:**

1. $A = (0,1)$.
    - Considere $f : (0,1) \longrightarrow (a, b)$ dada por $f(x) = t_a \circ m_{(b-a)}(x)$, em que $t_a(x) = x + a$ (translação) e $m_{b-a}(x) = (b-a)x$ (homotetia), i.e.,
    $$
    f(x) = (b-a)x + a
    $$
    - Note que $f(0) = a$ e $f(1) = b$.
    - $f$ é contínua, porque é composição de contínuas.
    - E sua inversa é dada por 
    $$
    f^{-1}(x) = (t_a \circ m_{(b-a)})^{-1}(x) = m_{1/(b-a)} \circ t_{(-a)}(x) = \frac{x-a}{b-a}
    $$

2. $B = (-\infty, 0)$.
    - Considere $f : (-\infty, 0) \longrightarrow (0, 1)$ dada por $f(x) = e^x$, cuja inversa é $\ln(x)$.

3. $C = (0, +\infty)$
    - Tome $f(x) = e^{-x}$.

4. $\mathbb{R}$.
    - Tome $f : \mathbb{R} \longrightarrow (0, 1)$ dada por 
    $$
    f(x) = \frac{x}{\sqrt{1+x^2}}
    $$
    - Cuja inversa é dada por
    $$
    f^{-1}(x) = \frac{x}{\sqrt{1-x^2}}
    $$

5. Caso $[a,b]$ e $[0,1]$.
    - Basta tomar intervalos fechados no primeiro caso.

6. Todo intervalo aberto.
    - Observe que, para $(-\infty, a)$, tomamos $f(x) = e^{x-a}$.

### Exercício 4.9

**Questão:** Encontre uma função $f : \mathbb{R} \longrightarrow \mathbb{R}$ que seja contínua em um único ponto.

**Resolução:**

- Considere
$$
f(x) = \begin{cases}
    x, & x \in \mathbb{Q} \\
    0, & x \in \mathbb{R} \setminus \mathbb{Q}
\end{cases}
$$
- E note que $f(x)$ só é contínua em zero.

### Exercício 4.11

**Questão:** Sejam $f, g: X \longrightarrow \mathbb{R}$ funções contínuas. Mostre que as funções $(f \lor g), (f \land g) : X \longrightarrow \mathbb{R}$ definidas por 
$$
(f \lor g)(x) = \max \{ f(x),~g(x) \}
$$
$$
(f \land g)(x) = \min \{ f(x),~g(x) \}
$$
são funções contínuas.

**Resolução:**

Basta notar que 
$$
(f \lor g)(x) = \frac{f(x) + g(x) + |f(x) - g(x)|}{2}
$$
e 
$$
(f \land g)(x) = \frac{f(x) + g(x) - |f(x) - g(x)|}{2}
$$

### Exercício 4.12

**Questão:** Seja $A \subset X$ e $f : A \longrightarrow Y$ uma função contínua. Se $Y$ é Hausdorff e $f$ pode ser estendida a uma função contínua $g : \overline{A} \longrightarrow Y$, então $g$ está unívocamente determinada por $f$.

**Resolução:** 

- Suponha que existem $g, h : \overline{A} \longrightarrow Y$ extensões contínuas de $f$.
- E assuma que existe $x \in \overline{A}$ tal que $g(x) \neq h(x)$.
- Como $Y$ é Hausdorff, existem $U$ e $V$ abertos tais que $g(x) \subset U$ e $h(x) \subset V$ com $U \cap V = \emptyset$.
- Como $g$ e $h$ são contínuas, $g^{-1}(U)$ e $h^{-1}(V)$ são abertos.
- Considere o aberto $W = g^{-1}(U) \cap h^{-1}(V)$. 
- Como $x \in W$, temos que $W$ é não vazio e $W \cap \overline{A} \neq \emptyset$ (pois toda vizinhança aberta de $x$ intersecta $A$).
- Portanto, existe $x_0 \in W \cap \overline{A}$ e temos que $f(x_0) = g(x_0) = h(x_0)$, o que contradiz $U \cap V = \emptyset$.
- Logo, $g \equiv h$.

<!-- 
- Suponha que existe $a \in A$ tal que $f(a) \neq g(a)$. 
- Como $Y$ é Hausdorff, existem $U$ e $V$ abertos tais que $f(a) \subset U$ e $g(a) \subset V$ com $U \cap V = \emptyset$.
- Como $f$ e $g$ são contínuas, $f^{-1}(U)$ e $g^{-1}$ são abertos.
- Considere o aberto $W = f^{-1}(U) \cap g^{-1}(V)$. 
- Como $a \in W$, temos que $W$ é não vazio e $W \cap \overline{A} \neq \emptyset$.
- Portanto, existe $x_0 \in W \cap \overline{A}$ e temos que $f(x_0) = g(x_0)$, o que contradiz $U \cap V = \emptyset$.
- Logo, $f \equiv g$. -->

### Exercício 4.14 (Willard Thm. 13.13)

**Questão:** Sejam $(X, \tau)$ e $(Y, \tau')$ dois espaços topológicos, com $Y$ de Hausdorff. E sejam $f, g: X \longrightarrow Y$ contínuas. Mostre que 
$$
A = \{ x \in X : f(x) = g(x) \}
$$
é fechado.

**Resolução:** 

- Mostremos que $A^c$ é aberto.
- Seja $x \in A^c$. Como $Y$ é Hausdorff, existem $U, V$ abertos em $Y$ disjuntos tais que $f(x) \subset U$ e $g(x) \subset V$.
- Como $f$ e $g$ são contínuas, $f^{-1}(U)$ e $g^{-1}(V)$ são abertos.
- Note que $x$ pertence ao aberto $W = f^{-1}(U) \cap g^{-1}(V)$.
- Tomando $y \in W$, temos que
$$
f(y) \in f(U), ~g(y) \in g(U) \implies f(y) \neq g(y)
$$
- Como $W$ é uma vizinhança aberta de $x$ contida em $A^c$, temos que $A^c$ é aberto.

### Exercício 4.18a

**Questão:** Sejam $(X, \tau)$ e $(Y, \tau')$ dois espaços topológicos e $f : X \longrightarrow Y$. Mostre que se $Y$ é Hausdorff e $f$ é contínua, então o gráfico de $f$ é fechado em $X \times Y$. 

**Resolução:** 

- Defina o gráfico de $f$:
$$
G(f) = \{ (x, f(x)) : x \in X \}
$$
- Tome $(x, y) \in G(f)^c$, i.e., $y \neq f(x)$.
- Como $Y$ é Hausdorff, existem $U, V \subset Y$ abertos tais que $f(x) \subset U$, $y \subset V$ e $U \cap V = \emptyset$.
- Como $f$ é contínua, $f^{-1}(U)$ e $f^{-1}(V)$ são abertos. 
- Seja $W$ uma vizinhança aberta de $x$ tal que $f(W) \subset U$.
- Mostrar que $(W \times V) \cap G = \emptyset$.
    - Tome $(z, f(z)) \in G$.
    - Caso $z \notin W$, então $(z, f(z)) \notin W \times V$.
    - Caso $z \in W$, então $f(z) \in U$ e, portanto, $f(z) \notin V$. Assim, $(z, f(z)) \notin W \times V$.
    - Em ambos os casos, $(z, f(z)) \notin W \times V$. Ou seja, $(W \times V) \cap G = \emptyset$.
- Logo, todo ponto de $G^c$ tem uma vizinhança aberta disjunta de $G$, i.e., $G^c$ é aberto.

### Exercício 4.18b

**Questão:** Sejam $(X, \tau)$ e $(Y, \tau')$ dois espaços topológicos e $f : X \longrightarrow Y$. Mostre que se $Y$ é compacto e o gráfico de $f$ é fechado em $X \times Y$, então $f$ é contínua.

**Resolução:** 

- Defina o gráfico de $f$:
$$
G(f) = \{ (x, f(x)) : x \in X \}
$$
- Seja $F$ um fechado de $Y$ e $\pi : X \times Y \longrightarrow X$ projeção na primeira coordenada. Como $Y$ é compacto, $\pi$ é fechada e contínua (Lema 1).
- Assim,
$$
\pi[G(f) \cap (X \times F)] = f^{-1}(F)
$$
- Como $G(f) \cap (X \times F)$ é fechado, temos que $f^{-1}(F)$ é fechado.
- Logo, $f$ é contínua.

### Exercício 4.20 (Willard Thm. 18.5)

**Questão:** Mostre que a imagem contínua e aberta de um espaço localmente compacto é localmente compacto.

**Resolução:** 

- Seja $f : X \longrightarrow Y$ contínua e aberta com $X$ localmente compacto.
- Considere $y \in f(X)$ e $V$ uma vizinhança de $y$. 
- Escolha $x \in f^{-1}(y)$.
- Como $f$ é contínua e $X$ localmente compacto, existe uma vizinhança compacta $K$ de $x$ tal que $f(K) \subset V$.
- Como $x \in K^\circ$, temos que $y \in f(K^\circ) \subset f(K)$.
- Como $f$ é aberta, $f(K^\circ)$ é aberta. 
- Logo, $f(K)$ é uma vizinhança compacta de $y$ contida em $V$.

<!-- - Seja $f : X \longrightarrow Y$ contínua e aberta com $X$ localmente compacto.
- Como $X$ é localmente compacto, existe $U \subset X$ aberto tal que $\overline{U}$ é compacto.
- Como $f$ é aberta, $f(U)$ é aberto.
- Seja $V = f(U)$. 
- Como $f$ é contínua, $f(\overline{U})$ é compacto. 
- Assim, $V = f(U) \subset f(\overline{U})$, ou seja, $V$ está contido num compacto.
- Logo, $Y$ é localmente compacto. -->

### Exercício 4.21

**Questão:** Sejam $(X, \tau)$ um espaço localmente compacto e $(Y, \tau')$ um espaço de Hausdorff. E seja $f : X \longrightarrow Y$ sobrejetora, contínua e aberta. Mostre que se $L \subset Y$ é compacto, existe $K \subset X$ compacto tal que $f(K) = L$.

**Resolução:** 

- Como $L$ é compacto num Hausdorff, $L$ é fechado.
- Pela continuidade de $f$, temos que $f^{-1}(L)$ é fechado. 
- Com isso, $f^{-1}(L) \cap M$ é compacto, para qualquer $M \subset X$ compacto. 
- Como $X$ é localmente compacto, para cada $x \in X$ existe um aberto $U_x$ e um compacto $C_x$ tal que $x \in U_x \subset C_x$.
- Cubra $f^{-1}(L)$ com as vizinhanças $C_x$.
- Dessa forma, $\{ f(C_x^\circ) : x \in f^{-1}(L) \}$ é uma cobertura aberta de $L$.
- Construir um compacto $M \subset X$ tal que $L \subset f(M)$.
- Tomar $K = f^{-1}(L) \cap M$.


### Exercício 4.22b (Willard Thm. 16.2)

**Questão:** Mostre que a imagem contínua e aberta de um espaço topológico que satisfaz o segundo axioma de enumerabilidade também satisfaz o mesmo axioma.

**Resolução:** 

- Seja $f : X \longrightarrow Y$ contínua e aberta e suponha que $X$ satisfaz o segundo axioma de enumerabilidade. 
- Verificar que, se $\mathcal{B}$ é base de $X$, então $f(\mathcal{B}) = \{ f(B) : B \in \mathcal{B} \}$ é base de $Y$.
- Seja $V$ aberto de $Y$ e $p \in V$.
- Então $f^{-1}(V)$ é aberto em $X$.
- Escolha $q \in f^{-1}(p) \subset f^{-1}(V)$.
- Então, para algum aberto básico $B$, temos $q \in B \subset f^{-1}(V)$.
- Portanto, $p \in f(B) \subset V$ e, como $f$ é aberta, os conjuntos $f(B)$ formam uma base para $Y$.

### Exercício 4.22c (Willard Thm. 16.6)

**Questão:** Mostre que a imagem contínua de um espaço Lindelof é Lindelof.

**Resolução:** 

- Suponha que $f : X \longrightarrow Y$ é contínua e sobrejetora e $X$ é Lindelof.
- Tome $\{ U_i \}_{i \in I}$ uma cobertura aberta de $Y$.
- Então $\{ f^{-1}(U_i) \}_{i \in I}$ é uma cobertura aberta de $X$, donde extraímos uma subcobertura enumerável $\{ f^{-1}(U_n) \}_{n \in \mathbb{N}}$.
- Assim, $\{ U_n \}_{n \in \mathbb{N}}$ é uma subcobertura enumerável de $\{ U_i \}_{i \in I}$.

### Exercício 4.22d

**Questão:** Mostre que a imagem contínua de um espaço separável é separável.

**Resolução:** 

- Note que um mapa contínuo $f$ de $X$ em $Y$ leva um subconjunto denso de $X$ em um subconjunto denso de $Y$.
- Seja $D$ denso enumerável em $X$.
- Como $f$ é contínua,
$$
f(D) \subset f(X) = f(\overline{D}) \subset \overline{f(D)}
$$
- Seja $y \in f(\overline{D})$. Então $y = f(x)$ para algum $x \in \overline{D}$.
- Seja $V \subset Y$ um aberto contendo $y$.
- Pela continuidade de $f$, temos que $f^{-1}(V) \subset X$ é aberto e $x \in f^{-1}(V)$.
- Como $D$ é denso, $f^{-1}(V) \cap D \neq \emptyset$. 
- Logo, $V \cap f(D) \neq \emptyset$.

### Exercício 4.24

**Questão:** Mostre que a imagem contínua de conexo é conexa.

**Resolução:** 

1. Suponha que a imagem seja desconexa. 
    - Sejam $f : X \longrightarrow Y$ contínua, $X$ conexo e $W = f(X)$.
    - Isto é, existem $U, V$ abertos não vazios tais que $W = U \cup V$ e $U \cap V = \emptyset$.

2. Deduza que o domínio é desconexo.
    - Assim, podemos escrever $X = f^{-1}(U) \cup f^{-1}(V)$.
    - Note que $f^{-1}(U)$ e  $f^{-1(V)}$ são não vazios e disjuntos.

### Exercício 4.27

**Questão:** Seja $f : X \longrightarrow Y$ contínua. Mostre que a imagem de cada componente conexa de $X$ está contida numa componente conexa de $Y$.

**Resolução:** 

- Seja $C_x$ a componente conexa de $x \in X$.
- Como $f$ é contínua, $f(C_x)$ é conexo.
- Denote por $y = f(x) \in f(C_x)$.
- Como $f(C_x)$ é conexo e $y \in f(C_x)$, temos que $f(C_x) \subset C_y$, pois $C_y$ é a maior componente conexa contendo $y$.

### Exercício 4.28

**Questão:** Suponha que $X$ e $Y$ são homeomorfos. Mostre que cada componente conexa de $X$ é homeomorfa a uma componente conexa de $Y$.

**Resolução:** 

- Sejam $C_x$ a componente conexa de $x \in X$ e $f : X \longrightarrow Y$ homeomorfismo.
- Como $f$ é contínua, pelo exercício anterior, $f(C_x)$ é conexo e $f(C_x) \subset C_y$, em que $y = f(x)$.
- Como $f^{-1}$ é contínua, $f^{-1}(C_y)$ é conexo e $f^{-1}(C_y) \subset C_x$.
- Assim, como $f$ é bijetora,
$$
f^{-1}(f(C_x)) = C_x \subset f^{-1}(C_y) \subset C_x \implies C_x = f^{-1}(C_y)
$$
- Analogamente,
$$
f(f^{-1}(C_y)) = C_y \subset f(C_x) \subset C_y \implies C_y = f(C_x)
$$
- Logo, $C_x$ e $C_y$ são homeomorfos.

### Exercício 4.30

**Questão:** Seja $M$ um espaço de Hausdorff e assuma que existe uma compactificação $(N, \varphi)$ de $M$ tal que $N \setminus \varphi(M)$ contém um único ponto. Mostre que $M$ é localmente compacto, mas não é compacto.

**Resolução:** 

1. Definição de compactificação.
    - Como $(N, \varphi)$ é compactificação, $N$ é Hausdorff e compacto e $\varphi : M \longrightarrow N$ é homeomorfo a um subconjunto denso de $N$.

2. Usar que $N$ é Hausdorff e compacto para concluir que $M$ é localmente compacto.
    - Seja $x \in M \subset N$.
    - Como $N$ é Hausdorff, existem $U, V$ abertos tais que $x \in U$, $p \in V$ e $U \cap V = \emptyset$, em que $\{ p \} = N \setminus \varphi(M)$.
    - Assim, $V^c$ é fechado em $N$ e, portanto, compacto. 
    - Como $U \subset V^c$, temos que $V^c$ é vizinhança compacta de $x$ em $M$. 
    - Logo, $M$ é localmente compacto.

3. Mostrar que $M$ não é compacto.
    - Suponha que $M$ seja compacto.
    - Então $\varphi(M)$ é compacto.
    - Como $N$ é Hausdorff, temos que $\varphi(M)$ é fechado.
    - Mas, por hipótese,
    $$
    \varphi(M) = \overline{\varphi(M)} = N \implies N \setminus \varphi(M) = \emptyset
    $$
    - Logo, $M$ não pode ser compacto.

### Exercício 4.32

**Questão:** Considere a esfera $S^n$ de $\mathbb{R}^{n+1}$. Se $N = (0, \ldots, 0, 1)$, mostre que a projeção estereográfica
$$
\begin{aligned}
\varphi : S^n \setminus \{ N \} &\longrightarrow \mathbb{R}^n \\
(x_1, \ldots, x_{n+1}) &\longmapsto \frac{1}{1-x_{n+1}} (x_1, \ldots, x_{n})
\end{aligned}
$$
define um homeomorfismo.

Com isso, mostre que a compactificação de Alexandroff de $\mathbb{R}^n$ é homeomorfa a $S^n$.

**Resolução:** 

1. Encontrar inversa.
    - Considere $\psi : \mathbb{R}^n \longrightarrow S^n \setminus \{ N \}$ dada por
    $$
    \psi(x_1, \ldots, x_n) = \frac{2}{1 + \| x \|^2}(x_1, \ldots, x_n, \| x \|^2 - 1)
    $$
    - Note que $\psi$ é contínua.
    - Além disso, $\varphi \circ \psi = \text{id}_{\mathbb{R}^n}$ e $\psi \circ \varphi = \text{id}_{S^n \setminus \{ N \}}$.
    - Logo, $\varphi$ define um homeomorfismo.

2. A compactificação de Alexandroff de $\mathbb{R}^n$ é homeomorfa a $S^n$.
    - Note que $S^n$ é Hausdorff e compacto, $\psi$ mergulha em um subconjunto denso de $S^n$ e $0 \notin \mathbb{R}^n$.
    - Logo, como $(S^n, \psi)$ é uma compatificação de Alexandroff de $\mathbb{R}^n$, segue que ela é homeomorfa a $S^n$.

### Exercício 4.34

**Questão:** Seja $M$ um espaço de Tychonoff e $(N, \varphi)$ a compactificação de $M$. 

1. Mostre que se $\varphi(M)$ é aberto em $N$, então $M$ é localmente compacto. 

2. Se $U$ é vizinhança compacta de $x \in M$, então $\varphi(U)$ é uma vizinhança de $\varphi(x) \in N$.

3. $\varphi(M)$ é aberto em $N$ se, e somente se, $M$ é localmente compacto.

**Resolução:** 

0. Fato.
    - Um subconjunto denso de um espaço Hausdorff compacto é localmente compacto sse. ele é aberto.

1. Se $\varphi(M)$ é aberto em $N$, então $M$ é localmente compacto. 
    - Como $N$ é Hausdorff e compacto, $N$ é localmente compacto. 
    - Dado que $\varphi(M)$ é aberto e denso em $N$, temos que $\varphi(M)$ é localmente compacto. 
    - Portanto, como $M$ é homeomorfo a $\varphi(M)$, temos que $M$ é localmente compacto.
    <!-- - Assim, como $N$ é Hausdorff e localmente compacto, qualquer subconjunto aberto de $N$ é localmente compacto.
    - Lembre que um subconjunto denso de um espaço Hausdorff compacto é localmente compacto sse. ele é aberto. -->
    <!-- - Sejam $x \in M$ e $U$ uma vizinhança aberta de $x$.
    - Como $\varphi$ é aberto, então $\varphi(U)$ é aberto.
    - Mas $N$ é Hausdorff e localmente compacto. Assim, existe $\overline{V} \in N$ compacto tal que $\overline{V} \subset U$. -->

2. $\varphi(U)$ é uma vizinhança de $\varphi(x) \in N$.
    - Como $U$ é compacto e $\varphi$ é contínua, temos que $\varphi(U)$ é compacto.
    - Como $x \in U$, temos que $\varphi(x) \in \varphi(U)$.
    - Logo, $\varphi(U)$ é vizinhança compacta de $\varphi(x)$.

3. Se $M$ é localmente compacto, então $\varphi(M)$ é aberto em $N$.
    - Seja $y \in \varphi(M)$.
    - Como $\varphi$ é mergulho, existe um único $x \in M$ tal que $y = \varphi(x)$.
    - Como $M$ é localmente compacto, existe $V$ vizinhança compacta de $x$.
    - Como $\varphi$ é contínua, então $\varphi(V)$ é vizinhança compacta de $y$.
    - Com isso, temos que $\varphi(M)$ é um subconjunto localmente compacto e denso de um espaço Hausdorff compacto.
    - Logo, $\varphi(M)$ é aberto.

### Lema 1

**Questão:** Seja $\pi : X \times Y \longrightarrow X$ a projeção na primeira coordenada, com $Y$ compacto. Então $\pi$ é fechado.

**Resolução:** 

- Sejam $C \in X \times Y$ fechado e $x_0 \notin \pi(C)$.
- Para qualquer $y \in Y$, temos $(x_0, y) \notin C$.
- Tomemos $U_y \times V_y$ aberto de $X \times Y$ contendo $(x_0, y)$ tal que $(U_y \times V_y) \cap C = \emptyset$.
- Como $Y$ é compacto e $(V_y)$ cobre $Y$, existem finitos $y_1, \ldots, y_n$ tais que $Y = V_{y_1} \cup \cdots \cup V_{y_n}$.
- Defina
$$
U = \bigcap_{i=1}^n U_{y_i}
$$
- E note que 
$$
(U \times Y) \cap C = (U_{y_1} \cap \cdots \cap U_{y_n}) \times (V_{y_1} \cup \cdots \cup V_{y_n}) \cap C = \emptyset
$$
- Logo, 
$$
x_0 \in U \subset X \setminus \pi(C) \implies X \setminus \pi(C) \text{ é aberto}
$$
- E $\pi(C)$ é fechado.

## Homotopia

### Exercício 5.2

**Questão:** Mostrar que a imagem contínua de um conjunto conexo por caminhos é conexo por caminhos.

**Resolução:** 

- Seja $f : X \longrightarrow Y$ contínua e $X$ conexo por caminhos.
- Assim, para todo $x_1, x_2 \in X$, existe $\gamma : [0,1] \longrightarrow X$ caminho de $x_1$ para $x_2$.
- Portanto, $$\gamma' = f \circ \gamma : [0,1] \longrightarrow f(X) \subset Y$$ é um caminho de $y_1 = f(x_1)$ a $y_2 = f(x_2)$. Note que $\gamma'$ é contínua e $\gamma'(0) = f(\gamma(0)) = f(x_1)$ e $\gamma'(1) = f(\gamma(1)) = f(x_2)$.

### Exercício 5.4

**Questão:** Mostrar que $S^n$ é conexo por caminhos para todo $n \in \mathbb{N}$.

**Resolução:** 

- Considere $f : \mathbb{R}^{n+1} \setminus \{ 0 \} \longrightarrow S^n$ dada por $$f(x) = \frac{x}{\| x \|}$$
- Como $f$ é contínua e $\mathbb{R}^{n+1} \setminus \{ 0 \}$ é conexo por caminhos, temos que $S^n$ é conexo por caminhos (e, portanto, conexo).

### Exercício 5.7

**Questão:** Mostrar que todo subconjunto conexo e aberto de $\mathbb{R}^n$ é conexo por caminhos.

**Resolução:** 

- Note que se as componentes conexas por caminhos são abertas, então o espaço é localmente conexo por caminhos.
- Seja $S \subset \mathbb{R}^n$ conexo e aberto. Como $S$ é conexo e localmente conexo por caminhos, segue que $S$ é conexo por caminhos.

### Exercício 5.8 (Seno do Topólogo)

**Questão:** Prove que o conjunto
$$
S = \{ (x, \sin(1/x)) : 0 < x \leq 1 \} \cup \{ (0,y) : -1 \leq y \leq 1 \}
$$
conexo e não é conexo por caminhos.

**Resolução:** 

1. Mostrar que $S$ é conexo.
    - Defina $S_1 = \{ (x, \sin(1/x)) : 0 < x \leq 1 \}$ e $S_2 = \{ (0,y) : -1 \leq y \leq 1 \}$. Note que $S_1$ e $S_2$ são conexos, porque são a imagem de uma função contínua definida num intervalo conexo.
    - Como $\overline{S_1} = S_2$, temos que $\overline{S_1} \cap S_2 \neq \emptyset$. Portanto, $S = S_1 \cup S_2$ é conexo.

2. Mostrar que $S$ não é conexo por caminhos.
    - Suponha que exista um caminho $f(t) = (f_1(t), f_2(t))$ com ponto inicial $(0, 0) \in S_2$ e ponto final em $S_1$ tal que $f_1(0) = 0$, $f_1(t) > 0$ e $f_2(t) = \sin(1/f_1(t))$ para $t > 0$.
    - Vamos mostrar que existe uma sequência $t_n \to 0$ tal que $f_2(t_n) = (-1)^n$, contradizendo a hipótese de que $f$ é contínua.
    - Dado $n \in \mathbb{N}$, escolhemos $0 < y_0 < f_1(1/n)$ tal que $\sin(1/y_0) = (-1)^n$. Pelo Teorema do Valor Intermediário, sabemos que existe $0 < x_0 < 1/n$ tal que $f_1(x_0) = y_0$. Escolha $t_n = x_0$.
    - Dessa forma, temos que $f_2(t_n) = (-1)^n$, que é descontínua. Logo, $f$ não é contínua e temos que $S$ não é conexo por caminhos.

### Exercício 5.12

**Questão:** Mostrar que se $M$ e $N$ são contráteis, então $M \times N$ é contrátil.

**Resolução:** 

1. Definição de contrátil.
    - Lembre que $X$ é contrátil se existe mapa constante $c$ tal que $H : \text{id}_X \simeq c$, i.e., a identidade é homotopicamente nula.

2. Usar que $M$ e $N$ são contráteis.
    - Como $M$ é contrátil, existe $c_M$ tal que existe homotopia $H_M : \text{id}_M \simeq c_M$. Analogamente, existe $H_N : \text{id}_N \simeq c_N$.

3. Definir projeções e homotopia.
    - Defina
    $$
    \pi_M : (M \times N) \times I \longrightarrow M, \quad \pi_M((x,y), t) = (x,t)
    $$
    - E, semelhantemente,
    $$
    \pi_N : (M \times N) \times I \longrightarrow N, \quad \pi_N((x,y), t) = (y,t)
    $$
    - Tomemos $H : (M \times N) \times I \longrightarrow M \times N$ como $H = (H_M \circ \pi_M, H_N \circ \pi_N )$. Assim,
    $$
    H((x,y), 0) = (H_M(x, 0), H_N(y, 0)) = (x,y) = \text{id}_{M \times N} \\
    H((x,y), 1) = (H_M(x, 1), H_N(y, 1)) = (c_M,c_N) = c
    $$
    - Note que $H_M, H_N, \pi_M, \pi_N$ são contínuas. Portanto, $H_M \circ \pi_M$ e $H_N \circ \pi_N$ são contínuas e, assim, $H$ é contínua.

### Exercício 5.14

**Questão:** Mostrar que o espaço de Sierpinski é contrátil.

**Resolução:** 

- Seja $H : M \times [0,1] \longrightarrow M$ dada por
$$
H(z,0) = z, \quad \forall ~z \in M \quad \text{ e } \quad  H(z, t) = x, \quad \forall ~z \in M, ~t \in (0,1]
$$
- Note que $H(z,0) = \text{id}_M$ e $H(z,1) = x$ é constante e $H$ é contínua porque $H^{-1}(\{ x \}) = \{ (x, 0) \} \cup (M \times (0, 1])$ é aberto. Logo, o espaço de Sierpinski é contrátil.

### Exercício 5.15

**Questão:** Mostrar que todo espaço contrátil é conexo por caminhos.

**Resolução:** 

1. Aplicar definição.
    - Seja $X$ contrátil. Então existe homotopia $H : X \times [0,1] \longrightarrow X$ tal que $H : \text{id}_X \simeq c$, em que $c$ é mapa constante em $X$.

2. Criar caminhos de $x_1$ a $c$ e de $x_2$ a $c$.
    - Definimos um caminho de $x_1$ a $c$ tomando $\varphi(t) = H(x_1, t)$. Note que $\varphi(0) = H(x_1, 0) = x_1$ e $\varphi(1) = H(x_1, 1) = c$.
    - E um caminho de $x_2$ a $c$ tomando $\psi(t) = H(x_2, t)$.

3. Inverter $\psi$ e tomar concatenação para obter caminho de $x_1$ a $x_2$.
    - Defina $\gamma = \varphi \ast \psi^{-1}$ por
    $$
    \gamma = 
    \begin{cases}
    \varphi(2t), & t \in [0, 1/2] \\
    \psi^{-1}(2t-1), & t \in [1/2, 1]
    \end{cases}
    $$
    - Logo, $X$ é conexo por caminhos.

### Exercício 5.16

**Questão:** Mostre que, se $X$ é contrátil e $Y$ é conexo por caminhos, então quaisquer dois mapas contínuos $f, g : X \longrightarrow Y$ são homotópicos.

**Resolução:** 

1. Aplicar definição.
    - Seja $X$ contrátil. Então existe homotopia $H(x, 0) = x$ e $H(x, 1) = c$ para todo $x \in X$.

2. Todo mapa $X \longrightarrow Y$ é homotópico a algum mapa constante.
    - Basta notar que $f \circ H : X \times I \longrightarrow Y$ é homotopia entre $f$ e $f(c)$.

3. Quaisquer dois mapas constantes são homotópicos.
    - Sejam $f_1 \equiv y_1$ e $f_2 \equiv y_2$ mapas constantes de $X$ para $Y$.
    - E seja $\gamma : [0,1] \longrightarrow Y$ caminho de $y_1$ a $y_2$. Então $F(x, t) = \gamma(t)$ é homotopia entre $f_1$ e $f_2$.

4. Usar que homotopia é relação de equivalência.
    - Portanto, todo mapa $X \longrightarrow Y$ é homotópico a algum mapa constante e quaisquer dois mapas constantes são homotópicos.
    - Como homotopia é relação de equivalência, quaisquer dois mapas $X \longrightarrow Y$ contínuos são homotópicos.

### Exercício 5.18

**Questão:** Mostrar que $S^n$ é um retrato de deformação de $\mathbb{R}^{n+1}\setminus \{0 \}$.

**Resolução:** 

1. Aplicar Definição.
    - Queremos mostrar que existe $r : \mathbb{R}^{n+1} \setminus \{0 \} \longrightarrow S^n$ contínuo tal que $r \circ i = \text{id}_{S^n}$ e $H : i \circ r \simeq \text{id}_{\mathbb{R}^{n+1} \setminus \{0 \}}$, em que $i : S^n \hookrightarrow \mathbb{R}^{n+1} \setminus \{0 \}$ é inclusão.

2. Construir retração.
    - Considere $r(x) = \frac{x}{\| x \|}$. Note que, se $x \in S^n$, então $r(i(x)) = x$. Portanto, $r \circ i = \text{id}_{S^n}$.

3. Construir homotopia.
    - Defina 
    $$
    \begin{aligned}
    H : \mathbb{R}^{n+1} \setminus \{0 \} \times I &\longrightarrow \mathbb{R}^{n+1} \setminus \{0 \} \\
    (x, t) &\longmapsto tx + (1-t)\frac{x}{\| x \|}
    \end{aligned}
    $$
    - Note que $H$ é contínuo e satisfaz 
    $$
    H(x, 0) = \frac{x}{\| x \|} = i \circ r(x), \quad H(x, 1) = tx = \text{id}_{\mathbb{R}^{n+1} \setminus \{0 \}}
    $$
    - Logo, $S^n$ é um retrato de deformação de $\mathbb{R}^{n+1} \setminus \{0 \}$.

### Exercício 5.19

**Questão:** Mostrar que o retrato de um espaço contrátil é contrátil.

**Resolução:** 

1. Aplicar definições.
    - Seja $A$ um retrato de $X$, i.e., existe $r : X \longrightarrow A$ contínuo tal que $r \circ i = \text{id}_A$, em $i : A \hookrightarrow X$ é inclusão.
    - E suponha $X$ contrátil. Ou seja, existe homotopia $H : \text{id}_X \simeq c$.

2. Construir homotopia.
    - Considere $r \circ H|_{A \times I} : A \times I \longrightarrow A$. Note que é contínuo porque é composição de contínuos.
    - Além disso, $r \circ H|_{A \times I}(x,0) = r(x) = x$ porque $x \in A$. E também $r \circ H|_{A \times I}(x, 1) = r(c)$.
    - Logo, $\text{id}_A$ é homotópico ao mapa constante $r(c)$.

### Exercício 5.21

**Questão:** Mostre que os espaços 
$$
M = \{ 0 \} \cup \{ 1/n : n \in \mathbb{N} \}
$$
com a topologia induzida de $\mathbb{R}$ e $\mathbb{N}$ com a topologia discreta não têm a mesma homotopia.

**Resolução:** 

1. Supor que são homotopicamente equivalentes.
    - Seja $X = (M, \tau_{\mathbb{R}})$ e $Y = (M, \tau_{\mathbb{N}})$ o espaço com a topologia induzida de $\mathbb{R}$ e $\mathbb{N}$ com a topologia discreta respectivamente.
    - Suponhamos, por contradição, que $X$ e $Y$ são homotopicamente equivalentes, i.e., existem $$f : X \longrightarrow Y \quad \text{ e } \quad g : Y \longrightarrow X$$ contínuas tais que $H : f \circ g \simeq \text{id}_Y$ e $F : g \circ f \simeq \text{id}_X$.

2. Usar compacidade de $X$ para mostrar que $f(X)$ é finito.
    - Como $X$ é compacto (qualquer aberto em torno do zero contém $M$ com exceção de finitos pontos) e $f$ é contínua, temos que $f(X)$ é compacto.
    - Mas, como $Y$ é discreto e todo subespaço compacto de discreto é finito, temos que $f(X)$ é finito.

3. Mostrar que $Y$ é finito.
    - Observe que $H(y, 0) = f(g(y))$ e $H(y, 1) = y$.
    - Como $Y$ é discreto, $H$ deve ser constante em subespaços conexos. Assim, como $\{ y \} \times I$ é conexo, temos que $f(g(y)) = y$ para todo $y \in Y$.
    - Mas $f(X)$ é finito e $\text{Im}(\text{id}_Y) = Y$. Portanto, $Y$ é finito.

4. Derivar contradição usando número de componentes conexas por caminhos.
    - Note que $X$ tem um número infinito de componentes conexas por caminhos, porque todo conjunto unitário é uma componente conexa por caminhos. 
    - Por outro lado, um espaço discreto finito possui um número finito de componentes conexas por caminhos.
    - Mas equivalência homotópica preserva o número de componentes conexas por caminhos, o que contradiz nossa hipótese.