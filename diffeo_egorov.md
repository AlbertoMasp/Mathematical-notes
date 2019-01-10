


# Diffeomorphism and the Egorov theorem 

Considero un diffeomorfismo del toro
$$
x \mapsto x + \beta(x) , \quad x \in \mathbb T
$$
dobe $\beta(x)$ è $2\pi$ periodica. Definisco  l'operatore lineare
$$
(U_\beta u)(x) = \sqrt{1+\beta_x(x)} \, u(x + \beta(x))
$$
Tale operatore è una isometria di $L^2(\mathbb T, \mathbb C)$, quindi in particolare è simplettico. 

Parto da equazione 
$$
i \dot u = {\rm Op}^w(a) u
$$
e voglio capire come il cambio di coordinate
$$
u(x) = (U_\beta v)(x)
$$
 mi cambia l'equazione. Ovviamente $v$ soddisfa
$$
i \dot v = \left(U_\beta^{-1}{\rm Op}^w(a) U_\beta\right) v
$$
e voglio capire come si trasforma lo pseudodiff. Conviene usare Egorov, ma per farlo dobbiamo realizzare $U_\beta$ come flusso a tempo $1$ di una pde. Faccio così: definisco
$$
U_\beta(\tau)\colon  \ \ \ u(x) \mapsto \sqrt{1+ \tau\beta_x(x)} \, u(x+\tau\beta(x))
$$
e verifico direttamente che è il propagatore $U(\tau,0)$ dell'equazione 
$$
\partial_\tau u  = b(\tau,x) \partial_x u + \frac12 (\partial_x b)u , \qquad b(\tau,x):= \frac{\beta(x)}{1+\tau \beta_x(x)}
$$
che riscrivo come 
$$
i \partial_\tau u = {\rm Op}^w \left(- b(\tau, x)\xi\right) u
$$
A questo punto ho che $U_\beta(\tau) \equiv U(\tau,0)$, che è la solutione di
$$
i \partial_\tau U(\tau,0) = {\rm Op}^w \left(- b(\tau, x)\xi\right) \, U(\tau,0) , \qquad U(0,0) = id
$$
 Ora il teorema di Egorov mi dice che
$$
U(\tau,0)^{-1} {\rm Op}^w(a) U(\tau,0) = {\rm Op}^w(a\circ \phi^\tau) + l.o.t.
$$
dove $\phi^\tau$ è il flusso a tempo $\tau$ dell'hamiltoniana $-b(\tau,x)\xi$, ovvero
$$
\begin{cases}
\dot x = - b(\tau,x)\\
\dot \xi = b_x(\tau,x) \xi
\end{cases}
$$
La soluzione di questo sistema è 
$$
\phi^t(y,\eta) = \left(y + \check\beta(\tau,y) , \ (1+\tau \beta_x(x))\eta\vert_{x = y + \check\beta(\tau,y)} \right) 
$$
dove 
$$
y = x+ \tau \beta(x) \Leftrightarrow x = y + \check\beta(\tau,y)
$$
## Egorov theorem
A questo punto voglio calcolare meglio 
$$
A(\tau):= U(\tau,0)^{-1} {\rm Op}^w(a) U(\tau,0) 
$$
Osserviamo che se $U(t,0)$ e' il propagatore di $i \dot \psi = X \psi$, allora $U(t,0) = e^{-i t X}$, e dunque
 $A(\tau)$ è soluzione dell'equazione di heisenberg
$$
\partial_\tau A(\tau) = i  [X, A(t)] , \qquad A(0) =  {\rm Op}^w(a)
$$
Nel nostro caso vogliamo risolvere tale equazione ricorsivamente, usando che
$$
X = {\rm Op}^w(\chi) , \qquad \chi \in S^1
$$
Cerco 
$$
A(\tau) =  {\rm Op}^w( a_0(\tau) + a_1(\tau) + \ldots ) , \qquad a_j \in S^{m-2j}
$$
Butto nell'equazione di Heisenberg e risolvo in ordini: a sinistra trovo
$$
 \partial_\tau a_0(\tau) + \partial_\tau a_1(\tau) + \ldots
$$
a destra invece dal calcolo pseudodiff con weyl quantzation
$$
\{ \chi, a_0 + a_1 + \ldots \}_M =\frac{1}{i} \{ \chi, a_0 \} + r(\chi, a_0) + \frac{1}{i}\{ \chi, a_1 \} + r(\chi, a_1) 
$$
dove abbiamo usato il fatto generale che con weyl quantzation
$$
\{ a, b  \}_M - \frac{1}{i} \{a, b \} = r(a,b) \in  S^{m+m'-3} . 
$$
Uguagliando i termini dello stesso ordine otteniamo il sistema di equazioni
$$
\begin{cases}
\partial_\tau a_0 = \{ \chi, a_0 \} ,  & a_0(0) = a\\
\partial_\tau a_1 = \{\chi, a_1 \} + r(\chi, a_0) , & a_1(0) = 0\\
\vdots \\
\partial_\tau a_j = \{\chi, a_j \} + r(\chi, a_{j-1}) , & a_j(0) = 0
\end{cases}
$$
che risolvo ora in maniera ricorsiva:
$$
\begin{cases}
a_0(\tau) = a \circ \phi^\tau_\chi \\
a_1(\tau) = \int_0^t r(\chi, a\circ \phi^s_\chi) \circ \phi^{t-s}_\chi \, ds \\
\vdots \\
a_j(\tau) = \int_0^t r(\chi, a_{j-1}(s)) \circ \phi^{t-s}_\chi \, ds 
\end{cases}
$$

## Applicazione
Se ora prendiamo
$$
a(x,\xi) = f(x)g(\xi) , \qquad \chi(x,\xi) =- b(x) \xi 
$$
con $g(\xi)$ simbolo omogeneo di ordine $\alpha$: $g(\lambda \xi) = \lambda^\alpha g(\xi)$, $\forall \lambda >0$. Quindi troviamo che
$$
\left(a\circ \phi^t_\chi\right)(y,\eta) = f(y + \check\beta(t,y)) \, g( (1+\beta_x)\vert_{x=y+\check\beta(t,y)}\eta) = 
 f(y + \check\beta(y)) \,  \left((1+\beta_x)\vert_{x=y+\check\beta(t,y)}\right)^{\alpha}g( \eta)
$$
quindi e' di nuovo un simbolo omogeneo dello stesso ordine di prima. Ora basta notare che il resto $r(\chi, a_j)$ e' anchesso omogeneo; infatti ha una espansione in simboli omogenei.
