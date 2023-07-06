---
title: MA453 Topologia Geral - Exercícios
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

## Espaços Topológicos

### Exercício 2.6a

**Questão:** Seja $(\mathcal{M}, \tau)$ um espaço topológico e $A, B \subset M$. Mostre que $A^\circ \cup B^\circ \subset (A \cup B)^\circ$. Dê um exemplo para o qual $A^\circ \cup B^\circ \neq (A \cup B)^\circ$.

**Resolução:** 

- Note que $A^\circ \cup B^\circ \subset A \cup B$. 
- Como $A^\circ \cup B^\circ$ é aberto, segue que $A^\circ \cup B^\circ \subset (A \cup B)^\circ$.
- Contraexemplo. Tome $A = [0,1]$ e $B=[1,2]$ em $\mathbb{R}$ com a topologia canônica:
$$
A^\circ \cup B^\circ = (0,1) \cup (1,2) \quad \text{mas} \quad (A \cup B)^\circ = ([0,2])^c = (0,2)
$$

### Exercício 2.6b

**Questão:** Seja $(\mathcal{M}, \tau)$ um espaço topológico e $A, B \subset M$. Mostre que $\overline{A \cap B} \subset \overline{A} \cap \overline{B}$. Dê um exemplo para o qual $\overline{A \cap B} \neq \overline{A} \cap \overline{B}$.

**Resolução:** 

- Observe que $A \cap B \subset \overline{A} \cap \overline{B}$.
- Como $\overline{A} \cap \overline{B}$ é fechado, segue que $\overline{A \cap B} \subset \overline{A} \cap \overline{B}$.
- Contraexemplo. Tome $A = \mathbb{Q}$ e $B = \mathbb{R} \setminus \mathbb{Q}$:
$$
\overline{\mathbb{Q} \cap \mathbb{R} \setminus \mathbb{Q}} = \emptyset \quad \text{mas} \quad \overline{\mathbb{Q}} \cap \overline{\mathbb{R} \setminus \mathbb{Q}} = \mathbb{R}
$$

### Exercício 2.9

**Questão:** Seja $(\mathcal{M}, \tau)$ um espaço topológico e $A \subset \mathcal{M}$. Mostre que $\partial A = \emptyset$ se, e somente se, $A$ é aberto e fechado. 

**Resolução:** 

- $(\Rightarrow)$ Lembre que $\partial A = \overline{A} \cap \overline{A^c}$.

- Para mostrar que $A$ é fechado, suponha que $A \neq \overline{A}$.

- Isto é, existe $x \notin A$ tal que $x \in \overline{A}$. 

- Como $x \notin A$, temos que $x \in A^c \subset \overline{A^c}$. 

- Ou seja, $x \in \overline{A} \cap \overline{A^c}$, o que contradiz o fato de que $\partial A = \emptyset$. 

- Portanto, $A$ é fechado.

- Pelo mesmo argumento, $A^c = \overline{A^c}$. Assim, $A^c$ é fechado e, portanto, $A$ é aberto. 

- $(\Leftarrow)$ Suponha $A$ aberto e fechado, i.e., $A = \overline{A}$ e $A^c = \overline{A^c}$. 

- Logo, $$ \emptyset = A \cap A^c = \overline{A} \cap \overline{A^c} = \partial A $$

### Exercício 2.10

**Questão:** Dê um exemplo de um conjunto $A \subset \mathbb{R}$ tal que os conjuntos
$$ A, A^\circ, \overline{A}, (\overline{A})^\circ, \overline{A^\circ}, \overline{(\overline{A})^\circ}, (\overline{A^\circ})^\circ $$

**Resolução:** Tome dois abertos, um fechado intersectado com os racionais e um ponto. 
$$ A = (0, 1) \cup (1, 2) \cup ([2, 3] \cap \mathbb{Q}) \cup \{ 4 \} $$

- $A^\circ = (0,1) \cup (1,2)$;

- $\overline{A} = [0,3] \cup \{ 4 \}$;

- $(\overline{A})^\circ = (0,3)$;

- $\overline{A^\circ} = [0,2]$;

- $\overline{(\overline{A})^\circ} = [0,3]$;

- $(\overline{A^\circ})^\circ = (0,2)$.

### Exercício 2.15

**Questão:** Prove que os intervalos $[a, b)$ para $a, b \in \mathbb{R}$ formam uma base para uma topologia $\tau_2$ de $\mathbb{R}$ que é mais fina que a topologia usual.

**Resolução:** 

- Defina $\mathcal{B} = \{ [a, b) : a < b, a, b \in \mathbb{R} \}$.

- Note que $$ \mathbb{R} = \bigcup_{a, b \in \mathbb{R}} [a, b) $$

- Seja $x \in \mathbb{R}$, $U = [a, b)$ e $V = [c, d)$ tais que $x \in U \cap V$. 

- Tome $$ W = [ \max \{ a, c \}, \min \{ b, d\} ) $$

- Então $x \in W \subset U \cap V$ e temos que $\mathcal{B}$ é base.

- Note que todo $(a, b)$ pode ser escrito como $$ (a,b) = \bigcup_{n \in \mathbb{N}} \left[a + \frac{\varepsilon}{n}, b \right), \quad \varepsilon < \frac{b-a}{2} $$

- Porém, $[a, b)$ não pode ser escrito como união de $(a, b)$.

- Assim, como $(a,b) \subset [a, b)$, mas $[a, b) \not\subset (a,b)$, segue que $\tau_2$ é mais fina que a topologia usual.

### Exercício 2.17a

**Questão:** Seja $(S, \mathcal{S})$ um subespaço de $(\mathcal{M}, \tau)$. Mostre que se $\mathcal{B}_x$ é uma base de vizinhanças para $x \in \mathcal{M}$, então $$ \mathcal{B}_x^s = \{ S \cap U : U \subset \mathcal{B}_x \} $$ é uma base de vizinhanças de $x \in S$.

Além disso, mostre que se $\mathcal{M}$ satisfaz o primeiro axioma de enumerabilidade, então $S$ também o satisfaz. 

**Resolução:** 

- Seja $U^s \in \mathcal{U}_x^s$. Precisamos mostrar que existe $V^s \in \mathcal{B}_x^s$ tal que $V^s \subset U^s$. 

- Como $\mathcal{B}_x$ é base de vizinhanças para $x \in \mathcal{M}$, para todo $U \in \mathcal{U}_x$ existe $V \in \mathcal{B}_x$ tal que $V \subset U$. 

- Assim, basta tomar $V^s = S \cap V$. Note que $V^s \in \mathcal{B}_x^s$ e $V^s \subset V \subset U^s$.

- Observe que se $\mathcal{B}_x$ é enumerável, então $\mathcal{B}_x^s$ também é enumerável. Isto é, se $\mathcal{M}$ satisfaz o primeiro axioma de enumerabilidade, então $S$ também satisfaz. 

### Exercício 2.17b

**Questão:** Seja $(S, \mathcal{S})$ um subespaço de $(\mathcal{M}, \tau)$. Mostre que se $\mathcal{B}$ é uma base para a topologia de $\mathcal{M}$, então $$ \mathcal{B}_s = \{ S \cap U : U \subset \mathcal{B} \} $$ é uma base para a topologia de $S$.

Além disso, mostre que se $\mathcal{M}$ satisfaz o segundo axioma de enumerabilidade, então $S$ também o satisfaz. 

**Resolução:** 

- Tome $U_s \in \mathcal{S}$. Como $U_s$ é aberto em $S$, temos
$$ U_s = S \cap U, \quad U \in \tau $$

- Agora como $\mathcal{B}$ é base, existe $\mathcal{C} \subset \mathcal{B}$ tal que 
$$ U = \bigcup_{V \in \mathcal{C}} V $$

- Portanto, 
$$ U_s = S \cap U = S \cap \bigcup_{V \in \mathcal{C}} V = \bigcup_{V \in \mathcal{C}} (S \cap V) $$

- Isto é, existe $\mathcal{C}_s \subset \mathcal{B}_s$ tal que $$ U_s = \bigcup_{V_s \in \mathcal{C}_s} V_s $$ Ou seja, $\mathcal{B}_s$ é base para a topologia de $S$. 

- Observe que se $\mathcal{B}$ é enumerável, então $\mathcal{B}_s$ também é enumerável. Isto é, se $\mathcal{M}$ satisfaz o segundo axioma de enumerabilidade, então $S$ também satisfaz. 

### Exercício 2.18

**Questão:** Seja $A$ um subconjunto de $\mathcal{M}$ e suponha que, para todo $x \in A$, existe um aberto $U_x$ contendo $x$ tal que $U_x \subset A$. Mostre que $A$ é aberto em $\mathcal{M}$.

**Resolução:** Basta notar que $A$ é união de abertos:
$$ A = \bigcup_{x \in A} x \subset \bigcup_{x \in A} U_x \subset A \iff A = \bigcup_{x \in A} U_x $$

### Exercício 2.19a

**Questão:** Seja $\{ \tau_i \}_{i \in I}$ uma coleção de topologias de $X$. Mostre que existe uma topologia que contida em todas as $\tau_i$ e que é a maior com esta propriedade.

**Resolução:** Basta tomar $\tau = \bigcap_{i \in I} \tau_i$ e temos que $\tau$ é a topologia mais fina (maior) contida em cada $\tau_i$.

### Exercício 2.19b

**Questão:** Seja $\{ \tau_i \}_{i \in I}$ uma coleção de topologias de $X$. A união de $\tau_i$ é uma topologia? 

Mostre que existe uma topologia que contém todas as $\tau_i$ e que é a menor com esta propriedade.

**Resolução:** 

- Considere $A \in \tau_1$, $A \notin \tau_2$, $B \in \tau_2$ e $b \notin \tau_1$ tais que ou a interseção ou a união de $A$ e $B$ não estão em $\tau_1$ ou em $\tau_2$. 

- Por exemplo,
$$ \tau_1 = \{ \emptyset, \{ a \}, \{ b \}, \{a, b \}, X \}, \quad \tau_2 = \{ \emptyset, \{ a \}, \{ c \}, \{a, c \}, X \} $$

- Temos que $\{ b \} \cup \{ c \} = \{ b, c \} \notin \tau_1 \cup \tau_2$. 

- Denote por $\mathcal{S}$ a coleção de todas as topologias que contém todas as $\tau_i$ e tome $\tau_s = \bigcap_{S \in \mathcal{S}} S$. Temos que:

    - $\tau_s$ é uma topologia. 
    - $\tau_s$ contém todas as $\tau_i$.
    - Se $\tau'$ é uma topologia contendo todas as $\tau_i$, então $\tau_s \subset \tau'$.

- Assim, $\tau_s$ é a menor topologia com a propriedade desejada.

### Exercício 2.25

**Questão:** Mostre que a coleção
$$ \mathcal{B}_1 = \{ [a,b) : a < b, ~a, b \in \mathbb{Q} \} $$
é base de uma topologia diferente da topologia do limite inferior de $\mathbb{R}$.

**Resolução:** 

- $\mathcal{B}_1$ é base de $\mathbb{R}$.

    - Note que $\mathbb{R} = \bigcup_{B \in \mathcal{B}_1} B$. 

    - Dados $x \in \mathbb{R}$ e $U, V \in \mathcal{B}_1$ tais que $x \in U \cap V$, vamos mostrar que existe $W \in \mathcal{B}_1$ tal que $x \in W \subset U \cap V$.

    - De fato, se $U = [a_1, b_1)$ e $V = [a_2, b_2)$, basta tomar $W = [a, b)$ com $a = \max \{ a_1, a_2 \}$ e $b = \min \{ b_1, b_2 \}$.

    - Logo, $\mathcal{B}_1$ é base de $\mathbb{R}$.

- Seja $\tau_1$ a base gerada por $\mathcal{B}_1$. Vamos verificar que essa topologia é diferente da topologia do limite inferior $\tau_l$.

    - Considere um elemento $[\sqrt{2}, \sqrt{2}+1) \in \tau_l$.

    - E considere $B = [a, b)$ um elemento da base $\mathcal{B}_1$ contendo $\sqrt{2}$. 

    - Como $a \in \mathbb{Q}$ e $B$ contém $\sqrt{2}$, temos que $a < \sqrt{2}$ e $a \notin [\sqrt{2}, \sqrt{2}+1)$.

    - Assim, $B$ não é um subconjunto de $[\sqrt{2}, \sqrt{2}+1)$.

    - Note que o argumento é válido para qualquer $x$ irracional no lugar de $\sqrt{2}$. 

    - Logo, $\tau_1$ e $\tau_l$ são diferentes.

### Exercício 2.29a

**Questão:** Mostre que cada subespaço aberto de um espaço topológico separável é separável.

**Resolução:** 

- Seja $(S, \mathcal{S})$ um subespaço aberto de um espaço separável $(M, \tau)$. 

- Como $M$ é separável, existe $D \subset M$ tal que $D$ é denso e enumerável.

- Considere $\tilde{D} = D \cap S$ e tome $\tilde{U}$ aberto em $S$.

- Assim, $\tilde{U} = U \cap S$, em que $U \in \tau$, é aberto em $M$, pois $S$ é aberto.

- Como $D$ é denso em $M$, $D \cap (U \cap S) \neq \emptyset$.

- Dessa forma,
$$
D \cap (U \cap S) = (D \cap S) \cap (U \cap S) = \tilde{D} \cap \tilde{U} \neq \emptyset
$$

- Logo, $\tilde{D}$ é denso em $S$. Como $\tilde{D} \subset D$, $\tilde{D}$ é enumerável.

### Exercício 2.29b

**Questão:** Mostre que cada subespaço fechado de um espaço topológico Lindelöf separável é Lindelöf.

**Resolução:** 

- Seja $(S, \mathcal{S})$ um subespaço fechado de um espaço Lindelöf separável $(M, \tau)$. 

- Tome $\{ \tilde{U}_i \}_{i \in I}$ uma cobertura aberta de $S$. Assim,
$$
\tilde{U}_i = U_i \cap S_i, \quad \forall~i
$$
em que cada $U_i$ é aberto em $M$.

- Portanto, $\{ U_i \}_{i \in I} \cup S^c$ é cobertura aberta de $M$.

- Como $M$ é Lindelöf, existe $J$ enumerável tal que $\{U_j \}_{j \in J} \cup S^c$ é subcobertura enumerável de $M$.

- Dessa forma, $\{\tilde{U}_j \}_{j \in J}$ é subcobertura enumerável de $S$ e, assim, $S$ é Lindelöf.

- De fato, dado $x \in S$ temos que 
$$
x \in M = S^c \cup \bigcup_{j \in J} U_j \implies x \in \bigcup_{j \in J} U_j \cap S = \bigcup_{j \in J} \tilde{U}_j
$$

### Exercício 2.31a

**Questão:** Mostre que $\mathbb{R}$ não é compacto.

**Resolução:** Basta cobrir $\mathbb{R}$ com os abertos da forma $(-n, n)$, que não possui subcobertura finita. 

### Exercício 2.31b

**Questão:** Mostre que um subconjunto finito de um espaço topológico é compacto.

**Resolução:** 

- Tome um conjunto finito $X = \{ x_1, \ldots, x_n \}$ e uma cobertura aberta $\{ U_i \}_{i \in I}$ de $X$.

- Para todo $x \in X$, existe $j \in I$ tal que $x \in U_j$.

- Assim, podemos renomear os conjuntos da cobertura de forma que 
    $$
        x_1 \in U_1, \ldots, x_n \in U_n
    $$

- Ou seja, $X$ é compacto, pois
$$
X \subset \bigcup_{i=1}^n U_i
$$

### Exercício 2.31c

**Questão:** Mostre que um espaço topológico discreto é compacto se, e somente se, é finito.

**Resolução:** 

- $(\Rightarrow)$ Suponha que $(X, \tau)$ é compacto e infinito. 

    - Tome $C = \{ \{x \} : x \in X \}$ uma cobertura aberta de $X$. 

    - Como $X$ é compacto, $X$ admite uma subcobertura finita $C' = \{ \{ x_i \} : x_i \in X, ~1 \le i \le n \}$.

    - Porém, como $X$ é infinito, existe $y \notin \{ x_1, \ldots, x_n \}$. 

    - Como $\{ y \} \notin C'$, temos que $C'$ não cobre $X$, o que é uma contradição. 

    - Logo, $X$ é finito. 

- $(\Leftarrow)$ Pelo item anterior, todo espaço finito é compacto.

### Exercício 2.33

**Questão:** Mostre que se $S$ é um subconjunto conexo de $\mathbb{R}$ e $a,b \in S$ com $a < b$, então $[a, b] \subset S$.

**Resolução:** 

- Suponha que $[a, b] \not\subset S$.

- Então existe $c \in [a,b]$ tal que $c \notin S$.

- Agora basta considerar
$$
    ((-\infty, c) \cap S) \cup ((c, +\infty) \cap S) = S
$$

- Como $(-\infty, c) \cap S$ e $(c, +\infty) \cap S$ são abertos disjuntos, temos que $S$ é desconexo.

<!-- ### Exercício 2.36

**Questão:** Mostre que, para todo $n \in \mathbb{N}$, a esfera unitária 
$$
    S^n = \left\{ (x_1, \ldots, x_{n+1}) \in \mathbb{R}^{n+1} : \sum_{i=1}^{n+1} x_i^2 = 1 \right\}
$$
é conexa.

**Resolução:** 

-  -->

### Exercício 2.38

**Questão:** Seja $M$ um espaço topológico discreto com pelo menos dois pontos. Mostre que 

1. $M$ é localmente conexo, mas não conexo.

2. $C_x = \{ x \}$ para cada $x \in M$ (i.e. o espaço discreto é totalmente desconexo). 

**Resolução:** 

1.
    - Note que, para todo $x \in M$, temos que $\{ x \}$ é aberto (pois topologia discreta) e $\{ x \}$ é conexo. Assim, temos que $M$ é localmente conexo. 
    - Note que $\{ x \}$ e $\{ x \}^c$ são abertos.
    - Ou seja, $\{ x \}$ é aberto e fechado em $M$.
    - Logo, como $\emptyset$ e $M$ não são os únicos abertos e fechados de $M$, temos que $M$ é desconexo.
2.
    - Suponha $y \neq x$ e $y \in C_x$.
    - Então $\{ x \}$ e $\{ y \}$ são abertos, mas também $\{ x \}^c$ e $\{ y \}^c$ são abertos.
    - Logo, como $\emptyset$ e $C_x$ não são os únicos abertos e fechados de $C_x$, temos que $C_x$ é desconexo, o que é uma contradição.

### Exercício 2.40

**Questão:** Se um espaço topológico compacto é localmente conexo, então ele possui um número finito de componentes conexas.

**Resolução:** 

- Seja $\{ C_x : x \in M \}$ as componentes conexas de $M$.

- Como $M$ é localmente conexo e componentes conexas de espaços localmente conexos são abertas, cada $C_x$ é aberto.

- Ou seja, $\{ C_x \}_{x \in M}$ é uma cobertura aberta de $M$.

- Como $M$ é compacto, existe $I \subset M$ finito tal que $\{C_x : x \in I\}$ cobre $M$.

- Por fim, como para todo $x \neq y \in M$ temos que $C_x = C_y$ ou $C_x \cap C_y = \emptyset$, segue que $\{C_x\}_{x \in I}$ são todas as componentes conexas.

## Propriedades Topológicas

### Exercício 3.1

**Questão:** Mostre que o axioma $T_1$ é equivalente a pedir que todo conjunto finito de pontos é fechado.

**Resolução:** 

1. Todo conjunto unitário é fechado sse. todo conjunto finito é fechado.
    - A volta é imediata: todo conjunto unitário é finito.
    - Suponha que todo conjunto unitário é fechado.
    - Como todo conjunto finito é união finita de conjuntos unitários, temos que todo conjunto finito é fechado.
2. $(\Rightarrow)$ Suponha $T_1$.
    - Para todo $y \neq x$, existe $V$ aberto contendo $y$ tal que $\{ x \} \cap V = \emptyset$.
    - Logo, $\{ x \}^c$ é aberto e $\{ x \}$ é fechado.
3. $(\Leftarrow)$ Suponha que todo conjunto finito de pontos é fechado.
    - Dado $x \neq y$ temos que $\{x \}$ e $\{ y \}$ são fechados. 
    - Ou seja, $\{ x \}^c =: V$ e $\{ y \}^c =: U$  são abertos. 
    - Como $x \in U$, $x \notin V$, $y \in V$ e $y \notin U$, temos que $T_1$ é satisfeito.

### Exercício 3.3

**Questão:** Considere $\mathbb{N}$ com a topologia em que 
$$
\overline{A} = \{ kn : ~n\in A, ~k \in \mathbb{N} \}
$$

Mostre que $\mathbb{N}$ com essa topologia é $T_0$, mas não $T_1$.

**Resolução:** 

- Considere sobre $\mathbb{N}$ a topologia $\mathfrak{N} = \{ A^c \subset \mathbb{N} : A = \overline{A} \}$.

- Vamos mostrar que $(\mathbb{N}, \mathfrak{N})$ é $T_0$.

    - Dados $a$ e $b$ naturais distintos, considere $A = \{ a \}$ e $B = \{ b\}$.

    - Então $\overline{A}^c = \mathbb{N} \setminus \{ n a : n \in \mathbb{N} \}$ e $\overline{B}^c = \mathbb{N} \setminus \{ nb : n \in \mathbb{N} \}$ são abertos.

    - Se $b \not| ~a$, então $a \in \overline{B}^c$ e $b \notin \overline{B}^c$. 

    - Se $a \not| ~b$,  pelo mesmo argumento, $b \in \overline{A}^c$ e $a \notin \overline{A}^c$.

    - Como $a \neq b$, um dos dois casos acima ocorre. Logo, $(\mathbb{N}, \mathfrak{N})$ é $T_0$.

- Por fim, mostramos que $(\mathbb{N}, \mathfrak{N})$ não é $T_1$.

    - Basta notar que $\{ a \}$ não pode ser fechado, pois $\overline{\{ a \}} = \{ n a : n \in \mathbb{N} \} \neq \{ a \}$.

### Exercício 3.5

**Questão:** Seja $M$ um conjunto infinito munido da topologia cofinita. Mostre que $M$ é $T_1$, mas não $T_2$.

**Resolução:** 

- Seja $x \in M$. Então $\{ x \}^c$ é aberto e, portanto, $\{ x \}$ é fechado. Ou seja, $M$ é $T_1$. 

- Tome $x, y \in M$ e suponha que existam abertos $U$ e $V$ tais que $x \in U$ e $y \in V$. 

- Assim, podemos escrever
    $$
        U = M \setminus F \quad \text{ e } \quad V = M \setminus G, \quad F, ~G \text{ finitos}
    $$

- Com isso,
    $$
    \begin{aligned}
        U \cap V &= (M \setminus F) \cap (M \setminus G) = (M \cap F^c) \cap (M \cap G^c) \\
        &= M \cap (F^c \cap G^c) = M \cap (F \cup G)^c = M \setminus (F \cup G)
    \end{aligned}
    $$

- Como $F \cup G$ é finito e $M$ é infinito, 
    $$
        U \cap V = M \setminus (F \cup G) \neq \emptyset
    $$

### Exercício 3.7b (Mujica 16.G)

**Questão:** Mostre que $M$ é $T_2$ sse., para cada $a \in M$ temos que
$$
\bigcap \{ \overline{U} : U \in \mathcal{U}_a \} = \{ a \}
$$

**Resolução:** 

1. $(\Rightarrow)$ Suponha que $M$ é $T_2$. 
    - Tome $x \in M$ e $U \in \mathcal{U}_x$. 
    - Se $\overline{U} = \{x\}$, não há nada para fazer.
    - Se existe $y \in \overline{U} \setminus \{ x \}$, como $M$ é Hausdorff, existem $U_1$ e $V_1$ abertos disjuntos tais que $x \in U_1$ e $y \in V_1$.
    - Como $V_1$ é aberto e $U_1 \subset M \setminus V_1$, segue que $M \setminus V_1$ é uma vizinhança fechada de $x$ que não contém $y$. 
    - Repetindo os passos acima temos que a interseção de todas as vizinhanças fechadas de $x$ é igual a $\{ x \}$.
2. $(\Leftarrow)$ Suponha que a igualdade do enunciado é válida.
    - Por hipótese, existe $U \in \mathcal{U}_x$ tal que $x \in \overline{U}$ e $y \notin \overline{U}$. 
    - Assim $V := M \setminus \overline{U}$ é um aberto que contém $y$.
    - Logo, $x \in U$, $y \in V$ e $U \cap V = \emptyset$.

### Exercício 3.8 (Mujica 18.B)

**Questão:** Prove que o espaço de Sierpinski é normal, mas não é regular nem Hausdorff.

**Resolução:** 

1. Sierpinski é normal.
    - Seja $X = \{ a, b\}$ e $\tau = \{ \emptyset, \{ a \}, \{ a, b\} \}$.
    - Note que os fechados são $\mathcal{F} = \{ \emptyset, \{ b \}, \{ a, b\} \}$.
    - Como não existem dois fechados disjuntos, o resultado segue trivialmente.
2. Sierpinski não é regular.
    - Considere o fechado $\{ b \}$ e $a \in \{ b \}^c$. 
    - O único aberto contendo $\{ b \}$ é $M$, mas $a \in M$. 
    - Ou seja, nenhum aberto contendo $a$ é disjunto de $M$. 
    - Logo, $X$ não é regular.
3. Sierpinski não é Hausdorff.
    - Considere os pontos $a$ e $b$.
    - Pelo mesmo argumento acima, $X$ não é Hausdorff. 

### Exercício 3.9 (Mujica 17.C)

**Questão:** Seja $X$ um conjunto infinito com a topologia cofinita. Prove que $X$ não é regular.

**Resolução:** 

- Tome $B$ fechado, portanto finito, e $a \in B^c$. 
- Suponha que $X$ seja regular. 
- Então existem abertos $U$ contendo $a$ e $V$ contendo $B$ disjuntos.
- Podemos escrever
$$
U = M \setminus F, \quad V = M \setminus G, \quad F,G \text{ finitos }
$$
- Portanto,
$$
\emptyset = U \cap V = M \setminus (F \cup G) 
$$
- Como $F \cup G$ é finito, isso contradiz a hipótese de que $U \cap V = \emptyset$.

### Exercício 3.11a (Mujica 17.E)

**Questão:** Considere sobre $\mathbb{R}$ a família
$$
\mathcal{B} = \{ (a,b)  : a, b \in \mathbb{R}, ~a < b \} \cup \{ (a,b) \cap \mathbb{Q} : a, b \in \mathbb{R}, ~a < b \}
$$

Mostre que $\mathcal{B}$ é uma base de uma topologia $\tau$ de $\mathbb{R}$.

**Resolução:** 

1. O espaço todo é união dos elementos da base:
$$
\mathbb{R} = \bigcup_{B \in \mathcal{B}} B
$$
2. Existe elemento da base que "faz o sanduíche":
    - Seja $x \in \mathbb{R}$ e $U, V \in \mathcal{B}$ tais que $x \in U \cap V$. 
    - Escreva $U$ e $V$ como intervalos. 
    - Tome $W$ um intervalo tal que $x \in W \subset U \cap V$.
    - Note que $W \in \mathcal{B}$.

### Exercício 3.11c (Mujica 17.E)

**Questão:** Considere sobre $\mathbb{R}$ a família
$$
\mathcal{B} = \{ (a,b)  : a, b \in \mathbb{R}, ~a < b \} \cup \{ (a,b) \cap \mathbb{Q} : a, b \in \mathbb{R}, ~a < b \}
$$

Mostre que $(\mathbb{R}, \tau)$ não é regular.

**Resolução:** 

- Tome $(a, b) \cap (\mathbb{R} \setminus \mathbb{Q})$ (fechado) e $c \in (a,b) \cap \mathbb{Q}$.
- Pela densidade dos racionais e irracionais, todo aberto contendo $c$ intersecta o fechado. 

### Exercício 3.12

**Questão:** Seja $(M, \tau)$ um espaço regular. Dado um fechado $A \subset M$ e um ponto $b \in A^c$, mostre que existem abertos $U, ~V \in \tau$ tais que $A \subset U$, $b \subset V$ e $\overline{U} \cap \overline{V} = \emptyset$.

**Resolução:** 

- Como $M$ é regular, existem $U_0, ~V_0 \in \tau$ tais que $A \subset U_0$, $b \in V_0$ e $U_0 \cap V_0 = \emptyset$. 

- Para cada $a \in A$, como $a \in U_0$, temos que existe $U_a \in \tau$ tal que $a \in U_a \subset \overline{U}_a \subset U_0$.

- Como $b \in V_0$, existe $V$ aberto tal que $b \in V \subset \overline{V} \subset V_0$.

- Definimos 
$$
U = \bigcup_{a \in A} U_a
$$

- Dessa forma, $A \subset U$ e $b \in V$.

- Como
$$
\overline{U} =\overline{\bigcup_{a \in A} U_a} = \bigcup_{a \in A} \overline{U}_a \subset U_0
$$

- Temos que
$$
\overline{U} \cap \overline{V} \subset U_0 \cap V_0 = \emptyset
$$

### Exercício 3.14a (Mujica, 21.H)

**Questão:** Seja $(M, \tau)$ um espaço de Hausdorff. E seja $K$ um subconjunto compacto de $M$ e $y \in K^c$. Mostre que existem abertos disjuntos $U$ e $V$ em $M$ tais que $K \subset U$ e $y \in V$.

**Resolução:** 

1. Aplique Hausdorff para obter os abertos.

    - Como $M$ é Hausdorff, para todo $x \in K$ existem $U_x$ e $V_x$ abertos disjuntos tais que $x \in U_x$ e $y \in V_x$. 

2. Aplique compacidade.

    - Como $K$ é compacto e
    $$
    K \subset \bigcup_{x \in K} U_x
    $$

    - Temos que existe $\Delta \subset K$ finito tal que 
    $$
    K \subset \bigcup_{x \in \Delta} U_x =: U
    $$

    - Seja
    $$
    V = \bigcap_{x \in \Delta} V_x \implies y \in V
    $$

    - Assim, $K \subset U$ e $y \in V$.

3. Mostre que $U \cap V = \emptyset$.

    - Tome $z \in U \cap V$. 

    - Então $z \in V_x$ para todo $x \in \Delta$ e existe $x_0 \in \Delta$ tal que $z \in U_{x_0}$.

    - Ou seja, $z \in U_{x_0} \cap V_{x_0}$, o que é uma contradição.

    - Logo, $U \cap V = \emptyset$.

<!-- ### Exercício 3.14b (Mujica, 21.H)

**Questão:** Seja $(M, \tau)$ um espaço de Hausdorff. E sejam $K$ e $L$ dois subconjuntos compactos e disjuntos de $M$. Mostre que existem abertos disjuntos $U$ e $V$ de $M$ tais que $K \subset U$ e $L \subset V$.

**Resolução:**  -->

### Exercício 3.15 (Mujica, 21.I)

**Questão:** Seja $(M, \tau)$ um espaço de Hausdorff, $K$ um subconjunto compacto de $M$ e $U_1, ~U_2$ abertos tais que $K \subset U_1 \cup U_2$. Mostre que existem dois subconjuntos compactos $K_1$ e $K_2$ de $M$ tais que
$$
K = K_1 \cup K_2, \quad K_1 \subset U_1, \quad K_2 \subset U_2
$$

**Resolução:** 

- Considere $K \setminus U_1$ e $K \setminus U_2$. 

- Note que $K \setminus U_1$ e $K \setminus U_2$ são disjuntos, pois
$$
(K \setminus U_1) \cap (K \setminus U_2) = K \setminus (U_1 \cup U_2) = \emptyset
$$

- E também note que $K \setminus U_1$ e $K \setminus U_2$ são compactos, pois são subconjuntos fechados de um compacto:
$$
K \setminus U_1 = K \cap (M \setminus U_1)
$$

- Como $M$ é Hausdorff, existem $V_1$ e $V_2$ abertos disjuntos tais que $K \setminus U_1 \subset V_1$ e $K \setminus U_2 \subset V_2$.

- Tomemos $K_1 = K \setminus V_1$ e $K_2 = K \setminus V_2$.

- Note que $K_1 \subset U_1$ e $K_2 \subset U_2$.

- Se $K = K_1 \cup K_2$, temos o que queríamos.

- Caso contrário, aplicamos o algoritmo acima novamente.

### Exercício 3.17a

**Questão:** Seja $(M, \tau)$ um espaço localmente compacto. Mostre que todo subespaço aberto de $M$ é localmente compacto.

**Resolução:** 

- Suponha $X$ um subespaço aberto de $M$. 
- Tome $x \in X$ e $U$ uma vizinhança aberta de $x$ em $X$.
- Como $X$ é aberto, $U$ é aberto em $M$. 
- Como $M$ é localmente compacto, existe uma base de vizinhanças para $x$ consistindo de compactos.
- Assim, $x \in V \subset U$ em que $V$ é uma vizinhança compacta de $x$ em $M$.
- Como $V \subset U \subset X$, temos que $V$ é uma vizinhança compacta de $x$ em $X$.

### Exercício 3.17b

**Questão:** Seja $(M, \tau)$ um espaço localmente compacto. Mostre que todo subespaço fechado de $M$ é localmente compacto.

**Resolução:** 

- Suponha $X$ um subespaço fechado de $M$.
- Primeiro, construímos uma vizinhança aberta de $x$ em $X$.
    - Tome $x \in X$ e $V$ uma vizinhança aberta de $x$ em $M$ tal que $\overline{V}$ é compacto.
    - Assim, temos que $V_x = V \cap X$ é uma vizinhança aberta de $x$ em $X$. 
- Vamos verificar que $\overline{V}_x$ é compacto.
    - Seja $\{ \tilde{U}_i \}_{i \in I}$ uma cobertura aberta de $\overline{V}_x$.
    - Assim, cada $\tilde{U}_i = U_i \cap \overline{V}_x$, em que $U_i$ é aberto.
    - Note que $\{ U_i \}_{i \in I} \cup \{ X^c \}$ é aberto e cobre $\overline{V}$, pois $V_x = V \setminus X^c$.
    - Pela compacidade de $\overline{V}$, temos que existe $J \subset I$ finito tal que $\{ U_j \}_{j \in J} \cup \{ X^c \}$ cobre $\overline{V}$.
    - Logo, $\{ \tilde{U}_j \}_{j \in J}$ é uma subcobertura finita de $\overline{V}_x$. 

### Exercício 3.18

**Questão:** Seja $(M, \tau)$ um espaço de Hausdorff. Mostre que a interseção de dois subespaços localmente compactos de $M$ é localmente compacta.

**Resolução:** 

- Lembre que um espaço Hausdorff é localmente compacto sse. todo ponto possui vizinhança compacta.

- Assim, sejam $X_1$ e $X_2$ dois subespaços localmente compactos de $M$.

- Como $M$ é Hausdorff, $X_1$ e $X_2$ também são.

- Tome $x \in X_1 \cap X_2$. 

- Como $x \in X_1$, que é Hausdorff localmente compacto, existe $V_1$ vizinhança compacta de $x$ em $X_1$.

- Analogamente, existe $V_2$ vizinhança compacta de $x$ em $X_2$. 

- Assim, $V_1 \cap V_2$ é uma vizinhança de $x$ em $X_1 \cap X_2$.

- Como $M$ é Hausdorff, $V_1$ e $V_2$ são fechados em $M$.

- Portanto, como $V_1 \cap V_2$ é um subconjunto fechado de um compacto, segue que $V_1 \cap V_2$ é compacto.

- Logo, $X_1 \cap X_2$ é Hausdorff (pois subespaço de $M$) e todo ponto possui vizinhança compacta, temos que $X_1 \cap X_2$ é localmente compacto.

### Exercício 3.19

**Questão:** Seja $(M, \tau)$ um espaço localmente compacto. Mostre que $A \subset M$ é aberto em $M$ sse. $A \cap K$ é aberto em $K$ para cada compacto $K \subset M$.

**Resolução:** 

1. $(\Rightarrow)$ Suponha $A$ aberto em $M$, em que $M$ é localmente compacto.

    - Tome $K \subset M$ compacto. 

    - No subespaço $K$, temos que $A \cap K$ é aberto, pois $A$ é aberto em $M$.

2. $(\Leftarrow)$ Suponha $A \cap K$ aberto em $K$ para cada compacto $K \subset M$.

    - Seja $x \in A$.

    - Como $M$ é localmente compacto, existe $V_x$ vizinhança aberta de $x$ tal que $\overline{V_x}$ é compacto.

    - Assim, $A \cap \overline{V_x}$ é aberto em $\overline{V_x}$ por hipótese.

    - Logo, $A$ é aberto em $M$.