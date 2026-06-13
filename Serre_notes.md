$$
\newcommand{\tr}{\operatorname{tr}}
$$
# Notes

- group representation 
- G-invariant subspace
- subrepresentation
- irreducible representation 
  - G-invariant subspace are trivial (bot or top)
  - if the representation space is defined over complex field, then the complex conjugate of an irrep is also irrep, i.e. if $\rho : G\to GL_\mathbb{C}(V)$ is an irrep, then $\rho^* \coloneqq \rho^*(g) = (\rho(g))^*$ is also an irrep
    - use the fact that the whole space $V$ over $\mathbb{C}$ is closed under complex conjugate thanks to canonical basis $(\cdots,1,\cdots)^T$. but a subspace may not be close as well, for example $W = \text{span}((1,i)^T) \neq W^*$   
- G-linear / G-equivariant / intertwinning mapping P
  - $P:V\to W,P(\rho_V(g)v)=\rho_W(g)P(v)$,
  - if P is G-linear, then $\ker P$ and $\Im P$ are $G$-invariant
  - linear combination of G-linear mappings is still G-linear : vector space $\text{Hom}_G(V, W)$
  - composition of G-linear mappings is still G-linear 
- G-linear isomorphism 
  - if $T : V \to W$ is a G-linear isomorphism, then $T^{-1}$ is also a G-linear isomorphism 
  - if $T$ is a G-linear isomorphism, then $T(W)$ is G-invariant iff $W$ is G-invariant. So G-linear isomorphism preserve the irreducibility 
- internal direct sum of subrepresentation 
- projection properties
  - P is a projection onto a subspace $W \subset V$ if $P$ linear and idempotent $P^2 = P$
  - $\forall v \in V, v = Pv + (I-P)v \implies V = \text{Im}(P) \oplus \text{Ker}(P)$
  - no need for finiteness of V
- orthogonal space is complementary in **finite** dim vector space 
  - infinite case : let $V = L^2([-1,1])$, we have $\forall P\in \mathbb{R}[X] = W, f \perp P \implies f = 0$, so $W + W^\perp \neq V$
- example of decomposition into invariant subrepresentation
  -  consider $G=S_3$ that permutes the canonical basis of $\mathbb{R}^3$, $W=\mathbb{C}\{(1,1,1)^T\}$ is $G$-invariant, all plan not containing (1,1,1) is a complementary of W but not necessarily G-invariant. but $W^\perp$ is. 
    - <u>prove that in this $S_3$ case, the orthogonal plan {x+y+z = 0} is the **only** G-invariant complementary of W.</u>
  - given a ~~finite~~ vector space equiped with a scalar product, $V = W \oplus W^\perp$, if the actions of $G$ are **unitary** (preserves scaler product), then $W^\perp $ is invariant iff $W$ invariant, because $x\in W, y\in W^\perp \implies\langle x,g\cdot y\rangle = \langle g\cdot x,g\cdot y\rangle = \langle x,y \rangle = 0 \implies g\cdot y \in W^\perp$
  - what if the actions are not unitary, and we still want to decompose into G-invariant subspaces? try constructing another scaler product that makes group actions unitary

## Maschke's theorem 

- Maschke's theorem
  - finite representation over complex field of finite group is totally reducible : $V = \bigoplus_k U_k \cong \bigoplus_\mu a_\mu V^\mu$ where $V^\mu$ is a representative of its class $C^\mu = \{ U_k \mid U_k \cong V^\mu \}$ and $a_\mu$ is the multiplicity i.e. $\text{card}(C^\mu)$
    - example : regular representation of $S_3$ on $V$. let $(e_i)$ be the 6 elements of $S_3$,  we have $V = U_1 \oplus U_2 \oplus U_3 \oplus U_4 \cong 1 \cdot V^{\mu_1} \oplus 1 \cdot V^{\mu_2} \oplus 2 \cdot V^{\mu_3}$ where $U_3 \cong U_4$ 
  - it's clear that we want to prove : if V has a strict subrepresentation W which is G-invariant , then V can be decomposed into direct sum: $V = W \oplus U$ where $U$ is also a G-invariant subrepresentation,
  - why the average projection can solve this problem? motivation ? 
    - We already know that projection is useful for direct sum decomposition. 
    - So the key is to construct a projection $\tilde P$ that satisfies $\Im \tilde P = W$ and $\ker \tilde P$ is G-invariant. 
    - and we know that if $\tilde P$ commutes with group actions, then $\ker \tilde P$ is invariant
    - the objective becomes : make $\tilde P$ commute with group actions
    - group average is one solution : centralizer. 
    - is it the only method ?
  - alternative 
    - construct a G-invariant scaler product, as noted before
  - explain the use of the 3 conditions : finite dim rep, finite group, complex filed 
    - finite dim rep : assure that the decomposition is finite
    - complex field is not necessary here, chr $\not \mid |G|$ suffices. but useful in Schur's lemma

## Schur's lemma 

- Schur's lemma 

  - let $(\rho_V, V)$ 和 $(\rho_W, W)$ ，be two **irreducible** representations over **complex** field,  given $\phi: V \to W$ a G-linear mapping, we can determine its form using the relation between the two irreps.
    - if $(V,\rho_V) \not\cong (W,\rho_W)$，then  $\phi = 0$
    - if $(V,\rho_V) = (W,\rho_W)$，then  $\phi = \lambda I$ where $\lambda \in \mathbb{C}$ is the only eigen value of $\phi$
  - corollary : if $(V,\rho_V),(W,\rho_W)$ are two irreducible representations, then  $\dim\text{Hom}_G(V, W) = 0$ if the two representations are not equivalent, else $1$
    - that is, two intertwining operators differ only by a scalar if $V \cong W$. In particular, if $V = W$ then $I$ is intertwinning, so all intertwinning map is $\lambda I$. 
  - proof : use the ker and im properties of intertwinning operator and definition of irreducibility 
  - application :
    - determine a linear map (to be $0$ or $\lambda I$) by proving that it is an intertwinning map between two irreps that we may construct.  

- Corollaries / Applications of Schur's lemma 

  - **irreps of abelian group over complex field has dimension 1** 
    - what's the minimum condition needed to prove the dimension 1 property ? can we generalize to non-abelian group ? 
    - equivalent proposition : representation matrices of finite abelian group over complex field can be simultaneouly diagonalised into diagonal matrix. 
    - alternative : since the group is finite (suppose of order $n$), all representation matrix $D(g)$ satisfies $(D(g))^n = I$, the polynomial $X^n = 1$ has $n$ distinct roots over complex field (scindé sur $\mathbb{C}$), so the minimal polynomial dividing it also splits over $\mathbb{C}$, hence all $D(g)$ can be diagonalised. And by the commutativity the eigenvalues and eigenvectors are shared between all matrices.  
  - let $Z(G) = \{z \in G \mid zg = gz, \forall g \in G\}$ be the center of the group G, and $(\rho, V)$ an irrep of $G$ over complex field, prove that $\forall z \in Z(G), \exists \lambda , \, s.t. \rho(z) = \lambda I$ 
    - if $\rho$ is a irrep for the bigger group, is it an irrep for the abelian subgroup ? restriction ? 
  - prove that for a character table, nb of lines (nb of inequivalent irreps) = nb of columns (nb of conjugacy classes)
  - let $G$ be a finite group, $W$ an irrep, $V$ a representation, then $\text{Hom}_G(W,V) = \langle \chi_W , \chi_V \rangle =$ multiplicity of $W$ in $V$. 
    - By Schur's lemma and Maschke's theorem  

- Construct an intertwinning operator from a linear map

  - given two representations $(V,\rho_V)$ and  $(W,\rho_W)$ and a linear map $X:V\to W$ not necessarily G-linear, we can construct a G-linear map (intertwinning operator) from it by using averaging skill : $\tilde{X} = \frac{1}{|G|} \sum_{h \in G}\rho_W(h)X\rho_V(h^{-1})$

  - if $\rho_V, \rho_W$ are **irreps**, then by Schur's lemma we know that $\tilde X$ can only be $0$ or $\lambda I$

  - rewrite in matrix form : $\tilde{X}_{ij} = \frac{1}{|G|} \sum_{h \in G} \sum_{p,q} D^W(h)_{ip} X_{pq} D^V(h^{-1})_{qj}$, let $(X)_{ij} = \delta_{ir}\delta_{jc}$, 

    - if $V \not\cong W$ , then $\forall i,j,r,c, \, \frac{1}{|G|} \sum_{h \in G} D^W(h)_{i,r} D^V(h^{-1})_{c,j} = 0$

    - if $V = W$, 

      - then  $(\tilde X)_{ij} = \frac{1}{|G|}\sum_{h \in G}\sum_{p,q}D^W(h)_{i,p}X_{p,q}D^V(h^{-1})_{q,j} = \frac{1}{|G|}\sum_{h\in G}D^W(h)_{i,r}D^V(h^{-1})_{c,j}$
      - at the same time, since $V = W$, we have for all $X$, $\tilde X = \lambda_X I $, so $(\tilde X)_{ij} = \lambda_X\delta_{i,j}$ and by **taking the trace** at both sides we have that if $(X)_{ij} = \delta_{ir}\delta_{jc}$ then $\lambda_X = \delta_{rc}/d_V$

      - so $\frac{1}{|G|}\sum_{h\in G}D(h)_{i,r}D(h^{-1})_{c,j} = \dfrac{\delta_{rc}\delta_{ij}}{d_V}$

    - <u>(prove this)</u> if $V \cong W$, $\frac{1}{|G|} \sum_{h \in G} D^W(h)_{ir} D^V(h^{-1})_{cj} = \dfrac{(T^{-1})_{cr}T_{ij}}{d_V}$  where $T:V\to W$ is any intertwinning operator. 

- Great orthogonality theorem (GOT) : In general, if $V,W$ are two **irreps**, then  $\forall r,c,i,j$, $\frac{1}{|G|} \sum_{h \in G} D^W(h)_{ir} D^V(h^{-1})_{cj} =  \delta^{WV} \dfrac{(T^{-1})_{cr}T_{ij}}{d_V}$

  - this theorem uses the fact that we can construct an intertwinning operator from **arbitary** linear map $X$ 
  - 
  - Corollary : let $r=i,c=j$ and take the sum over all $i,j$,  we get $\frac{1}{|G|} \sum_{h \in G} \tr\left(D^W(h)\right) \tr\left(D^V(h^{-1})\right) = \delta_{WV}$   (1 when $V \cong W$ else 0)

- Character of a group element $h$ is defined by the trace of its representation matrice $\chi(h) \coloneqq \tr(D(h))$ 

  - important properties of $\tr$ : $\tr(AB) = \tr(BA)$,  $\tr(A^T) = \tr(A)$.
  - characters determines the representation, that is 
  - $\rho_V \cong \rho_W \iff \chi_{\rho_V} = \chi_{\rho_W}$
    - $\implies $ is easy 
    - RHS implies $( \chi_V \mid \chi_\mu) = ( \chi_W \mid \chi_\mu)$ that is, each inequivalent irrep occurs the same times in the decompositions of $V$ and $W$ is equal so $V \cong W$ 
  - $\chi(h^{-1}) = \chi(h)^*$   (* denote complex conjugate)
    - for finite group, we can always construct a scalar product (using unitary skill, as noted before) such that all group action is unitary. for unitary matrix $D(h)$, we have $D(h^{-1}) = [D(h)]^{-1} = D(h)^\dagger$
    - Corollary : $\frac{1}{|G|} \sum_{h \in G} \chi_W(h) \chi_V(h)^* = \delta_{WV}$
  - $\dim(V) = \chi(e)$
  - character $\chi : G\to \mathbb{C}$ is a class fonction : group elements in the same conjugacy class has the same character
  - 

- First orthogonality of character (FOC)

  - Define inner product for **complex value functions** defined on finite group $G$ : $\langle \phi, \psi \rangle = \frac{1}{|G|} \sum_{h \in G} \phi(h) \psi(h)^*$
    - class functions like $\chi$ are also complex value functions, but be careful in the application, since $h$ runs in $G$ and not only in the representative set.
  - For any **irreps** $\mu,\nu$ , we have the character orthogonality $\langle \chi^\mu, \chi^\nu \rangle = \delta_{\mu\nu}$  where $\langle \chi^\mu, \chi^\nu\rangle  \coloneqq \frac{1}{|G|} \sum_{h \in G} \chi^\mu(h)\chi^\nu(h)^*$

- Corollaries of first orthogonality of character

  - $V \cong \bigoplus_\mu a_\mu V^\mu \implies \chi^V(h) = \sum_\mu a_\mu \chi^\mu(h)$   (Maschke's theorem + linearity of $\tr$ ), 
  - $\langle \chi^V(h),\chi^\mu(h)\rangle = a_\mu$  
    - if the two irresps are isomorphic i.e. $\mu \cong \nu$, then their multiplicities are the same $a_\mu = a_\nu$. The inverse obviously not true
  - Maschke's decomposition is unique up to isomorphism : $V \cong \bigoplus_\mu a_\mu V^\mu$ where $V^\mu$ represents its isomorphic **class**, the multiplicity $a_\mu$ for each class $\mu$ of irreducible representations is unique 
  - $\langle \chi^V(h),\chi^V(h)\rangle = \sum_\mu |a_\mu|^2$ 
    - allows to calculate the possible multiplicity of irreps
  - $V$ is irrep iff $\frac{1}{|G|} \sum_{h \in G} |\chi^V(h)|^2 = 1$

- Regular representation 

  - consider the vector space $V$ spaned by the group elements $\{e_g\}_{g\in G}$, the representation $R$ of group $G$ is defined by left multiplication ：$\rho^R(g) e_h = e_{gh}$。
  - $\chi^R(h) = n$ if $h = e$ else $0$
  - for any irrep $\mu$, its multiplicity in the regrep equals its degree, i.e. $a_\mu = \dim(V_\mu)$  (also say that the irrep $\mu$ appears $a_\mu$ times in the regular representation $R$)
    - corollary : using $\langle \chi^V(h),\chi^\mu(h)\rangle = a_\mu = \dim(V^\mu) \geq 1$, we also say that all irrep is contained (isomorphic to a sub-irrep) in the regular representation and appears its dimension times.
  -   $\sum_\mu d_\mu^2 = \dim V = |G|$ （The sum of squares of the degrees of the **inequivalent** irreps equals the group order. here the multiplicity is not involved）
    - allows us to calculate possible dimensions of irreps : for example for $S_3$, $1^2 + 1^2 + 2^2 = 6$ so the irreps can only have dimension $1,2$

- Character table 

  - line : inequivalent irreps $\mu_i$
  - column : conjugacy classes $S_j \subset G$
  - entries : character of the irrep of the conjugacy class i.e. $\chi^{\mu_i}(S_j)$
  - properties : 
    - **nb of lines = nb of columns** **proof**
      - prove that the characters of irreps must span the whole class function space (otherwise there will be a class function $f$ orthogonal to the $n$ characters of irreps ).
      - key motivation : given an irrep, how do we determine a linear map? does $f$ meets the condition ? 
    - column vectors are orthogonal under ?  m
    - line vectores are orthogonal under ?
  - calculation 
    - key tool : character inner product $\langle \phi, \psi \rangle = \frac{1}{|G|} \sum_{h \in G} \phi(h) \psi(h)^*$ 
      -  $\displaystyle \langle \chi_\mu, \chi_\nu \rangle = \frac{1}{|G|} \sum_{\text{class }C_i} \text{card}(C_i) \cdot \chi_\mu(C_i) \chi_\nu(C_i)^*$    
    - determine the nb of rows (and columns) by counting the nb of conjugacy classes
    - determine the dims of the irreps i.e. the first column : the first column corresponds to the characters of different irreps of the conjugacy class $\{ e\}$. Since $\forall \text{irrep }\mu , \chi_\mu(e) = d_\mu$, there is $\sum_\mu (\chi_\mu(e))^2\ = \sum_\mu d_\mu^2 = |G|$ i.e. 
      - the square sum of the first column equals $|G|$
    - the first row corresponds to the characters of the trivial representation of different class. 
      - the first row is all one
    - each pair $(i,j)$ of rows corresponds to the characters of a pair of inequivalent irreps $(\rho_i, \rho_j)$, hence their character functions satisfy the orthogonality $\langle \chi_i,\chi_j\rangle = \frac{1}{|G|}\sum_{g\in G}\chi_i(g)\chi_j(g)^* = 0$.
      - two different rows are orthogonal under the character inner product.
    - each row corresponds to an irrep, so $\langle \chi_i,\chi_i\rangle = \frac{1}{|G|}\sum_{g\in G}|\chi_i(g)|^2 = 1$. 
      - so each row has norm 1 under the character product. 

- Find the explicite irreducible subrepresentation (irreducible subspace of a representation, not an irreducible representation) for a concret representation 

  - if the group is finite abelian
    - then all representation matrices can be simultaneously diagonalised (noted in the Schur's lemma exercices), il suffices to determine the eigenspaces.
  - if the group is not abelian
    - it suffices to find a projection for each invariant subspace 
    - use group property to determine the nb of conjugacy groups -> use orthogonality equalities to solve the character table -> use the projection, its image is the explicite subspace
    - to find the explicite subrepresentation of $\rho$
    - Projection operator : $P^\mu = \frac{d_\mu}{|G|} \sum_{g \in G} \overline{\chi^\mu(g)} \rho(g)$
      - let $V = \bigoplus_i V_i$ be the explicit decomposition into irreducible subrepresentation. verify that $P^\mu$ defined above is the projection onto the $V_\mu$ , i.e. vectors in other spaces are annihilated.
  - other methods like Young table, if the character table of the group hasn't been determined yet 

- Synthese : criterion of irreducible representation 

  - by def : invariant subspace is trivial 
  - by the sum of the squares of the modules of characters: $\frac{1}{|G|} \sum_{h \in G} |\chi^V(h)|^2 = 1$

## example : $S_3$

- calculation of the character table 

  - $S_3$ has 3 conjugacy class : the class of cycles of length resp. 1,2,3. (cycles are conjugate iff they are of the same length)

    - hence $S_3$ has 3 irreducible representations (trivial rep $V_{I}$, sign rep $V_{\text{sgn}}$, 2 dim reps $V_{2d}$)

  - first column : 1,1,2 because $6 = 1^2+ 1^2 + 2^2$

  - first row : 1,1,1

  - |          $\chi_\rho(C)$          | $\{e\}$ | $\{(12),(23),(13)\}$ | $\{(123),(132)\}$ |
  | :------------------------------: | :-----: | :------------------: | :---------------: |
    | $\rho_1$  trivial representation |    1    |          1           |         1         |
    |   $\rho_2$ sign representation   |    1    |        x = -1        |       y = 1       |
    | $\rho_3$ triangle representation |    2    |        z = 0         |      w = -1       |
  
  - second row : 

    - by the orthogonality between $\rho_1$ and $\rho_2$ : $1+3x+2y=0$
  - by the fact that if $g$ is a transposition then $g^2 = e$ , since $\rho_2$ is of dimension 1, so $\rho_2(g)^2 = I_1 = 1$ and  $\rho_2(g) = \pm 1$
    - verify that $\rho_2(g)=x=-1$  and $y=1$ satisfy both condition
  
  - third row: 

    - by the orthogonalities with the first and second rows : $2+3z+2w = 0$ and $2-3z+2w = 0$ 
  - solve the equation and obtain $z = 0, w = -1$
  
  - the regular representation of $S_3$ is reducible into $W_1,W_2,W_3,W_4$, where $W_1 \cong V_I, W_2 \cong V_{\text{sgn}}, W_3 \cong W_4 \cong V_{2d}$, resp. of dimension 1,1,2, which also verifies the equality of regrep : $\sum_\mu d_\mu^2 = |G| = 6$

- calculation of the irreducible subrepresentations of regular representation 

  - from the character table we know that $S_3$ has 3 irreps.
  - regular representation contains all irreps so there should also be 3 invariant subspace. 
  - let $B = \{e_e,e_{(12)},e_{(13)},e_{(23)},e_{(123)},e_{(132)}\}$ be the basis of the representation space $V$

## Hom 

- if $V_1 \not\cong V_2$, then $\text{Hom}_G(W, V_1 \oplus V_2) \cong \text{Hom}_G(W, V_1) \oplus \text{Hom}_G(W, V_2)$
- $\dim\text{Hom}_G(W,V) = \langle \chi_W, \chi_V \rangle_G$



- on the induced representation and frobinius rule
- basic version : let $H \le G$ , $(W,\theta)$ a subrepresentation of the restriction $\rho_H$, hence $W$ is an invariant subspace of $\rho$ and $\rho_H$. We say that $(V,\rho)$ is induced by $(W,\theta)$ if $V = \bigoplus_{s \in R}{ \rho_s W}$  where $R$ is the representatives of cosets in $G/H$ 
- properties 
  - regrep can be induced from its irreducible subrep 
  - if $\rho_1,\rho_2$ are resp. induced by $\theta_1,\theta_2$ ,then $\rho_1 \oplus \rho_2$ is induced by $\theta_1 \oplus \theta_2$ 
    - def : $\rho_1 \oplus \rho_2 : G\to GL(W_1 \oplus W_2) \quad (\rho_1 \oplus \rho_2)(s)(w_1 + w_2) = \rho_1(s)w_1 + \rho_2(s)w_2$
  - if $(W,\theta)$ induces $(V,\rho)$ and $W_1 \le W$ stable under $\theta$, then $V_1 = \sum_{s\in R}\rho(s)W_1$ stable under $\rho$ 
    - if $W$ reducible, then $V$ induced by $W$ is reducible. If we want to induce from $(W,\theta)$, we can find the induced representations of the irreps of $\theta$ at the subgroup level, then take the sum.
  - $$\text{Ind}_H^G(\theta) \otimes \rho' \cong \text{Ind}_H^G(\theta \otimes \text{Res}_H^G(\rho'))$$
- given a representation $(W,\theta)$ of $H \le G$,   $\operatorname{Ind}_H^G(\theta) $ exists and is unique up to an isomorphism
  - existence : 
  - how do we construct the first induced representation from a given representation ? 
  - what's the motivation of lemma 1 ? 

## Module & group algebra 

### submodule

one sometimes say that a $C[H]$-module $W$ is a submodule of a $C[G]$-module $V$, in fact, this means that $W$ is a submodule when $V$ is considered as a $C[H]$-module.

### group algebra 

- we consider a group element as a base vector (as in regrep) and define group algebra $\mathbb{C}[G]$ : 
  - vector space : $v \in \mathbb{C}[G] \iff v = \sum_{g \in G} c_g g$ where $c_g \in \mathbb{C}$
  - ring : $(c_1 g_1)(c_2 g_2) = (c_1 c_2) (g_1 g_2)$
- Notes : 
  - group-algebra $\mathbb{C}[G]$ vs group-module  $\mathbb{C}[G]$-$V$ : group algebra is the vector space with the group elements being the base vectors. Group module is a module over a group algebra (a ring, with scaler multiplication)
- if $H \le G$ ,then  $\mathbb{C}[H]$ is a subalgebra of $\mathbb{C}[G]$
- In view of the definition of group algebra and tensor product, we can translate the language of representation into that of group module : 
  - the group $H$ has a representation on $W$ : $W$ is a left $\mathbb{C}[H]$-module, i.e. $(\sum_{h\in H}c_h h) \cdot w = \sum_{h\in H}c_h\rho_H(h)w \in W$
  - $\mathbb{C}[H]$ is a left $\mathbb{C}[G]$-module and a right $\mathbb{C}[H]$-module i.e. $\forall v \in V =\mathbb{C}[H], (\sum c_ig_i)\cdot v \in V, v\cdot (\sum d_jh_j) \in V$
  - and we can define the induction as : $$\text{Ind}_H^G W \coloneqq \mathbb{C}[G] \otimes_{\mathbb{C}[H]} W$$
- 

## tensor product 

- Def : it's kind of a reformulation for the product space of two vector spaces, i.e. the image of a bilinear function $\phi: U \times V \to W$

  - let $R$ be a ring, in this way, we want the product $\phi$ to be balanced and $R$-bilinear (not necessarily symmetric, since $\lambda \phi(u,v)$ is not yet defined)
    - $\phi(\lambda u, v) = \phi(u, \lambda v)$    
    - $\phi(u_1+u_2, v) = \phi(u_1, \lambda v)+\phi(u_2, \lambda v)$
    - $\phi(u, v_1+v_2) = \phi(u, \lambda v_1)+\phi(u, \lambda v_2)$,
  - that explains why we define $M \otimes_R N \coloneqq (M\times N) / K$ and $\phi : M\times N \to (M\times N)/K$
  - where $K$ is generated by the set of elements of the form : 
    - $(m_1 + m_2, n) - (m_1, n) - (m_2, n)$
    - $(m, n_1 + n_2) - (m, n_1) - (m, n_2)$
    - $(mr, n) - (m, rn)$

- a function is balanced if $f(\lambda u, v) = f(u, \lambda v)$. note that $W$ might not be a $R$-module, in which case $\lambda \phi(u,v)$ is not defined, and bilinearity can't be used to imply balance

- Properties 

  - the **pure tensors** $m\otimes n \coloneqq (m,n)+K$ i.e. is the equivalence class of $(m,n)$ in $(M\otimes N)/K$
  - $\forall r\in R, r(m\otimes n ) \coloneqq mr \otimes n = m \otimes rn$
  - associativity : $ p \otimes (q \otimes r) = (p\otimes q) \otimes r $ 

- **Universal Property** : let $P$ be a vector space, for all **balanced** bilinear function $f: M \times N \to P$，there exists a **unique** linear map $\tilde{f}: M \otimes_R N \to P$，such that for all **pure tensors**, there is ：$f(m, n) = \tilde{f}(m \otimes n)$ 

  - In this way, we associate a bilinear function to a linear one. 

  - Proof : let $f$ be a balanced bilinear function. Define $\Phi((m, n)) = f(m, n)$, so $K \subseteq \ker(\Phi)$. By the universal property of quotient space, there exists a **unique** linear function $\tilde{f}: F/K \to P$  such that $\tilde f((m,n)+K) \coloneqq \Phi((m,n))$ where $F/K = M\otimes_R N$
    - $\tilde f$ is well defined, i.e. independent of the chosen representative because $x \equiv y \implies x-y\in K \implies f(y)-f(x) = \Phi(y-x) = 0 $. 

- examples 

  -  let $V,W$ be resp. spanned by $\{e_1, e_2\}$ and $\{f_1, f_2\}$, $v \otimes w$ is called a pure tensor, for all $v\in V, w \in W$. show that  $z = e_1 \otimes f_1 + e_2 \otimes f_2$ is not a pure tensor, hence not all tensors are pure tensors. 

  -  consider $U = \mathbb{Z}_2 \otimes_{\mathbb{Z}} \mathbb{Z}_3$, show that $\mathbb{Z}_2 \otimes_{\mathbb{Z}} \mathbb{Z}_3 = \{0\}$ (as a module over $\mathbb{Z}$)

  -  show that $\mathbb{Z}_4 \otimes_{\mathbb{Z}} \mathbb{Z}_6 \cong \mathbb{Z}_{2}$ and $U = \mathbb{Z}_6 \otimes_{\mathbb{Z}_6} \mathbb{Z}_6$ ? 

  -  show that $$R \otimes_R R \cong R$$ for commutative ring $R$ (this reflects the interest of universal definition of tensor product.)

## constructions of induced representation 

### by cosets（intuitional）

- let $H \le G$ and $(W,\rho_H)$ be a representation of the group $H$ on a vector space $W$, let $R = \{g_1,g_2,\cdots,g_k\}, k=[G:H]$ be a representative set of $G/H$. we can define a representation $\text{Ind}_H^G W = (V,\rho)$ of $G$ using $\rho_H$ : 

  - $\displaystyle V \coloneqq \bigoplus_{g_i \in R}g_iW $     
  - $\forall g_0 \in G, \forall v = g_iw \in g_iW, g_0g_i = g_jh \implies \rho(g_0)v = g_j\cdot \rho_H(h)w$

- Notes

  - we haven't defined any multiplication or representation on $V$, so what does it mean by $g_iW$ ? it's not even a coset since $g_i$ and $W$ are of different natures.  

    -  $g_iW$ carries no operational significance, only serves as a independent vector space, $g_i$ can be considered as a tag. Since the cardinal of $R$ is $[G:H]$, we know that the dimension of $V$ is $[G:H]\times \dim W$ 

    - in fact, $g_iW$ is exactly what we mean by $g_i \otimes W$ in $\text{Ind}_H^G W \coloneqq \mathbb{C}[G] \otimes_{\mathbb{C}[H]} W$

  - $\text{Ind}_H^G W = (V,\rho)$ doesn't rely on the $R$ chosen, we should verify that the representation obtained are isomorphic under different $R$ chosen. that is, induced representations $(V_R, \rho_R)$ and $(V_{R'}, \rho_{R'})$ based on any two representative sets $R$ and $R'$ are isomorphic

### by tensor product 

- $\text{Ind}_H^G W \coloneqq \mathbb{C}[G] \otimes_{\mathbb{C}[H]} W$
  - the construction doesn't rely on $R$
- the dimension of induced representation is $[G:H]\dim W$, this can be obtained using the condition $(sh) \otimes w = s \otimes (hw)$ , that is, $C[G]$ is a $C[H]$-right module with the representative system $R$ as a basis 
- $$\rho(g)x_i\otimes w = g \cdot (x_i \otimes w) = x_j \otimes (\pi(h)w)$$
- this corresponds to $g_0x_i = x_jh \implies g_0 x_iw = x_j(hw)$ where $x_i,x_j$ are representatives in the coset construction. 
- $C[G]$-homomorphism (module language) corresponds to the intertwining operator (representation language)
- prove that $\mathbb{C}[G] \otimes_{\mathbb{C}[H]} W$ is effectively an induced representation, i.e. $W' = \mathbb{C}[G] \otimes_{\mathbb{C}[H]} W \cong \bigoplus_{s\in R}s\cdot W = V$ as $C[G]$-modules
  - let $i:W\to V$ be the injection of $W$ in $V$
  - we can extend $i$ to a $C[G]$ homomorphism $i'$ , i.e.  $i'(1\otimes w) = w$ and $i'(g\cdot 1\otimes w ) = i'(g \otimes w ) = g\cdot i'(1 \otimes w) = g\cdot w$
  - this already contains the surjectivity.
  - so we obtain a $C[G]$-homomorphism $i'(g\otimes w) = g\cdot w$ 
  - now it remains to prove that $i'$ is injective.
  - if $\sum_{s\in R} s \cdot w_i = 0_V $, then $s\cdot w_i = 0_V$ and $w_i = 0_V$ (since $s\cdot w_i$ means the action of $s$ on $w_i$, which is invertible, by the definition of $C[G]$-module)
  - at the same time we have  $\sum_{s\in R}s \cdot w_i = i'(\sum_{s\in R}s \otimes w_i)$, hence $i'(\cdot ) = 0_V \implies \cdot = 0_{\otimes}$, so $i'$ is injective 


### by  $\text{Hom}$ 

- let $H \le G$ and $(W,\rho_H)$ be a representation of the group $H$ on a vector space $W$, we can define a representation $(V,\rho)$ of $G$: 
  - $V \coloneqq \{ f: G\to W \mid \forall h \in H, \forall g\in G, \,f(hg) = \rho_H(h)f(g)\}$     that is, V is the space of $H$-equivariant functions defined on $G$
  - $\forall g_0 \in G, [\rho(g_0)f](g) = f(gg_0)$
- Notes 
  - $\dim V = [G:H] \times \dim W$, since the values of $f$ on two different group elements in the same coset are uniquely determined by each other via $\rho_H$
  - $H$ is a subgroup of $G$, but $W$ not a subspace of $V$ 
  - we can also define a group homomorphism based on the left translation : $\forall g_0 \in G, [\rho(g_0)f](g) = f(g_0^{-1}g)$, but this can't be the representation on the equivariant function space $V$, since it breaks the equivariance : let $F = g_0 \cdot f$,  $F(hx) = f(g_0^{-1}hx) = \rho_H(h)f(g_0^{-1}x) = F\rho_H(h)F(x)$, the second "=" only holds for all $h\in H$ when $g_0^{-1}h = hg_0^{-1}$ i.e. $g_0$ commutes with $H$. 

### tensor-Hom adjunction 

- for all $(R, S)$-double module $M$，left module $X$ and $Y$，there exists a natural isomorphism ：$$\text{Hom}_R(M \otimes_S X, Y) \cong \text{Hom}_S(X, \text{Hom}_R(M, Y))$$
  - this explains why $\text{Ind}$ is the right-adjunction of $\text{Res}$ when using $\text{Hom}$ to construct the induction whereas it's the left-adjunction when using tensor product.  

## Frobenius reciprocity 

- use the tensor product construction of induced representation, show that : $$E = \text{Hom}_G(\text{Ind}_H^G V,W) \cong \text{Hom}_H(V,\text{Res}_H^G W) = F$$
- use the equivariant function space construction of induced representation, show that : $$E = \text{Hom}_G(W, \text{Ind}_H^G V) \cong \text{Hom}_H(\text{Res}_H^G W, V) = F$$
  - two objects : show that given $\phi : W \to Ind_H^GV$, we can construct $\psi : W \to V$ from it.
  - show that for each $\psi$, we can find its $\phi$ 
- Proof : 
  - there are too many nested notations, let's boldly simplify them to get an intuition
  - $E : W \xrightarrow[G]{\phi} (G \xrightarrow[H]{\phi(w)} V) $
  - $F : W \xrightarrow[H]{\psi} V $
  - to obtain a function that goes from $W$ to $V$, we can follow the arrows in $E$, that is, evaluate twice. 
  - $\phi(\cdot)e : W \to V$, and we can verify that it does commute with actions of $H$, hence we can define $\psi(\cdot) = \phi(\cdot)e$ 
  - now, suppose that the bijectivity exists, that is, for any $\psi \in F$, there exists $\phi \in E$  such that $\psi(w) = \phi(w)e$, we want to represent $\phi(w)g$ with $\psi(\cdot)$, to see what the result might look like. 
  - $\phi(w)g = \phi(w)eg = [g \cdot\phi(w)](e) = \phi(gw)e = \psi(gw)$
  - so , if a $\psi \in F$ has preimage, then it's uniquely determined by $\psi(gw)$
  - it remains to show that, for each $\psi \in F$,  $\psi(gw)$  is its preimage, that is, $\phi(w)g =  \psi(gw) \in E$
  - so we should verify that 1. $\phi(w) : G \xrightarrow[H]{} V$ and 2. $\phi : W \xrightarrow[H]{} Ind_H^GV$, which can be done only using the property of $\psi$. 
  - 1. $\forall g\in G,\forall h\in H, \forall w\in W, \quad\phi(w)(hg) = \psi(hgw) = h\psi(gw) = h\phi(w)g$
  - 2. $[\phi(g_0 w)](g) = \psi(g g_0 w) = \phi(w)(g g_0) = [g_0 \cdot \phi(w)](g)$
  - 
- a question is, after the first step, $\psi(\cdot) = \phi(\cdot)e$, that means only the local information of $\phi(\cdot)$ at the point $e$ is conserved in $\psi(\cdot)$ , how is it possible to recover $\phi(\cdot)$ from  $\psi(\cdot)$ , its evaluation at $e$? 
  - from the proof, we know that's because  $\phi(w)g = \psi(gw) = \phi(gw)e $, so as long as we know the $\phi(w)e$ for all $w \in W$, then $\phi$ is determined.
- Corollary : $(W \mid \text{Ind}_H^G V )_G = (\text{Res}_H^G W \mid V )_H$
  -  Let  $V$  be  an  irreducible  representation  of $H$  and  $W$  an 
    irreducible representation of $G$.  Then  the number of times that $V$ occurs in 
    $\text{Res}(W)$ is equal to the number of times that $V$ occurs in $\text{Ind}(W)$

- Categorical perspective
  - $\text{Res}$ : forgetful functor 
  - $\text{Ind}$ : free functor 
  - in category theory, we always say that induction is the left adjunction of restriction (induction at left = restriction at right), that is $\text{Hom}_G(\text{Ind}_H^G V, W) \cong \text{Hom}_H(V,\text{Res}_H^G W)$
  - but here what we have is $\text{Hom}_G(W, \text{Ind}_H^G V) \cong \text{Hom}_H(\text{Res}_H^G W, V) = F$  
  - in fact, since this isomorphism is obtained based on the function space construction. It should be written as : $\text{Hom}_G(W, \text{Coind}_H^G V) \cong \text{Hom}_H(\text{Res}_H^G W, V)$  ($\text{Coind}$ is the right adjunction of $\text{Res}$)
  - If the use the tensor product construction for the induced representation, then we will have instead: $\text{Ind}$ is the left adjunction of $\text{Res}$ ：$\text{Hom}_G(\text{Ind}_H^G W, V) \cong \text{Hom}_H(W, \text{Res}_H^G V)$
  - in conclusion, for **finite group** induction and coinduction is naturally isomorphic, i.e.$\text{Ind}_H^G V \cong \text{Coind}_H^G V$
  - related : $$\text{Hom}(X \otimes Y, Z) \cong \text{Hom}(X, \text{Hom}(Y, Z))$$
  - 

### example : $D_4$

- $D_4 = \{e,r,r^2,r^3, \quad s, sr, sr^2, sr^3 \}$
- $r$ is the rotation of 90 degree, $s$ is the reflection about the central axis
- properties : order = 8, 4 rotations, 4 reflections
- $r^4 = s^2 = e$
- $rs = sr^{-1}$   i.e. $rs = sr^3$
- Let $G = D_4$, and let $H = \{e, s\}$ be a subgroup of order 2, where $s$ is a reflection. Consider the sign representation $\rho_{\text{sgn}}$ of $H$ (where $\chi(e)=1, \chi(s)=-1$). Using Frobenius Reciprocity, calculate the inner product of the induced representation $\text{Ind}_H^G(\rho_{\text{sgn}})$ with itself. Based on this result, determine whether this 4-dimensional induced representation is an irreducible representation of $D_4$.
  - the interest of using Frobenius reciprocity : $H$ is a small group and to calculate the character $\langle \rho_{\text{sgn}}, \text{Res}_H^G(\text{Ind}_H^G(\rho_{\text{sgn}})) \rangle_H$, we only need to calculate the product of characters for two element $e,s$. 
  - related : Mackey's double cosets decomposition 
- this time ,let $H = \{e, r^2, s, sr^2\}$ ( p.s. abelian, isomorphic to $V_4$) and define a $1$-dimensional representation $\rho$ for $H$ : $\rho(e) = 1, \rho(r^2) = 1, \rho(s) = -1, \rho(sr^2) = -1$. Let $V = Ind_H^G(\rho)$ be the induction space based on the coset direct sum construction. Target : determine the representation matrix of elements of $G$
  -  

### exercices

- Let $W$ be an arbitrary irrep of a finite group $G$, and let $H$ be a subgroup of $G$. Using Frobenius Reciprocity, prove that the multiplicity of $W$ in the permutation representation $\mathbb{C}[G/H]$ is exactly equal to the number of $H$-invariant vectors in $W$ (i.e., the multiplicity of the trivial representation of $H$ in the restriction $\text{Res}_H^G W$).
  - we have $\mathbb{C}[G/H] \cong \text{Ind}_H^G \mathbf{1}_H$

## topological group 

- def :group multiplication and inverse are continuous under the endowed topology 

## Haar mesure 

- Def (Borel Measure) : Let $G$ be a topological space, and let $\mathcal{B}(G)$ denote the Borel $\sigma$-algebra on $G$. A **Borel measure** on $G$ is a function $\mu : \mathcal{B}(G) \to [0, \infty]$ that is countably additive.
- Haar theorem : Let $G$ be a **compact** Hausdorff topological group. A **normalized Haar measure** $\mu$ on $G$ i.e. a regular Borel measure satisfying the following two properties exists and is a **unique** (up to a positive scalar) :
  - Right-Translation Invariance: For any **continuous** function $f: G \to \mathbb{C}$ and  $\forall s \in G$ : $\int_G f(ts) \, d\mu(t) = \int_G f(t) \, d\mu(t)$
  - Normalization : The total measure of the group $G$ is normalized to $1$: $$\int_G 1 \, d\mu(t) = \mu(G) = 1$$


- Notes

  - Every metric space is Hausdorff
  - regular Borel measure : 
  - from the two conditions we can deduce the left invariance : $\int_G f(st)dt = \int_G f(t)dt$   correponds to $\sum_{x \in G} f(gx) = \sum_{y \in G} f(y)$
    - Proof :  $\forall s \in G$ and Borel set $E$，there is $\nu(E) = \mu(sE) = \mu(E)$
    - since $G$ is a topological group, $x\mapsto sx$ is a homeomorphism so $sE$ is also a Borel set. 
    - this new mesure $\nu$ is right invariant and normalized as $\mu$, by the uniqueness of Haar mesure, the two mesures differ by a constant depending on $s$ (Module function): $$\mu_s(E) = \Delta(s) \mu(E)$$
    - by the arbitrary of $E$, $\mu(sG) = \mu(G)\ = \Delta(s) \mu(G) \implies \Delta(s) = 1 \implies \mu_s(E) = \mu(sE) = \mu(E)$, that is the left invariance. 

  - we can also deduce the inversion invariance : $\int_G f(t^{-1})dt = \int_G f(t)dt$, using the homeomorphism $x \mapsto x^{-1}$

  - the integral is finite on a compact subset, globally compact so the integral over the group is finite.

- Significance : 

  - generalize the conditions for the existence of translation invariant mesure to continuous operation (topology) groups (algebra).
  - define $$[u, v] = \int_G \langle gu, gv \rangle \, d\mu(g)$$, so that (Weyl) <u>any finite representation of compact Lie groups is equavalent to a unitary representation .</u>
  - Enables Fourrier analysis on groups : $\hat{f}(\chi) = \int_G f(g) \overline{\chi(g)} \, d\mu(g)$

- examples 

  - calculate characters 
  - Fourrier analysis on groups 
  - SO(3) group 

## linear representations of compact groups 

linear representation that is also continuous about group element. 

### $SU(2)$ special unitary group 

- $$SU(2) = \{ M \in M_2(\mathbb{C}) \mid M^\dagger M = I, \det(M) = 1 \}$$
- $$M = \begin{pmatrix} \alpha & \beta \\ -\bar{\beta} & \bar{\alpha} \end{pmatrix}$$ with $$|\alpha|^2 + |\beta|^2 = 1$$, span $\alpha$ and $\beta$, then we get $x_1^2 + x_2^2 + x_3^2 + x_4^2 = 1$ 
-  
- $SU(2)$ basic representation : matrix multiplication on  $\mathbb{C}^2$ 
- $\mathcal{R}^j$ : $SU(2)$ on homogenous polynomials of degree $n = 2j$ defined on $\mathbb{C}^2$ ,
  - $[\rho(U)f](z,w) = f(U^{-1}\matrix{z,w})$
  - the representation space is $\mathbb{C}[z,w]_{n+1}$, we can determine a basis $\phi_k(z,w) = z^kw^{n-k}$
- the completeness of irreps of $\mathcal{R}^j$ 
- applications in quantum physics 

## Double coset 

- The idea of double cosets comes from our purpose to decompose a $C[G]$-module (or an induction, i.e. $V = \bigoplus_{xH \in G/H}xW$, $W$ as a $C[H]$-module) into a **direct sum** of $C[K]$-modules, where $K \le G$. To do that, we just need to group the $H$-cosets that belong to the same orbit of $K$ (i.e., a double coset $KsH$), because the subspace spanned by each orbit is naturally stable under the action of $K$.
- let $K,H\le G$, $W$ a representation of $H$ and $V = \bigoplus_{s\in R}sW$ induced by $W$. 
- define for an element $s\in G$ the double coset : $KsH = \{ksh \mid k\in K \and h \in H\}$ and 
- $K\backslash G / H = \{KsH \mid s\in G\}$ the set of double cosets. 
- Example of $S_3$ : 
  - define $G = S_3 = \{e,(12),(13),(23),(123),(132)\}$
  - $K = \{e,(12)\}$
  - $H = \{e, (13)\}$
  - we have the following right-cosets $xH$ : 
    - $eH = \{e,(13)\}$ 
    - $(12)H = \{(12),(132)\}$
    - $(23)H = \{(23),(123)\}$
  - we have the following double cosets $KsH$ : 
    - $KeH = \{e,(12),(13),(132)\}$
    - $K(23)H = \{(23),(123)\}$
- Remarks 
  - for each coset $xH$, there is $xH \subset KxH$. two different cosets can be contained in one double coset, for example we have $eH,(12)H \subset KeH$. In fact, $KxH$ contains all cosets $xH$ deplaced by a $K$-left action, i.e. it's the orbit of $xH$ under $K$. 
  - $\forall x \in G, \quad |KxH| = n|H|$ 
    - $k_1xH \cap k_2xH \neq \empty \iff k_1xh_1 = k_2xh_2 \iff k_1xH = k_2xH$
  - $K\backslash G / H$ is a partition of $G$, each double coset in $K\backslash G / H$ is composed of several cosets $xH$ 
  - $\displaystyle V = \bigoplus_{xH \in G/H}xW$. In this formula, the objects we sum over are subspaces labeled by the cosets. For example, $V = eW \oplus (12)W \oplus (23)W$. 
  - We can first collect and sum over the labels $xH$ that constitute the double coset $KsH$. For instance, $eH$ and $(12)H$ constitute $KeH$ : $V = [eW \oplus (12)W] \oplus (23)W = V(e) \oplus (23)W$. 
  - Thus, $\displaystyle V = \bigoplus_{KsH \in K \backslash G / H} V(s)$ where $V(s) = \bigoplus_{xH \subset KsH} xW$
  - every $V(s)$ is stable under actions of $K$, i.e. $K$ permutes the vectors inside each $V(s)$, so $V(s)$ is a representation of $K$. 

### direct sum as induction

- lemma (orbit-stabilizer theorem, optional ) :  consider the action of the group $G$ over a set $X$ , let $x \in X$
  - Define the orbit of $x$ :  $G \cdot x = \{g \cdot x \mid g \in G\}$    which is a subset of $X$
  - Define the stabilizer of $x$: $\text{Stab}_G(x) = \{g \in G \mid g \cdot x = x\}$    which is a subgroup of $G$
  - then we have : there exists a bijection from image to coset $\phi : G\cdot x \to G/\text{Stab}_G(x)$  such that $g \cdot x \mapsto g \,\text{Stab}_G(x)$
  - corollary : $|\text{orb}_G(x)| = |G/\text{Stab}_G(x)|$
  - in what follows, $\{W_i\}_{I}$ is the set $X$, we can show that it's also the orbit of $W$. and the stabilizer of $W$ is $\text{Stab}_G(W) = \{g \in G \mid g \cdot W = W\} = H$. So from orbit-stabilizer theorem we know that $|G/H| = |I|$
- lemma (proposition 19) : let $W_i$ be vector spaces (**not** $C[G]$-modules), $V = \bigoplus_{i\in I} W_i$ be a $C[G]$-module, $G$ **permutes** $W_i$ **transitively**, and $H\le G$ is the **stabilizer** of $W = W_{i_0}$ for some certain $i_0$, then $V$ is a $C[G]$-module induced by the $C[H]$-module $W$ i.e. $V = \text{Ind}_H^G(W)$
  - Remarks : 
    - pay attention to **what kind of module $V$ is**
    - $W$ is not given as a module, but it's stable under the stabilizer $H$, which makes it a representation for $H$. At the same time, $H \le G$, so $\text{Ind}_H^G(W)$ is well defined. 
    - $G$ permutes $W_i$ **transitively** means ,$\forall i,j, \exists g\in G, gW_i = W_j$
    - this is a strong condition, which says that the set of $W_i$ is the orbit of a certain $W$
    - choose $W = W_{i_0}$, so  $\forall i \in I, \exists g_i\in G, W_i = g_iW$ and $V = \bigoplus_I g_iW$
    - $H$ is the stabilizer of $W$ means: $H = \{g\in G \mid gW = W\}$
  - proof : it suffices to show that $V = \bigoplus_{xH \in G/H}xW$. 
    - on the one hand, since $V = \bigoplus_I g_iW$ and $g_{i_0} = e$, $\forall i,j\in I, g_iW = g_jW \iff g_j^{-1}g_iW = W \iff g_j^{-1}g_i \in H$  (the last iff given by the fact that $H$ is the stabilizer of $W$), hence $V \subset \bigoplus_{s \in R}sW$ 
    - on the other hand, since $V$ is a $C[G]$-module, $\forall g\in G,gW \subset V$, so $ \bigoplus_{s \in R}sW \subset V$  
- Corollary : if $V$ is irreducible and we want to find the $H$ which induces $V$, then it suffices to verify that $G$ permutes $W_i$ among themselves, since the transitivity is automatic (for each orbit of $G$ in the set of $W_i$'s is stable under $G$ thus defines a subrepresentation of $G$, irrep so one orbit i.e. transitive)

### Mackey's subgroup theorem 

- the main purpose here is to study $\text{Res}_K \text{Ind}_H^G(W)$, i.e. the restriction of an induction .
- from the double coset decomposition we know that $V(s) = \bigoplus_{xH \subset KsH} xW$ (where $xH \subset KsH \implies x \in Ks$) is a **$C[K]$-module**. can we show that it's induced by a subset of $K$, using proposition 19 ? 
  - let $R'$ be the set such that $x\in R' \iff xH \subset KsH$, $\{W_x = xW\}_{x\in R'}$ and $V(s) = \bigoplus_{x \in R'}W_x$, it's clear that $K$ permutes $W_x$ transitively. 
    - $xH \subset KsH \iff x\in Ks$, so of course $K$ permutes $W_x$. it's transitive since $x,y\in Ks \implies x=k_1s, y=k_2s \implies k_2k_1^{-1}x=y \implies k_2k_1^{-1}W_x = W_y$ 
  - now consider the stabilizer of $sW$. Let $E$ be the stabilizer, then $esW = sW \iff s^{-1}esW = W \iff s^{-1}es \in H \iff e \in sHs^{-1}$, so $ sHs^{-1}\cap K = E \le K$ is the stabilizer of $sW$
  - by proposition 19, we know that $V(s) = \text{Ind}_E^K(W_s)$ is a $C[K]$-module. 
    - $W_s$ is stable under $E$, but what's the concrete representation of $E$ on $W_s$ ? 
    - let $\rho : H \to GL(W)$ be the representation of $H$ and $\rho^s : E \to GL(sW)$ be the representation of $E$. 
    - then $x = shs^{-1} \in E \implies x(sw) = shw = s(s^{-1}xs)w \implies \rho^s(x)sw = s\rho(s^{-1}xs)w$
  - hence $\text{Res}_K\displaystyle V = \bigoplus_{KsH \in K \backslash G / H} \text{Ind}_E^K(W_s) $  is a $C[K]$-module. 
  - $\text{Res}_K$ is there since initially $V$ is a $C[G]$-module. 
- Theorem : $\text{Res}_K \text{Ind}_H^G(W) = \bigoplus_{s \in K \backslash G / H} \text{Ind}_{sHs^{-1} \cap K}^K (W_s)$

### Irreducible induction (Mackey's irreducibility criterion)

- let $W$ be a $C[H]$-module, is $V = \text{Ind}_H^G W$ irreducible as a $C[G]$-module ? i.e. $\langle V, V \rangle_G = 1$ ? 
- by Frobenius, $\langle V, V \rangle_G = \langle \text{Ind}_H^G W, \text{Ind}_H^G W \rangle_G = \langle W, \text{Res}_H \text{Ind}_H^G W \rangle_H$
- take $K = H$ in the above theorem, we get $V(s) = \text{Ind}_{sHs^{-1} \cap H}^H (W_s)$
- $\text{Res}_H \text{Ind}_H^G(W) = \bigoplus_{s \in H \backslash G / H}V(s) =  \bigoplus_{s \in H \backslash G / H}\text{Ind}_{sHs^{-1} \cap H}^H (W_s)$ ?
- $s = e \implies sHs^{-1}\cap H = H \implies V(e) = \text{Ind}_{H}^H (W) = W$
- $\displaystyle \langle V, V \rangle_G = \langle W, V(e) \rangle_H + \sum_{s \in H \backslash G / H, s \neq e} \langle W, V(s) \rangle_H = 1 + \sum_{s \in H \backslash G / H, s \neq e} \langle W, V(s) \rangle_H$
  - for readers : $s \in H \backslash G / H$ means $s$ belongs to the representative system. 
- Theorem : $V = \text{Ind}_H^G W$ is irreducible iff 
  - $W$ is irreducible 
  - $\forall s \in G- H, W$ and $V(s)$ are disjoint representations of $H$, i.e. $\langle W, V(s) \rangle_H = 0$
- in order to calculate $\langle W, V(s) \rangle_H$, we need to know the concrete representation of $V(s) = \text{Ind}_{sHs^{-1} \cap K}^K (sW)$
  - $W$ is a $C[H]$-module, let $\rho : H \to GL(W)$ be the representation of $H$
  - let $H_s = sHs^{-1}\cap K, \quad \rho^s : H_s \to GL(sW)$
  - from the proof of Mackey's subgroup theorem ,we know that the representation on $H_s$ is $\rho^s(x)sw = s\rho(s^{-1}xs)w$
- example : 
  - let $G = S_3 = \{e,r,r^2,s,sr,sr^2\}$, $H = \{e,r,r^2\} \triangleleft G$ and define representation of $H$ as $\rho(r) = \omega \coloneqq e^{i\frac{2\pi}{3}}$ , $W = \mathbb{C}$
  - if $V = \text{Ind}_H^G(W)$ irreducible ? 
  - $H \backslash G / H = \{H, HsH\} = \{H, sH\}$ , the representative system $R = \{e,s\}$
  - apply Mackey's irreducibility criterion,
  - $\displaystyle \langle V, V \rangle_G = \langle W, V(e) \rangle_H + \sum_{s \in H \backslash G / H, s \neq e} \langle W, V(s) \rangle_H = 1 + \langle W, V(s) \rangle_H$
  - $\langle W, V(s) \rangle_H = \frac{1}{|H|}\sum_{h \in H}\chi(\rho(h))\overline{\chi(\rho(s^{-1}hs))} = \frac13[\chi(\rho(e))\overline{\chi(\rho(e))} + \chi(\rho(r))\overline{\chi(\rho(s^{-1}rs))}] + \chi(\rho(r^2))\overline{\chi(\rho(s^{-1}r^2s))}$
  - we can also use the properties : $s^{-1}rs = r^2$, $s^{-1}r^2s = r$, $r^2 = r^{-1}$ , $\overline{\chi(\rho(s))} = \chi(\rho(s^{-1}))$
  - so $\langle W, V(s) \rangle_H = \frac13(1+w^2+w) = 0$  so $V$ is irreducible ! 

## semi direct product $SE(3) = \mathbb{R}^3 \rtimes SO(3)$

- Def : note that in the following definition, $H,K$ can be any two arbitrary groups. ![image-20260608202041021](C:\Users\T480s\AppData\Roaming\Typora\typora-user-images\image-20260608202041021.png)
  - In this definition, $H$ doesn't need to be a normal subgroup of $G$, BUT under this definition, $\tilde H = {(h,1)}$ becomes consequently a normal subgroup of $G$.
  - the point is, such non-trivial action $\phi$ doesn't always exist. when $H \triangleleft G$, we can define the automorphism $\phi_k$ for each $k \in K$ ($K$ can act on $H$) : given two groups $H,K \le G$ ,$HK$ is not always a subgroup. But if $H \triangleleft G$ or $k \triangleleft G$ then $hkh'k' = h\phi_k(h')kk' = (hkh'k^{-1})(kk') \in HK$ becomes a subgroup.
  - $\rtimes$ means the group on the right acting on the group on the left (which is an abelian normal subgroup)
  - if $G = H \rtimes K$, it means that $K$ acts on the normal subgroup $H$ of $G$. $H \rtimes $ points to $H$ just like $H \triangleleft G$. In fact $H$ is not a normal subgroup of $G$ but isomorphic to $\{(h,1)\}$ which is .
- if in addition, $H$ is normal and abelian, then each element in the semi-product group can be written uniquely as $hk$ with $h\in H, k \in K$
- for $$SE(3) = \mathbb{R}^3 \rtimes SO(3)$$ we can define the group multiplication $$(t_A, R_A) \circ (t_B, R_B) = (t_A + R_A t_B, R_A R_B)$$  
  - $R_A$ serves as the automorphism $\phi_k$ on $R^3$. 

## Mackey's little group method 

outline 

- find all the irreps of abelian normal subgroup : $\chi_p(t) = e^{i p \cdot t}$ i.e. character tagged by momentum vector $p$
  - First, consider the group $X = \text{Hom}(A, \mathbb{C}^*)$ formed by all one-dimensional characters of the normal abelian subgroup $A = \mathbb{R}^3$. The group $G$ (or $H$) acts on $X$ via the adjoint action, which generates orbits. By Pontryagin duality, all unitary characters of $\mathbb{R}^3$ constitute its dual group $\widehat{\mathbb{R}^3}$. We can parameterize these characters using a "momentum vector" $\mathbf{p} \in \mathbb{R}^3$: $\chi_{\mathbf{p}}(\mathbf{x}) = e^{i\mathbf{p} \cdot \mathbf{x}}$.
  - First, consider the group $X = \text{Hom}(A, \mathbb{C}^*)$ formed by 1-dim characters of the normal abelian subgroup $A = \mathbb{R}^3$.
    - Why do we consider the group formed by one-dimensional characters?
    - What is Pontryagin duality?
    - How do we find all the unitary characters of $\mathbb{R}^3$?
    - What is the dual group $\widehat{\mathbb{R}^3}$?
    - How should we understand the "momentum vector" here? What is its physical meaning?
    - What are the overall goal, motivation, and logic here?
      - Goal: To find all one-dimensional irreducible representations (irreps) of $A$?
- study the orbits $\{ Rp \mid R \in SO(3)\}$
- select a momentum vector $p_0$ on the sphere surface and find the operations that doesn't change it, this subgroup that maintains the character is called little group. For example, if $p_0$ is the vector on the $z$-axis, then $SO(2)$ is the little group because its action doesn't change the vector 
- use the induced representation techniques to extend the representation of $SO(2)$ to the entire bigger group $SE(3)$. 
- Proof of the effectiveness 

# todo

- ~~tensor product's properties~~
- categorical understandings 
- concrete examples or counter examples 
- prove Frobenius reciprocity using tensor product construction 
- prove that the induction by Hom space is effective and equivalent to that by tensor product 
- review the universal properties of tensor product and prove for cummutative ring $R$ , $R\otimes_R R \cong R$
- why we need to use Hom space as representation for topological / compact groups, instead of direct sum/ tensor product construction ?
- review that irrep is contained in regrep 
- prove that every finite abelian group is isomorphic to the direct product of its Sylow subgroups
- prove and find counter example for : H × K is abelian if and only if H and K are abelian, but semi direct product may not be the case 
- how to prove that a set of irreps is complete ? examples 

# resources 

- Jean-Pierre Serre Linear representation of finite groups 
- https://kconrad.math.uconn.edu/blurbs/grouptheory/semidirect-product.pdf