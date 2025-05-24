# Research journal

# 2025

2025-05 May
--
**2025-05-14 Mercredi**

### Read <span style='color:skyblue;fontsize="bold"'> An evaluation of distribution parameters estimation</span>

### Seminaire sur le thème "Imputation des données manquantes: Cas de données en coupe instantannée"
- Invité par Dr OLOITCHA
- Présentateur: Kevin AGOGNON étudiant à la Chaire
- Participants: Collegues du présentateur et moi



**2025-05-15 Jeudi**

### Read <span style='color:skyblue;fontsize="bold"'> An evaluation of distribution parameters estimation</span>

**2025-05-19 Lundi: Revue de littérature(début)**
### Read <span style='color:skyblue;fontsize="bold"'> Univariate Stable distribution: Models for Heavy Tailed Data</span>
[https://edspace.american.edu/jpnolan/test-2/](https://edspace.american.edu/jpnolan/test-2/)
- Chapitre 1: Traite d'une introduction non technique aux distributions stables univariées
- Chapitre 2: Traite d'une vue d'ensemble des applications utilisant les lois stables
- Chapitre 3: Mathematical exposition of stable laws
- Chapter 4: Parameter estimation
- Préface
  - Le paramètres d'echelle n'est pas à confondre avec le standard deviation. Ce dernier n'existe pas pour la plupart et le paramètre de localisation ne doit pas être confondre avec la moyenne $\mu$
  - Il est préférable d'utiliser ($\alpha,\beta,\gamma,\delta$) comme les paramètres
- On a 4 paramétrisation de lois stables présentés:0-parametrisation,1-parametrisation,2-parametrisation,3-parametrisation
- Chapitre 1: Basic Properties of Univariate Stable Distributions
  - Stable distributions are a rich class of probability distributions that allow skewness and heavy tails and have many mathematical properties
  - We need to use computer programs to compute stable densities, distribution functions, and quantiles.
  - Pour des simplicités algébriques, il est facile de travailler avec la paramétriqation S ($\alpha,\beta,\gamma,\delta$; 1)
  - La constante $c_n >0$ dans la condition de stabilité de la loi X 
  $$ \sum X_i \overset{d}{=} c_nX + d_n $$
  joue le rôle d'echelle. Elle est donc positive.
  - Une loi stable symétique $\implies \phi_X(t)$ est réelle ($\phi$ est la fonction caractéristique) 
  - Une autre caractérisation des distributions stables est donnée par le théorème centrale limite généralisé
  - La façon concrete de décrire toutes les distributions stables est à travers leur fonction caractéristique ou transformation de Fourier
  - Il y a de bonnes raisons d'utiliser différentes paramétrisation dans des situations différentes
  - Si $\beta=0$, la paramatrisation O et 1 sont identiques
  - Il est recommandé d'utiliser la paramétrisation S ($\alpha,\beta,\gamma,\delta$; 1) pour des travaux numériques et pour l'inférence statistique: c'est la forme simple pour la fonction caractéristique qui est continue pour tous les paramètres. La paramétrisation 1 est la plus utilisée quand l'on s'intéresse aux propriétés algébriques
  - Les paramétrisations 0 et 1 sont les standart dans la littérature
  - Pour avoir une paramétrisation dont le paramètre d'echelle et de localisation ont une signification intuitive, on introduit la paramétrisation 2:  the location parameter is the mode and the scale parameter agrees with the standard scale parameters in the Gaussian and Cauchy cases.
  - The 2- parametrisation is useful in signal processing and in linear regression problems when there is skewness.
  - Dans la littérature, il y a 11 paramétrisation de la loi stable

**2025-05-21 Mercredi: Revue de littérature(suite)**
### Read <span style='color:skyblue;fontsize="bold"'> The Truncated Normal Distribution</span>
Nous voulons tronquer une partie de la loi normale de sorte que la fonction de densité soit nulle sur cette partie. Autrement dit nous voulons qu'il existe a, b  pour $-\infty <a <b <+\infty$ tel que $\forall x \notin ]a,b[, f(x) = 0$

Dans plusieurs cas, on désire utiliser la distribution normale pour décrire la variation aléatoire d'une quantité qui pour des raisons physiques doit être strictement positive. La façon de garder les caractéristiques de la normale et d'éviter les valeurs négatives est d'utiliser la distribution normale tronquée. \
On modifie le pdf de la distribution normale en posant les valeurs en dehors de l'intervalle [a,b] = 0 et en reduisant les valeurs dans [a,b] pour que l'intégrale totale soit égale à 1. Soit $\phi(\mu,\sigma,a,b;x)$ le pdf de la distribution normale tronquée avec $\mu, \sigma$ les paramètres de la distribution de base(celle non tronquée) et a,b les bornes du domaine de troncature alors
$$ \phi(\mu,\sigma,a,b;x) = \begin{cases}
    0 & si \; x \leq a \\
    \frac{f(x; \mu,\sigma)}{F(b)-F(a)} & si \; x \in [a,b]\\
    0 & si \; x \geq b
\end{cases}$$
où f et F sont respectivement le pdf et cdf de $\mathcal{N}(\mu,\sigma)$
- La troncature déforme la forme de la distribution gaussienne qui n'est plus en forme de cloche même dans le cas où l'intervalle de troncature est symétrique.
- Le cdf de la normale tronquée se définit directement par
$$ \Phi(\mu,\sigma,a,b;x) = \int_{a}^{x} \phi(\mu,\sigma,a,b;x)dx \qquad \text{si} \; x \in [a,b]; 0 \, sinon$$





### Read <span style='color:skyblue;fontsize="bold"'> ASA066 The Standard Normal Cumulative Density Function
</span>
Il m'est toujours arriver de me poser la question de comment évaluer l'intégrale

$$\int_{-\infty}^{x} \frac{1}{\sqrt{2\pi}}e^{-\frac{1}{2}t^2}dt$$
i.e calculer les propabilités cumulatives d'une distribution normale standard.
Bien évidemment, nous savons que de méthodes analytiques ne nous permettront pas de répondre à cette question: il faut faire appel aux méthodes numériques. 

Pour moi Martin-Junior, avec mes connaissances actuelles, j'utiliserais une des méthodes d'intégration numérique des plus puissantes: la méthode de Romberg. Le problème que je pourrai avoir est de pouvoir quantifier nécessairement $-\infty$ pour pouvoir proposer une subdivision du domaine d'intégration, ce sur quoi repose la méthode de Romberg. Je pourrais être tenté de poser $-\infty = - 10^3$ pour une rapidité de calcul. Mais il est tout à fait clair que en général, $- 10^9$ est plus précis que $-10^3$ en tant qu' appproximation de $-\infty$.Et dans ce second cas, le temps et les ressources de calcul deviennent importants. Une autre façon possible serait d'utiliser la méthodes des quadrature mais dans ce cas nous pourrions rencontrer beaucoup de difficultés. Dans ce papier, David Hill décrit une manières de faire ce calcul est décrit en proposant l'algorithme AS 66.

Disponible [ici](https://www.jstor.org/stable/2346800), il s'agit d'une façon de calculer qui utilise l'approximation de l'intégrande par une fonction rationnelle ou une approximation asymptotique. Les approximations sont issus du travail `ADAMS, A. G. (1969). Algorithm 39. Areas under the normal curve. Computer J., 12, 197-198. ` auquel je n'ai pas accès.

L'algoritme utilise des propriétés intéressantes de la gausienne notamment la symétrie. Soit à calculer
$$ P(Z \leq x) \; avec \; Z \sim \mathcal{N}(O,1)$$
Il suffit d'évaluer la probabilité des queues et d'utiliser les propriétés suivantes: \
Si $x \geq 0, P(Z < x) = 1-P(Z>x)$: $P(Z>x)$ est la queue supérieure \
Si $x \leq 0, P(Z > x) = 1-P(Z<x)$: $P(Z<x)$ est la queue inférieure. \
Donc il suffit d'évaluer la queue supérieure $\forall x$ car elle est égale à la queue inférieure $P(Z< -x) = P(Z>x)$.\
Le calcul de la queue supérieure se déroule comme suit:
- Définition de valeurs limites au delà desquelles les queues $\sim 0$: E.g: Si $z > 7, P(Z < z) \simeq 1$ on retourne 1 directement.
- Selon le cas $Z \leq 1.28 \;ou\; \geq 1.28$, on utilise des approximations différentes.






### Read <span style='color:skyblue;fontsize="bold"'> Truncated stable random variables: characterization and simulation</span>

### Read <span style='color:skyblue;fontsize="bold"'> The Pareto-Lévy Law and the Distribution of Income
</span>

Le but de l'article est double. L'auteur souhaite rendre compte d’un ensemble de nouveaux modèles pour certaines propriétés de distribution d’une classe importante de grandeurs économiques, qui inclut le "revenu". L'auteur a l’intention d’attirer l’attention de l’économiste sur la grande importance potentielle des distributions de probabilités "stables non gaussiennes".
- Le papier développe les points principaux dans le cadre d'une théorie de la répartition des revenus mais l'approche sera traduisible en termes de quantités similaires et la théorie peut bien être plus raisonnable, ou l’adaptation empirique meilleure, dans le cas de certaines autres quantités. 
- Cet article est presque exclusivement théorique. Le point de départ est une observation empirique intéressante, à savoir que sur 
une certaine gamme de valeurs du revenu U, **sa distribution n’est pas nettement influencée soit par la structure socio-économique de la communauté en cours d’étude**, ou par la définition choisie pour "revenu". Car ces deux élements peuvent influencer les valeurs prises par certains paramètres d’une loi de distribution apparemment universelle(la Pareto). 
- Le papier introduit une nouvelle version de la loi de Pareto qui appartient à la classe des distributions stables et désigner par `Pareto-Levy` distribution.
- Mais une limite(que je peux améliorer): Cette loi explique partiellement la 
données relatives à la tranche de revenu intermédiaire.
- Les motivations de la loi est double: D’abord, 
parmi toutes les interpolations possibles du Pareto faible (pareto asymptotique), la loi P-L est la seule qui satisfait strictement un (fort) forme de la condition d’invariance ou de la distribution, par rapport à la définition du revenu. Car on l'avais dit, la définition du revenu influence les paramètres de la distribution. Deuxièmement, une distribution P-L est une possible distribution limite(puisque stable) des sommes de variables aléatoires. C’est-à-dire, comme nous allons le démontrer, que la distribution gaussienne n’est pas la seule limite possible (comme on le suppose trop généralement), et qu’il est inutile (et même insuffisant) d’essayer de sauver l’argument limite en l’appliquant à log U, au lieu de 
U, comme on le fait dans certaines théories conduisant à la "loi log-normale" pour U. 
- La loi P-L a des propriétés désirables, l'inconvénient de se limiter à l'interpolation de la loi de Pareto lorsque $1 < \alpha < 2$.
- Le papier étudie aussi les P-L processus stochastiques, une famille de modèles pour la variation des revenus.
  - Ces processus conservent certains aspects souhaitables les propriétés des processus gaussiens classiques, sans pour autant que la variation du revenu ne puisse être gaussienne.
  - Il se trouve que dans la gamme de revenu élevé, un processus P-L Markovian peut être approximé par une marche aléatoire de $log(U)$
#### Introduction
**Loi forte de Pareto: Une variante de la loi de Pareto** \
Soit P(u) le pourcentage d'individus ayant un revenu U dépassant une certaine quantité u(u est supposé être une variable continue). La loi de Pareto forte dit que 
$$\begin{equation}
  P(u) = \begin{cases}
    (u_0/u)^{\alpha} &si \, u >u_0 \\
    1 &si \, u <u_0
  \end{cases}
\end{equation}$$
La densité de proba est alors
$$\begin{equation}
  p(u) = \begin{cases}
    \alpha u_0^{\alpha} u^{-\alpha-1} &si \, u >u_0 \\
    0 &si \, u <u_0
  \end{cases}
\end{equation}$$

Cette distribution est complètement spécifiée par deux variables d'états: $u_0$ un facteur d'echelle et $\alpha$ qui est un certain genre d'indice d'inégalité de la distribution.\
La loi forte laisse la valeur de a indéterminée (bien que, dans certains cas, on affirme immédiatement que a > 1).
On peut également trouver l'énoncé plus fort selon lequel a ≥ 3/2 : la variante correspondante de la loi forte sera alors appelée la loi de Pareto la plus forte.\
Graphiquement, la loi forte implique que le graphe (« double logarithmique ») de y = log P en fonction de v = –log t est une ligne droite.
- Empiriquement, la loi est également vérifiée pour des échantillons de quelques centaines de personnes. On considère la variable U comme une variable aléatoire prenant les valeurs u.

**Loi faible de Pareto** 

La loi de Pareto la plus forte est désormais reconnue comme empiriquement non justifiée (et il convient de noter que de nombreuses prétendues « réfutations » de « la » loi de Pareto ne s'appliquent qu'à cette variante).

En revanche, la validité de la loi de Pareto ne fait guère de doute si l'on s'intéresse aux valeurs "suffisamment" grandes de u.

La meilleure façon de tenir compte des limitations de la loi forte est simplement d'énoncer que : \
P(u) **"se comporte comme"** $(u_0/u)^{-\alpha}$ lorsque $u \to \infty$. \
**C'est la loi de Pareto faible**.\
Une telle affirmation n'est utile que si la définition exacte de "se comporte comme" est conforme aux observations empiriques
$$ P(u) \sim (u_0/u)^{-\alpha}$$ 
i.e
$$\frac{P(u)}{(u_0/u)^{-\alpha}} \to 1 \; \text{lorsque} \; u \to \infty$$
$$P(u) = \{1 + e(u)\}(u/u_0)^{-\alpha}, \; où \; e(u) \to 0,\, lorsque \, u \to \infty $$
**Interpolation avec la loi de Pareto faible**