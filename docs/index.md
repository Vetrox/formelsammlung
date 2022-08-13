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

# Softwareentwicklung
## Design Patterns
### Strategy Pattern
Das Verhalten (Funktionalität, Algorithmus) eines Objekts (dem Context) 
wird in eine eigene Strategieklasse (Strategie = gekapselter Algorithmus) ausgelagert.
Der Context hält eine Referenz auf sein Strategieobjekt und wenn er das ausgelagerte
Verhalten ausführen soll, so delegiert er den Aufruf an sein referenziertes Strategieobjekt.
Der Context arbeitet mit einer Strategie-Schnittstelle.

[Strategy](https://www.philipphauer.de/study/se/design-pattern/strategy.php)

### Observer Pattern
Das Observer Pattern ermöglicht, dass sich Objekte (Observer, **beobachtendes** Objekt) 
bei einem anderem Objekt (Subject, **beobachtetes** Objekt) registrieren und 
fortan vom diesem informiert werden, sobald es sich ändert. 

Beispiel sind Clients (Observer), die sich bei einem Server (Subject) registrieren,
um über broadcasts informiert zu werden. Dabei werden Interfaces verwendet,
um das Verhalten von Observer und Subject zu extrahieren.

[Observer](https://www.philipphauer.de/study/se/design-pattern/observer.php)

### Decorator Pattern
Das Decorator Design Pattern ermöglicht das dynamische Hinzufügen von Fähigkeiten
zu einer Klasse. Dazu wird die Klasse, dessen Verhalten wir erweitern möchten 
(Component, Komponente), mit anderen Klassen (Decorator, Dekorierer) dekoriert
(vgl. engl. "to wrap": umhüllen). Das heißt der Decorator umschließt (enthält)
die Component. Der Decorator ist vom selben Typ wie das zudekorierende Objekt, 
hat somit die gleiche Schnittstelle und kann an der selben Stelle wie die
Component benutzt werden. 
Er delegiert Methodenaufrufe an seine Component weiter und führt sein eigenes 
Verhalten davor oder danach aus.

Die Reihenfolge der Decorators sollte keine Rolle spielen, in der Praxis 
ist dies aber mitunter anders.

Eine Liste könnte als Decorator-Pattern ausgedrückt werden. Das Ende (NIL) ist 
die Komponente (als Alternative könnte man unterschiedliche Enden von Listen)
ermöglichen, die dann alle Komponenten wären). Die Dorierer sind dann
die weiteren (vorne angehangenen) Listenelemente (viele Klassen, ein Interface).
Sowohl Komponenten als auch Dekorierer erweitern das Listen-Interface, welches
die `print`-Methode beinhaltet. Ein Aufruf dieser resultiert in rekursiven
Aufrufen der print Methode von den geschachtelten Dekorierern bzw. der
Komponente.

[Decorator](https://www.philipphauer.de/study/se/design-pattern/decorator.php)

### Rest WIP

[Katalog](https://www.philipphauer.de/study/se/design-pattern.php)


# Sonstiges
## Nützliches Git Gedöns
- Branch löschen: `git push origin :mybranch`
- Tag erstellen: `git tag -a mytag`
  - Tag löschen: `git push --delete origin mytag`
- Stash (staged & unstaged uncommited changes): `git stash push -m 'mydescription'`
  - Re-Apply changes (apply=keep stash): `git stash [apply/pop] stash@{xy}`
  - Stash untracked changes aswell: `-u`
  - Stash ignored and untracked aswell: `-a`
  - List stashes: `git stash list`
  - Create branch of stash: `git stash branch branchname stash@{xy}`
  - Delete stash: `git stash drop stash@{xy}`

### Merging strategies
`git checkout main && git merge feature [options] `
- Fast-forward (`--ff-only`): `feature`-branch hat neue commits, main branch nicht. Alle `feature` commits werden an main angehangen.
- Recursive (`-s recursive`): Default. Macht irgendwie alles und nix.
- Ours (`-s ours`): Löst merge-Konflikte, indem immer die main Version der Änderung bevorzugt wird.
- Octopus (`-s octopus`): Bricht den merge bei Konflikten ab. 
- Resolve (`-s resolve`): Löst nur absolut triviale Konflikte automatisch.
- Subtree (`-s subtree`): Wenn feature eine teilbaum von main ist.
