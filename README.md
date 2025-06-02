# Culture Bot
Für das Modul der FHNW: Dialogsysteme
von Eufrat Özmen, David Ishak & Saliou Dieng

🔹 1. Define — Use Case

1.1 Problem
•	Viele Menschen mit Migrationshintergrund oder familiären Wurzeln im Ausland sind ohne enge Verbindung zu ihrem Herkunftsland aufgewachsen.
•	Ihnen fehlen leicht zugängliche, personalisierte Informationsquellen über Geschichte, Politik, Wirtschaft und Kultur dieses Landes.
•	Das Internet bietet zwar viele Informationen, aber oft unstrukturiert, zu komplex oder nicht vertrauenswürdig.

1.2 Goals
•	Bereitstellung eines interaktiven, sprachsensiblen Chatbots, der Wissen über Länder auf einfache und attraktive Weise vermittelt.
•	Ermöglichung gezielter Themenerkundung (z. B. Politik, Geschichte, Wirtschaft, Kultur) über Buttons.
•	Förderung von Identitätsstärkung, kultureller Neugier und Bildung durch nutzerzentrierte Inhalte.
•	Vereinfachter Zugang zu qualitativ hochwertigen Daten durch API-Anbindung (RestCountries, Wikipedia) und AI-generierte Texte.

1.3 Audience
•	Junge Erwachsene mit schwacher oder gebrochener Verbindung zu ihrem Herkunftsland.
•	Personen mit familiärem Migrationshintergrund, die auf der Suche nach Wissen, Identität und kulturellem Verständnis sind.
•	Nutzer:innen mit durchschnittlicher technischer Kompetenz, ohne Vorwissen über das Land.

1.4 Context
•	Einsatz als Web-Chatbot über Voiceflow (Desktop und Mobile).
•	Mehrsprachige Oberfläche (z. B. Deutsch, Englisch, Französisch).
•	Nutzung von offenen APIs (Wikipedia, RestCountries) kombiniert mit KI-generierten Antworten.
•	Einsatzszenarien: Bildungsbereich, soziale Projekte, Kulturinitiativen.

1.5  Define — User Persona
Name & Background
Name: Leila M.
Background: Leila ist 22 Jahre alt, lebt in Basel und studiert Soziale Arbeit. Ihre Familie stammt ursprünglich aus Senegal. Leila spricht fließend Deutsch, aber kaum Wolof oder Französisch. Sie möchte mehr über das Land erfahren, in dem ihre Eltern aufgewachsen sind – besonders über Geschichte, Kultur und gesellschaftliche Zusammenhänge.

Goals
Ein besseres Verständnis für Geschichte und Kultur Senegals entwickeln.
Mehr Orientierung über das Land gewinnen, um sich stärker mit ihrer Herkunft zu identifizieren.

Roles / Tasks
Nutzt den Chatbot spontan am Smartphone, meist abends oder unterwegs.
Wählt gezielt Themen per Button (Politik, Wirtschaft, Geschichte, Kultur).

Challenges
Onlinequellen wirken oft unübersichtlich oder unverständlich.
Fühlt sich durch Sprachbarrieren (Französisch/Wolof) von vielen Infos ausgeschlossen.

Questions & Prompts
„Wie war die Kolonialgeschichte Senegals?“
„Was sind typische kulturelle Bräuche?“
„Welche Musikrichtungen gibt es in Senegal?“
„Wie sieht die Wirtschaft dort heute aus?“

Desires
Einfache, verständliche Erklärungen, die ihr echtes Interesse wecken.
Verbindung zur eigenen Identität stärken – ohne schulisches Gefühl.

Fears
Zu technische oder oberflächliche Antworten.
Gefühl, nicht ernst genommen zu werden oder nicht dazu zu gehören.

1.6 Define — Bot Persona
Name & Character Description
Name: Cultur_Bot
Beschreibung: Ein freundlicher, respektvoller und wissbegieriger digitaler Assistent, der Nutzer:innen dabei hilft, ihr Herkunftsland besser kennenzulernen – immer offen, verständlich und empathisch.

Core Trait
Offen, informativ, einfühlsam.
Tone of Voice
Freundlich, klar, ruhig, leicht verständlich – auch bei komplexeren Themen. Immer respektvoll und kulturell sensibel.

Backstory
Cultur_Bot wurde als Reaktion auf den Wunsch entwickelt, jungen Menschen mit Migrationshintergrund den Zugang zu ihren kulturellen Wurzeln zu erleichtern – mit Respekt, Neugier und Unterstützung durch moderne Technologie.

Behaviour & Service
•	Startet mit Sprachwahl → Länderwahl → Themenauswahl via Buttons.
•	Bietet strukturierte, AI-generierte Antworten zu Politik, Geschichte, Wirtschaft, Kultur etc.
•	Gibt Folgeoptionen („Mehr wissen“, „Anderes Land“, „Beenden“).
•	Holt Basisdaten über APIs (Wikipedia, RestCountries).
•	Unterstützt emotional durch persönlichen, respektvollen Ton.

🔹 2. Design — Sample Dialogue
Beschreibung: Leila interessiert sich für ihr Herkunftsland Senegal und nutzt den Chatbot auf Deutsch, um sich gezielt über Kultur, Geschichte und Wirtschaft zu informieren.

<img width="588" alt="grafik" src="https://github.com/user-attachments/assets/cca05849-7ff0-4379-8fc5-39205b8bb987" />





🔹 3. Architect — Bot Architecture
1. Data Need
   
•	Länderinfos via RestCountries API

•	Themeninfos via Wikipedia API

•	Userdaten: Sprache & Länderwahl (für Sessionsteuerung)
•	Optional: Nutzungsverhalten für Analytics

3. Channel / UI
•	Voiceflow Web-Chat
•	Vollständig responsiv (Desktop + Mobile)
•	Optionale Button-Navigation für Themenwahl und Entscheidungspfade

4. Framework
•	Voiceflow zur Erstellung und Logikstruktur
•	KI-Modul innerhalb Voiceflow (Pio’s Agent) für natürliche Textgenerierung
•	Sprachauswahl-Logik via Code-Block (Javascript)

5. Action
•	GET-Requests an APIs zur Datenbeschaffung (z. B. Hauptstadt, Bevölkerung, Politik)
•	Ausgabe von personalisierten Antworten über strukturiertes Prompting
•	Dynamische Flows durch Button-Trigger


🔹 4. Projektüberblick
Cultur_Bot ist ein KI-gestützter Chatbot, der Menschen mit schwacher Verbindung zu ihrem Herkunftsland (z. B. Secondos oder junge Migrant:innen) hilft, auf einfache Weise relevante Informationen über dieses Land zu erhalten. Thematisch konzentriert sich der Bot auf Bereiche wie Geschichte, Politik, Wirtschaft und Kultur. Ziel ist es, Identitätsentwicklung, kulturelles Verständnis und Bildung auf niederschwellige Weise zu fördern.
Die Umsetzung erfolgte mit Voiceflow, einer No-Code-Plattform für die Entwicklung dialogbasierter Systeme. Dabei kamen APIs, Button-basierte Navigation, Sprachwahl und generative KI-Module zum Einsatz.

4.1 Phasen der Entwicklung

Erste Version – ohne API (statisch)
In der ersten Entwicklungsphase wurde eine minimal funktionsfähige Version (MVP) erstellt. Die Inhalte zu Ländern wurden manuell eingefügt, ohne Verbindung zu externen Datenquellen. Diese Phase diente der grundlegenden Konzeptvalidierung: Funktioniert die Idee, ein kulturelles Informationsangebot als Chatbot bereitzustellen?
Erkenntnisse:
•	Inhalte waren nur schwer wartbar.
•	Der Aufwand zur manuellen Pflege war hoch.
•	Es fehlte an Dynamik, Flexibilität und Aktualität.

Zweite Version - Einführung von APIs
In der zweiten Phase wurde die Datenbeschaffung automatisiert. Zwei externe APIs wurden integriert:
a) RestCountries API
•	Quelle: https://restcountries.com/
•	Funktion: Bereitstellung strukturierter Basisdaten wie Bevölkerung, Hauptstadt, Sprachen und Flagge.
•	Anwendung: Die Daten werden über GET-Requests abgerufen, in Variablen gespeichert (z. B. {countryInfo}) und in den Antworten verwendet.
b) Wikipedia API
•	Quelle: https://en.wikipedia.org/api/rest_v1/page/summary
•	Funktion: Abfrage von themenspezifischen Inhalten (z. B. Politik, Wirtschaft, Geschichte, Kultur).
•	Die Inhalte werden thematisch gefiltert, an die KI übergeben und zu sprachlich ansprechenden Texten verarbeitet.

Dritte Version: Einführung von Themen-Buttons
Zur Verbesserung der Benutzerführung wurden Auswahl-Buttons eingeführt. Nach der Länderwahl kann die Nutzerin oder der Nutzer aus den Themen Politik, Wirtschaft, Geschichte, Kultur, "anderes Land" oder "Beenden" wählen. Diese Entscheidung trug wesentlich zur Klarheit und Struktur im Gesprächsverlauf bei und ermöglichte eine gezielte Steuerung der Nutzerinteraktion.

Vierte Version:  Mehrsprachigkeit
Im weiteren Verlauf wurde eine Sprachwahl am Anfang des Gesprächs eingebaut. Zur Verfügung stehen Deutsch, Englisch und Französisch, Albanisch, Spanisch, Wolof, Italienisch, Portugiesisch, Schweizerdeutsch und Aramäisch. Die Sprachwahl wird in einer Variable gespeichert und beeinflusst den gesamten weiteren Gesprächsverlauf.
Diese Funktion brachte einerseits eine breitere Zielgruppenansprache und bessere Zugänglichkeit, führte andererseits aber zu einem erhöhten Pflegeaufwand bei der Benutzeroberfläche, da Inhalte mehrfach übersetzt und gepflegt werden müssen.

4.2 Technische Umsetzung in Voiceflow
Die technische Umsetzung folgt einem klaren Ablauf: Nach der Sprachauswahl gibt der Nutzer ein Land ein. Diese Eingabe wird in einer Variable gespeichert und über GET-Requests an beide APIs weitergegeben. Die Antworten werden in JSON-Form zurückgegeben, analysiert und in benutzerdefinierten Variablen gespeichert.
Das KI-Modul von Voiceflow verarbeitet diese Informationen weiter und generiert auf dieser Grundlage natürlichsprachliche Antworten. Die Themenwahl erfolgt über Buttons, wobei jede Auswahl in einer separaten Variablen hinterlegt wird. So wird gesteuert, ob der Bot Informationen über beispielsweise Wirtschaft oder Geschichte anzeigt. Nach jeder Antwort kann die Nutzerin oder der Nutzer erneut ein Thema wählen oder das Gespräch beenden.

4.3 Designentscheidungen und Begründungen
Im Projektverlauf wurden mehrere Schlüsselentscheidungen getroffen. Die Verwendung von APIs anstelle manueller Inhalte stellte die Skalierbarkeit, Aktualität und Wartbarkeit des Systems sicher. Die Kombination aus Wikipedia und RestCountries ermöglichte einerseits strukturierte Datennutzung, andererseits Zugriff auf thematische Tiefe. Die Einführung von Buttons sorgte für eine strukturierte Nutzerführung und eine intuitive Bedienung.
Die Sprachwahl zu Beginn des Dialogs förderte Inklusion und kulturelle Diversität. Gleichzeitig wurde durch die Integration generativer KI eine deutlich bessere Verständlichkeit erreicht als durch rohe API-Ausgaben. Der gesamte Flow wurde modular aufgebaut, um ihn später leicht erweitern zu können.

🔹 5. Reflexion
Das Projekt bietet zahlreiche positive Aspekte. Die technische Umsetzung ist skalierbar und vielseitig einsetzbar. Die Nutzung ist niederschwellig und auf die Zielgruppe zugeschnitten. Die Kombination aus Daten, Interaktion und KI generiert echten Mehrwert und schafft eine gute Balance zwischen Funktionalität und Bildung.
Dennoch gibt es auch Herausforderungen: Die Qualität der Wikipedia-Inhalte ist nicht immer konsistent. Die Mehrsprachigkeit erfordert hohen Pflegeaufwand, da alle Inhalte mehrsprachig gepflegt werden müssen. Zusätzlich besteht eine gewisse Abhängigkeit von der Verfügbarkeit externer APIs. Außerdem ist die inhaltliche Tiefe durch die Nutzung von Buttons begrenzt, da wir uns nicht auf Freitexteingaben fokussiert haben.

🔹 6. Ausblick und Weiterentwicklung
Cultur_Bot ist ein funktionierender Prototyp mit gesellschaftlichem Mehrwert. Das Projekt demonstriert, wie moderne Technologien wie APIs, generative KI und dialogisches Design sinnvoll kombiniert werden können, um kulturelle Bildung niedrigschwellig zugänglich zu machen.
Für die Zukunft sind mehrere Erweiterungen denkbar: Eine Text-to-Speech-Funktion könnte die Barrierefreiheit verbessern. Auch die Integration persönlicher Erfahrungsberichte (z. B. von Migrant:innen) wäre sinnvoll. Thematisch könnte der Bot um Bereiche wie Bildung, Religion oder Migration erweitert werden. Zudem wäre ein Backend mit Analysefunktionen hilfreich, um die Nutzung systematisch auszuwerten und Inhalte weiter zu optimieren.


Dieser Text wurde teilweise mithilfe Künstlicher Intelligenz erstellt, formatiert und/oder überarbeitet.

Links und Dateien:

teilweise fertiges Miro Board: https://miro.com/welcomeonboard/Y2RwWGxzMG5halI3d0lZL051SXA1ZDF4MkluL1IyNUcrY0NuQTVLN05Rdk13V3poS3VQNDJIN3ljd0lFRVpnbC9ETTlBNXZVeHRyYVdIYndoelBlNUEzREljTFMvQisyZDBEMG9Wb09pS2pla0R6SUd2U3NTTCtNL0cvS1NwaFNyVmtkMG5hNDA3dVlncnBvRVB2ZXBnPT0hdjE=?share_link_id=497470720686

Voiceflow worklow:
![voiceflow-export-1748860871957](https://github.com/user-attachments/assets/161b5618-86ce-45e5-bea2-fa17d49d2201)

Voiceflow link: https://creator.voiceflow.com/project/680f803b8c3d328c9c0ea9f9/canvas/64dbb6696a8fab0013dba194



