Mathematische Logik Notes

> © 2022 Mathematische Grundlagen der Informatik, RWTH Aachen

# reduzierte Formeln
Wir nennen Formeln, in denen die Symbole $\land, \rightarrow, \forall$ **nicht** vorkommen, reduziert.

Wir können diese Symbole durch die folgenden ersetzen:
1. $\phi \land \psi \equiv \neg(\neg \phi \lor \neg \psi)$
2. $\phi \rightarrow \psi \equiv \neg \phi \lor \psi$
3. $\forall x \phi \equiv \neg \exists x \neg \phi$


# Normalformen für Prädikatenlogik
## Negationsnormalform
Eine Formel ist in Negationsnormalform, wenn die Negation nur auf atomare Formeln angewendet wird.  
Diese neue Formel ist dann **logisch äquivalent** zur ursprünglichen Formel.

Vorgehensweise:
1. Negationsregeln anwenden

Beispiel: $\neg \exists x (Rxy \land \forall z(Sxz \rightarrow Ryy))$
* $\equiv \forall x (\neg Rxy \lor \neg \forall z(Sxz \rightarrow Ryy))$
* $\equiv \forall x (\neg Rxy \lor \neg \exists z(Sxz \land \neg Ryy))$

---

## Pränexnormalform
Eine Formel ist in Pränexnormalform, wenn alle Quantoren vor den Junktoren am Anfang der Formel stehen.  
Diese neue Formel ist dann **logisch äquivalent** zur ursprünglichen Formel.

Vorgehensweise:
1. Formel in Negationsnormalform bringen
2. Quantoren mit gleichen Variablen trennen
3. Alle Quantoren zum Anfang der Formel bringen

Beispiel: $\neg \forall x \neg Rxx \land \forall x \exists y (Rxy \land (\neg Ryy \land \exists x Ryx))$
* $\equiv \exists x Rxx \land \forall x \exists y(Rxy \land (\neg Ryy \land \exists x Ryx))$
* $\equiv \exists z Rzz \land \forall x \exists y(Rxy \land (\neg Ryy \land \exists u Ryu))$
* $\equiv \exists z \forall x \exists y \exists u(Rzz \land Rxy \land (\neg Ryy \land Ryu))$
* $\equiv \exists z \forall x \exists y \exists u(Rzz \land Rxy \land \neg Ryy \land Ryu)$

---

## Skolem-Normalform
Eine Formel ist in Skolem-Normalform, wenn alle Quantoren Allquantoren sind und diese am Anfang der Formel stehen. Diese neue Formel ist dann **erfüllbarkeitsäquivalent** zur ursprünglichen Formel.

Vorgehensweise:
1. Formel in Pränexnormalform bringen
2. Existenzquantoren durch Funktionen ersetzen

Beispiel: $\exists x \exists y \forall w \exists z(P(x,y,w) \lor Q(z,x))$
* $\equiv \exists y \forall w \exists z(P(a,y,w) \lor Q(z,a))$ mit $a$ als nullstelliges Funktionssymbol
* $\equiv \forall w \exists z(P(a,b,w) \lor Q(z,a))$ mit $b$ als nullstelliges Funktionssymbol
* $\equiv \forall w (P(a,b,w) \lor Q(f(w), a))$ mit $f$ als einstelliges Funktionssymbol

---