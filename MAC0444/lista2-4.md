### Q4
(a)
```
avof(Mul, Pess) :- 
    mae(Mul, X),
	(mae(X, Pess);pai(X,Pess)).
```
(b)
```
avom(Hom, Pess) :- 
    pai(Hom, X),
	(mae(X, Pess);pai(X,Pess)).
```
\(c\)
```
bisavom(Hom, Pess) :-
    pai(Hom, X),
    (avom(X, Pess);avof(X, Pess)).
```
(d)
```
primo_1(P1, P2) :-
    (avom(X, P1); avof(X, P1)),
    (avom(X, P2); avof(X, P2)),
    \+ (pai(Y, P1),
        pai(Y, P2)),
    \+ (mae(Y, P1),
        mae(Y, P2)).

```
(e)
```
genitor(X, Y) :-
    (pai(X, Y); mae(X, Y)).

antecedente(X, Y) :-
    (genitor(Z, X),
     genitor(Z, Y);
     antecedente(genitor(Z, X), genitor(Z, Y))).

primo(P1, P2) :-
    \+ (pai(Y, P1),
        pai(Y, P2)),
    \+ (mae(Y, P1),
        mae(Y, P2)),
    antecedente(genitor(Z, P1),
                genitor(Z, P2)).
```
(f)
```     
maior_de_idade(Pess) :-
    idade(Pess, X),
    X >= 18.
```
(g)
```
pessoas(Lista) :-
    findall(X,homem(X);mulher(X), Lista).
```
(h)
```
mais_velho(Pess) :-
    idade(Pess, X),
    \+ (idade(_, Y),
    Y > X).
```
(i)
```
lista_pessoas(Lista, Sexo) :-
    (Sexo = m ->  
    	forall(homem(X),
               insert(X, Lista));
    	lista_f(Lista)).
```
(j)
```
adequados(Hom, Mul) :-
    homem(Hom),
    mulher(Mul).
```






















