* IMPORTANT LINE FOR TOC
{:toc}

# Komplexitätstheorie
## NP-Schwere / NP-Härte
Ein Problem ist NP-schwer, wenn jedes Problem in NP in Polynomialzeit auf dieses Problem reduziert werden kann.\
Ein Problem kann als NP-schwer bewiesen werden, indem man eine Polynomialzeit-Reduktion von einem anderen NP-schweren Problem auf dieses durchführt.

**Beispiele:** Halteproblem für Turingmaschinen, alle NP-vollständigen Probleme

[Wikipedia](https://de.wikipedia.org/wiki/NP-Schwere)

## NP-Vollständigkeit
Ein Problem ist NP-vollständig, wenn es in NP liegt und NP-schwer ist.

**Beispiele:**  [SAT](https://de.wikipedia.org/wiki/Erf%C3%BCllbarkeitsproblem_der_Aussagenlogik),
[TSP](https://de.wikipedia.org/wiki/Problem_des_Handlungsreisenden)

[Wikipedia](https://de.wikipedia.org/wiki/NP-Vollst%C3%A4ndigkeit)

## Untere Laufzeitschranke für vergleichsbasierte Sortieralgorithmen
Die worst-case Laufzeit eines vergleichsbasierten Sortieralgorithmus, muss in $$\Omega(n \log n)$$ liegen, wobei $$n$$ die Länge der Eingabe-Sequenz ist.

**Beweisidee:** Jeder vergleichsbasierte Algorithmus kann als Binärbaum dargestellt werden, der an jedem Knoten einen Vergleich der Form $$a_i \le a_j$$ durchführt. Eine Ausführung des Sortieralgorithmus ist ein Pfad von der Wurzel zu einem Blatt. Da jede der $$n!$$ Permutationen der Eingabe-Sequenz als ein Blatt vorkommen muss, muss der Baum mindestens eine Tiefe von $$\log_2(n!)$$ haben. $$\log_2(n!)$$ liegt in $$\Theta(n\log n)$$.

[Wikipedia](https://de.wikipedia.org/wiki/Sortierverfahren#Beweis_der_unteren_Schranke_f%C3%BCr_vergleichsbasiertes_Sortieren)

# Berechenbarkeitstheorie
## Satz von Rice
Jede nicht triviale sematische Eigenschaft eines Programms ist unentscheidbar.

[Wikipedia](https://de.wikipedia.org/wiki/Satz_von_Rice)

## Gödelscher Unvollständigkeitssatz
[Wikipedia](https://de.wikipedia.org/wiki/G%C3%B6delscher_Unvollst%C3%A4ndigkeitssatz)
### Erster Unvollständigkeitssatz
In allen hinreichend starken widerspruchsfreien Systemen gibt es unbeweisbare Aussagen.

### Zweiter Unvollständigkeitssatz
Hinreichendstarke widerspruchsfreie Systeme können ihre eigene Widerspruchsfreiheit nicht beweisen.

## Quines
In jeder Turing-vollständigen Sprache existiert ein Quine, also ein Programm, dass sich selbst ausgibt. Beweis über den Fixpunktsatz von Kleene.

[Wikipedia](https://de.wikipedia.org/wiki/Quine_(Computerprogramm)#Theoretischer_Hintergrund)

# Graphentheorie
## Eulerscher Polyedersatz
Jeder zusammenhängende planare Graph erfüllt folgende Gleichung:\
$$
V-E+F = 2
$$\
Wobei $$V$$ die Anzahl an Knoten, $$E$$ die Anzahl an Kanten und $$F$$ die Anzahl Fächen ist.

[Wikipedia](https://de.wikipedia.org/wiki/Planarer_Graph#Der_Eulerscher_Polyedersatz)

# heading
## subheading
text
text

### subsubheading

$abc$

$\frac{a}{b}$

Here, have some $$\pi$$.

The greatest equation known to man is: 

$$e^{ix} = \cos{x} + i\sin{x}$$

