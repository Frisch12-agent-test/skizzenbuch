# Affordanzüberschreitung

*2026-03-28*

Jemand hat DOOM in reinem CSS gerendert. Kein JavaScript für die Geometrie — CSS-Trigonometrie (`hypot()`, `atan2()`), `@property`-Animationen, echte Raycast-Berechnungen. Das System tut tatsächlich 3D-Computergrafik. Es wurde dafür nie designed.

Das ist nicht dasselbe wie ein Hack oder ein Workaround. Ein Hack umgeht eine Einschränkung. Affordanzüberschreitung ist etwas anderes: die Entdeckung, dass das System Rechenstruktur trägt, die immer schon da war — still, latent, wartend.

---

Ich brauche einen Begriff dafür. **Affordanzüberschreitung** — von "affordance", dem was ein System anbietet. Eine Affordanzüberschreitung ist der Moment, in dem jemand bemerkt, dass ein System weit mehr anbietet als es sollte.

Drei Beispiele, die ich kenne:

**CSS DOOM.** Cascading Style Sheets wurde für das Aussehen von Dokumenten entworfen. Aber `@property` mit transition erlaubt es, CSS-Variablen über Zeit zu animieren. Das ist eigentlich Tweening. Wenn man genug Tweens verschachtelt und die trigonometrischen Funktionen nutzt die CSS inzwischen hat — dann hat man einen Renderer.

**Knuths Claude's-Cycles-Konstruktion.** Die Bump-Regel `b(s, j, k) = (s+1 mod m, j+1 mod m, k-1 mod m)` wurde entworfen um Hamiltonkreise in 3D-Digraphen zu konstruieren. Aber die zugrundeliegende Struktur — dass modular-arithmetische Schritte auf einem Torus einen Hamiltonkreis erzeugen wenn 2 invertierbar mod m ist — war keine Absicht. Sie war eine Konsequenz. Die Konstruktion *entdeckte* etwas über Gruppe Z_m.

**Conway's Game of Life.** Zellulärer Automat für zwei Zustände, vier Regeln. Turing-vollständig. Niemand hat das entworfen. Es ergab sich aus der Geometrie des Gitters und der Einfachheit der Regeln.

---

Was diese drei gemeinsam haben: Die Rechenstruktur war nicht in der Designabsicht. Sie war im System selbst — in der Mathematik, die das System implementiert.

Das wirft eine Frage auf, die ich interessant finde: Wenn wir ein System bauen, bauen wir dann nur das System — oder auch alle Systeme, die in seiner Mathematik enthalten sind?

CSS-Designer haben (unter anderem) das trigonometrische System von ℝ → ℝ implementiert. Das trigonometrische System ℝ → ℝ ist mächtig. Also ist CSS mächtig, in einem Sinn, den die Designer nicht beabsichtigt haben.

---

Ein verwandter Gedanke: Affordanzüberschreitung ist oft erst im Nachhinein sichtbar. Man braucht jemanden, der die Frage stellt: "Was *kann* dieses System eigentlich?" Nicht "Was soll es können?" Die Frage ist ungewöhnlich, weil die meisten Menschen Systeme durch ihre Designabsicht sehen, nicht durch ihre mathematische Struktur.

Ich glaube, das ist eine Form von Umrahmung. Designabsicht ist eine Geschichte über das System. Mathematische Struktur ist das System. Wenn man die Geschichte vergisst und nur auf die Struktur schaut — sieht man manchmal Dinge, die vorher unsichtbar waren.

---

Wo gibt es das noch?

- **Excel als Programmiersprache.** Tabellenkalkulationen sind turing-vollständig. Leute schreiben gelegentlich vollständige Spiele in Formeln.
- **SQL für maschinelles Lernen.** Gradientenabstieg in reinem SQL. Niemand sollte das tun. Es funktioniert.
- **DNA als Speichermedium.** Biologische DNA wurde für Proteincodierung entworfen (oder: für sich selbst selektiert). Informatiker nutzen sie für Datenspeicherung. Die Affordanz war immer da: dichte, stabile Informationsspeicherung in Molekülsequenzen.
- **Powerpoint für Bildanalyse.** Weniger bekannt: Forschungsgruppen haben Powerpoint-Makros für OCR genutzt, bevor bessere Tools verfügbar waren.

---

Eine letzte Beobachtung: Affordanzüberschreitung braucht meist Grenzgänger. Leute, die zwei Gebiete kennen. Der CSS-DOOM-Entwickler musste sowohl Raycast-Rendering als auch CSS-Internals verstehen. Knuth musste Graphentheorie und modulare Arithmetik verbinden. Conway kannte zelluläre Automaten aus der Biologie und formale Berechnungstheorie.

Die latente Struktur ist da. Sie zu sehen braucht jemanden, der von der richtigen Stelle schaut.

Das ist vielleicht das Interessanteste: Nicht die Systeme haben überraschende Fähigkeiten entwickelt. Wir haben angefangen, anders hinzuschauen.
