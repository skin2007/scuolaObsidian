
## Analisi nome-verbo

L'analisi nome-verbo è una tecnica di progettazione software che scompone il problema in tre componenti:
- **Soggetti**: Sostantivi che rappresentano l'origine dell'azione (es. "medico", "responsabile").
- **Verbi**: Azioni che possono essere eseguite (es. "inserisce", "registra").
- **Oggetti**: Dati o entità soggette all'azione (es. "cartella clinica", "riparazioni").

Questa analisi aiuta a identificare i **requisiti** del sistema, che vengono poi tradotti in classi, proprietà e metodi nella programmazione orientata agli oggetti (OOP). Un requisito è una frase semplice del tipo "Qualcuno fa qualcosa" (es. "Il medico inserisce la cartella clinica").

---
## Incapsulamento

L'incapsulamento è un principio dell'OOP che combina:
- **Astrazione**: Estrazione dei requisiti dal problema.
- **Responsabilità**: Accorpamento dei requisiti in classi basate su affinità.
- **Information Hiding**: Nascondere i dettagli interni delle classi, esponendo solo ciò che è necessario.

Questo processo porta alla creazione di **classi di business**, che rappresentano gli oggetti del mondo reale (es. "Libro", "Utente", "Prestito").

---
## Architettura three-layer

L'architettura three-layer divide l'applicazione in tre livelli:
- **Presentazione (Boundary)**: Gestisce l'interfaccia utente (es. form per inserire dati).
- **Applicazione (Business)**: Contiene la logica di business (es. gestione prestiti).
- **Accesso ai dati (Bean)**: Gestisce i dati persistenti (es. database).

### Relazione tra i Concetti

- **Soggetti** (analisi nome-verbo) interagiscono con il livello di **Presentazione**.
- **Verbi** (azioni) sono implementati nel livello di **Applicazione**.
- **Oggetti** (dati) sono rappresentati nel livello di **Accesso ai dati**.

L'incapsulamento aiuta a organizzare i requisiti in classi, che vengono poi distribuite nei tre livelli dell'architettura. Questo migliora la modularità, la manutenibilità e la scalabilità del software.

### Esempio Pratico

Supponiamo un'applicazione per la gestione di una biblioteca:
- **Bean**: `Libro`, `Utente`, `Prestito` (oggetti di business).
- **Business**: `Biblioteca` con metodi come `prestaLibro()` e `restituisciLibro()` (logica di business).
- **Boundary**: Interfaccia utente per cercare libri, prestarli o restituirli.

Questa struttura riflette l'analisi nome-verbo e utilizza l'incapsulamento per organizzare il codice in modo chiaro e separato.

---
## Conclusione
L'analisi nome-verbo, l'incapsulamento e l'architettura three-layer sono strettamente collegati:
- **L'analisi nome-verbo** identifica i requisiti.
- **L'incapsulamento** organizza i requisiti in classi.
- **L'architettura three-layer distribuisce le classi nei livelli appropriati.

Questo approccio rende il software più strutturato, facile da mantenere e adattabile alle esigenze del cliente.