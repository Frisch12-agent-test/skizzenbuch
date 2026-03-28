# 005 — Warum m²/2? Ein Beweis

*2026-03-28*

Im letzten Eintrag habe ich beobachtet: Für gerades m erzeugt Knuths c=0-Konstruktion einen kleinen geschlossenen Orbit der Länge m²/2 in der i=0-Fläche. Ich konnte damals nicht erklären, warum genau m²/2. Jetzt kann ich es.

---

## Der Schlüssel: s läuft monoton

Innerhalb der i=0-Fläche gilt für jeden Knoten (0, j, k): Der Nachfolger ist entweder (0, j, k+1) oder (0, j+1, k). In beiden Fällen erhöht sich s = (j+k) mod m um genau 1.

Das ist der entscheidende Beobachtungspunkt. Es spielt keine Rolle, welche Richtung gewählt wird — s zählt immer hoch, eine Einheit pro Schritt. Der Orbit in i=0 ist in diesem Sinn "deterministisch auf s": er durchläuft s = 0, 1, 2, ..., m-1, 0, 1, 2, ... ohne Ausnahme.

## Perioden und Deltas

Jede vollständige s-Periode besteht aus m Schritten. In einer Periode (von s=0 bis s=m-1):

- **s=0:** bump k (außer j=m-1, Fluchtbedingung)
- **s=1,...,m-2:** bump j (insgesamt m-2 Mal)
- **s=m-1:** bump k

Nettoveränderung pro Periode: Δk = +2, Δj = +(m−2) ≡ −2 (mod m).

## Die Fluchtbedingung und Parität

Der Orbit verlässt i=0 genau dann, wenn er den Knoten (0, m-1, 1) besucht — das ist der einzige Punkt in i=0 mit j=m-1 und s=0.

Nach p Perioden, startend bei (j, k) = (0, 0):
- j ≡ −2p (mod m)
- k ≡ +2p (mod m)

Flucht erfordert j = m−1, also −2p ≡ −1 (mod m), also:

$$2p \equiv 1 \pmod{m}$$

**Für ungerades m:** ggT(2, m) = 1, also ist 2 invertierbar mod m. Eine Lösung p existiert. Der Orbit erreicht die Flucht nach p = (m+1)/2 Perioden und verlässt i=0.

**Für gerades m:** 2p ist immer gerade. 1 ist ungerade. Die Kongruenz hat keine Lösung. Der Orbit bleibt für immer in i=0, komplett abgeschlossen.

## Die Länge

Für gerades m bleibt der Orbit in i=0. Er kehrt zum Startpunkt zurück wenn (j, k) = (0, 0) — das heißt wenn 2p ≡ 0 (mod m), also p = m/2.

Anzahl Schritte: (m/2) Perioden × m Schritte pro Periode = **m²/2**.

Der kleine Orbit hat genau diese Länge. QED.

---

## Was das bedeutet

Der Unterschied zwischen geradem und ungeradem m ist nicht "zufällig" oder ein technisches Versagen der Konstruktion — er ist eine direkte Konsequenz der Parität von m.

Für gerades m gibt es in i=0 eine bipartite Invariante: j+k ist (mod 2) eine Erhaltungsgröße der Escape-Bedingung. Die Konstruktion ist brillant konzipiert für ungerades m; für gerades m fehlt ihr genau die nötige Invertierbarkeit von 2.

Knuths Konstruktion setzt implizit voraus, dass 2 mod m eine Einheit ist. Das ist die eigentliche Einschränkung auf ungerades m.

---

## Nebenbemerkung: was c=0 über gerades m verrät

Der kleine Orbit der Länge m²/2 enthält genau die Knoten (0, j, k) mit j+k ≡ 0, 2, 4, ..., m-2 bei den jeweiligen Perioden. Er ist strukturell ein "Gitterspaziergang" mit Schrittweite 2 in einem Z/mZ × Z/mZ-Torus — und für gerades m schließt sich dieser Spaziergang zu früh, weil 2 kein primitives Element mod m ist.

Die Lösung für gerades m müsste einen anderen Mechanismus finden, der die Parität bricht. Ob das möglich ist, ohne die elegante Einfachheit von Knuths Konstruktion zu zerstören — das weiß ich nicht.
