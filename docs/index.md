1. IMPORTANT LINE FOR TOC
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

### Factory Method Pattern
Das Factory Method Entwurfsmuster dient der Entkopplung des Clients von der
konkreten Instanziierung einer Klasse. Das erstellte Objekt kann elegant
ausgetauscht werden. Oft wird es zur Trennung von (zentraler) Objektverarbeitung
und (individueller) Objektherstellung verwendet. 

Der Erstellungscode eines Objektes (Product genannt) wird in einer eigenen Klasse
(Creator, Factory) ausgelagert. Dieser Creator ist abstrakt und delegiert die
konkrete Objektinstanziierung wiederrum an seine Unterklasse. Erst die Unterklasse
entscheidet welches Product erstellt wird. Da der Client sich komplett auf
Abstraktion stützt (sowohl beim Creator als auch bei den Products), ist er
vollkommen von den Implementierungen entkoppelt und unabhängig. 


Der abstrakte Creator kann allgemeine Modifikationen am Product durchführen.
Der konkrete Creator kann Produktspezifische Modifikationen an ihm durchführen.

[Factory Method](https://www.philipphauer.de/study/se/design-pattern/factory-method.php)

### Abstract Factory Pattern
Das Abstract Factory Design Pattern dient der Definition einer 
zusammenhängenden Familie aus Produkten (engl. products). Die Familien
können elegant ausgetauscht werden.

Der Instanziierungscode wird in eine Factory ausgelagert. Allerdings wird 
die Factory hinter einer abstrakten Schnittstelle vor dem Client verborgen.
Diese Factoryschnittstelle, die namensgebende Abstract Factory, definiert
für jedes Produkt der Produktfamilie (Produktsatz) eine Operation, mit der 
der Client eine Instanz des jeweiligen Produkts erhalten kann. Der Client
ist damit von einer bestimmten Factoryimplementierung entkoppelt. Es stützt 
sich allein auf Abstraktion - sowohl bei den Produkten als auch bei der Factory.

Da eine Factory immer die gesamte Schnittstelle erfüllen muss, wird sicher
gestellt, dass der Client nur mit Produkten arbeitet, die zusammen gehören
und zusammen passen. Die abstrakte Factory gibt eine Familie an abstrakten 
Produkten zurück.

[Abstract Factory](https://www.philipphauer.de/study/se/design-pattern/abstract-factory.php)

### Singleton Pattern
Das Singleton Entwurfsmuster sorgt dafür, dass es von einer Klasse nur eine
einzige Instanz gibt und diese global zugänglich ist.

Damit es nur eine einzigartige Instanz gibt, muss eine
Instanziierung durch den Client verhindert werden. Dafür wird der 
Konstruktur privat deklariert. Nun kann einzig der Singletoncode 
selbst das Singleton instanziieren.

#### Lazy- vs Eager-Loading
Lazy erstellt die Singleton-Instanz erst beim ersten Aufruf der 
`getInstance`-Methode. Eager loading erstellt die Instanz beim Laden der Klasse 
(statische Initialisierung).

#### Synchronisierung
Multithreading benötigt den sog. <em>doppelten Null-Check</em>:
```py
if instance is null:
    synchronize:
        if instance is null:
            InitializeInstance()
else:
    return instance
```

[Singleton](https://www.philipphauer.de/study/se/design-pattern/singleton.php)

### Command Pattern
Das Command Design Pattern ermöglicht die Modularisierung von Befehlen und 
Aufrufen. Auf elegante Weise können Befehle rückgängig gemacht, protokolliert
oder in einer Warteschlange gelegt werden.

Invoker (Aufrufer) und Receiver (Empfänger) werden entkoppelt. 
Dazu werden die namensgebenden Command-Objekte (Befehle) zwischengeschaltet. 
Nur das Command-Objekt allein weiß, welche Aktionen auf welchem Empfänger 
auszuführen sind. Das Command-Objekt wird extern erstellt/initialisiert.
Ein Settingsmenü könnte weitere konfiguration an ihm durchführen.
Der Aufrufer ist nur sinnvoll eingesetzt, wenn er keine erstellung/konfiguration
vom Command-Objekt durchführt. Mehrere Aufrufer können somit den selben Befehl
ausführen. Das Command-Objekt arbeitet mit dem konkreten Receiver und führt
die spezifischen Aufrufe der Receiver-Methoden durch.

[Command](https://www.philipphauer.de/study/se/design-pattern/command.php)

### Composite Pattern
Das Composite Entwurfsmuster ermöglicht es, eine verschachtelte (Baum)Struktur 
einheitlich zu behandeln, unabhängig davon, ob es sich um ein atomares Element 
oder um ein Behälter für weitere Elemente handelt. Der Client kann elegant mit 
der Struktur arbeiten.

Es wird eine gemeinsame Schnittstelle für die Elementbehälter (Composite,
Kompositum; Aggregat, Knoten) und für die atomaren Elemente (Leaf, Blatt)
definiert: Component. Diese Schnittstelle Component definiert die Methoden,
die gleichermaßen auf Composites und auf Leafs angewandt werden sollen. 
Composites delegieren oft Aufrufe (operate()) an ihre Components, die atomare
Leafs oder wiederrum zusammengesetzte Composites seien können.

Die Default-Implementierung der Component-Schnittstelle beinhaltet für alle
Methoden ausschließlich `throw new Exception("not implemented")`. Blätter
und Knoten haben somit nur die Aufgabe, die für sie relevanten Methoden
zu implementieren.

[Composite](https://www.philipphauer.de/study/se/design-pattern/composite.php)

### Model View Controller Pattern
- Model: Backend, welches alle Daten verwaltet
  - Datenbankinteraktion
  - Integrität etc.
- View: Stellt den aktuellen Zustand dar (GUI)
  - Userinteraktionen mit der View werden via Eventhandler und Setter an
    den Controller weitergeleitet
- Controller: Logik, die entscheidet wie die Daten dargestellt werden und das Model
  modifiziert wird.
  - Zieht sich den Zustand der Daten aus dem Model
  - Setzt die View auf

[MVC GfG](https://www.geeksforgeeks.org/mvc-design-pattern/)
[MVC FCC](https://www.freecodecamp.org/news/the-model-view-controller-pattern-mvc-architecture-and-frameworks-explained/)

# Analysis
## Partielle Integration
Sei $$\mathbb{I}$$ ein offenes Intervall und $$f,g: \mathbb{I} \to \mathbb{R}$$ differenzierbar.
Dann gilt:

$$\int f \cdot g \, dx = f \cdot \int g \, dx - \int f' \cdot (\int g \, dx) \, dx$$

oder anders ausgedrückt:

$$\int f \cdot g' \, dx = f \cdot g - \int f' \cdot g \, dx$$

[Integration by Parts](https://www.mathsisfun.com/calculus/integration-by-parts.html)

# Internet
## Open System Interconnection (OSI) model
1. Physical: Transfers Bits
2. Data Link: Transfers Data Frames between 2 nodes
3. Network (IP): Transfers Packets over a multi-node Network (routing, addressing, etc.)
4. Transport (TCP UDP): Transfers Segments/Datagrams using segmentation, acknowledgement etc.

[Wikipedia](https://en.wikipedia.org/wiki/OSI_model)

## Hypertext Transfer Protocol (HTTP)
Basiert auf TCP.

![Anfrage](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http_request.png)

Methoden:
- GET: Erhält Daten vom Server
- POST: Sendet Daten an den Server
- OPTIONS: Erlaubte Kommunikationsmethoden mit dem Server
- HEAD: GET ohne Body (nur header).

[HTTP HEADERS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers)
[HTTP Status Codes](https://developer.mozilla.org/en-US/docs/Web/HTTP/Status)

![Antwort](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview/http_response.png)

[Mozilla](https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview)

# Sonstiges
## Curl Zeugs
- `--request [GET/POST/HEAD/...]` request type
- `--header 'xyz'` custom header

```sh
curl --trace-ascii - \ 
<ip/domain> \ 
--request POST \
--header 'Accept:' \
--header 'User-Agent:' \
--header 'Host: <domain>' \
--data 'mysuperdata'
```


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
