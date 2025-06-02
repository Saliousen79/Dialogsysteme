# Dialogsysteme
Für das Modul: Dialogsysteme

1.1 Define — Use Case
1. Problem
•	Viele Menschen mit Migrationshintergrund oder familiären Wurzeln im Ausland sind ohne enge Verbindung zu ihrem Herkunftsland aufgewachsen.
•	Ihnen fehlen leicht zugängliche, personalisierte Informationsquellen über Geschichte, Politik, Wirtschaft und Kultur dieses Landes.
•	Das Internet bietet zwar viele Informationen, aber oft unstrukturiert, zu komplex oder nicht vertrauenswürdig.
2. Goals
•	Bereitstellung eines interaktiven, sprachsensiblen Chatbots, der Wissen über Länder auf einfache und attraktive Weise vermittelt.
•	Ermöglichung gezielter Themenerkundung (z. B. Politik, Geschichte, Wirtschaft, Kultur) über Buttons.
•	Förderung von Identitätsstärkung, kultureller Neugier und Bildung durch nutzerzentrierte Inhalte.
•	Vereinfachter Zugang zu qualitativ hochwertigen Daten durch API-Anbindung (RestCountries, Wikipedia) und AI-generierte Texte.
3. Audience
•	Junge Erwachsene mit schwacher oder gebrochener Verbindung zu ihrem Herkunftsland.
•	Personen mit familiärem Migrationshintergrund, die auf der Suche nach Wissen, Identität und kulturellem Verständnis sind.
•	Nutzer:innen mit durchschnittlicher technischer Kompetenz, ohne Vorwissen über das Land.
4. Context
•	Einsatz als Web-Chatbot über Voiceflow (Desktop und Mobile).
•	Mehrsprachige Oberfläche (z. B. Deutsch, Englisch, Französisch).
•	Nutzung von offenen APIs (Wikipedia, RestCountries) kombiniert mit KI-generierten Antworten.
•	Einsatzszenarien: Bildungsbereich, soziale Projekte, Kulturinitiativen.

1.2 Define — User Persona
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

🔹 1.3 Define — Bot Persona
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
Beschreibung:
Leila interessiert sich für ihr Herkunftsland Senegal und nutzt den Chatbot auf Deutsch, um sich gezielt über Kultur, Geschichte und Wirtschaft zu informieren.
BOT response	USER input	BOT response (alternatives)
Welcome! Which language do you prefer?	German	–
Über welches Land möchtest du gerne mehr Informationen erhalten?	Senegal	–
Senegal ist ein afrikanisches Land… Möchtest du mehr erfahren oder ein anderes Land wählen?	Mehr Informationen	–
Was interessiert dich: Politik, Geschichte, Wirtschaft oder Kultur?	Kultur	Senegal ist kulturell sehr vielfältig…
Möchtest du ein anderes Thema wählen oder beenden?	Wirtschaft	Die Wirtschaft Senegals ist stark diversifiziert…
Noch Interesse an Geschichte, Politik oder einem anderen Land?	Geschichte	Die Geschichte Senegals reicht bis in die Steinzeit zurück…
Noch Fragen?	Beenden	Schön, dass du da warst! Bis bald.

 
🔹 3. Architect — Bot Architecture
1. Data Need
•	Länderinfos via RestCountries API
•	Themeninfos via Wikipedia API
•	Userdaten: Sprache & Länderwahl (für Sessionsteuerung)
•	Optional: Nutzungsverhalten für Analytics
2. Channel / UI
•	Voiceflow Web-Chat
•	Vollständig responsiv (Desktop + Mobile)
•	Optionale Button-Navigation für Themenwahl und Entscheidungspfade
3. Framework
•	Voiceflow zur Erstellung und Logikstruktur
•	KI-Modul innerhalb Voiceflow (Pio’s Agent) für natürliche Textgenerierung
•	Sprachauswahl-Logik via Code-Block (Javascript)
4. Action
•	GET-Requests an APIs zur Datenbeschaffung (z. B. Hauptstadt, Bevölkerung, Politik)
•	Ausgabe von personalisierten Antworten über strukturiertes Prompting
•	Dynamische Flows durch Button-Trigger
 

