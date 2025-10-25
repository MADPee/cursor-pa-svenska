# .cursorrules Best Practices

.cursorrules är en fil som definierar regler för AI:n att följa automatiskt. Denna guide visar hur man skapar effektiva regler.

## Vad är .cursorrules?

En markdown-fil i projektroten som innehåller instruktioner för Cursor AI. Allt från kodstil till säkerhetskrav.

## Filplacering

```
projekt/
├── src/
├── docs/
└── .cursorrules    <-- Här
```

## Struktur - Vad Inkludera

### 1. Projektöversikt
```markdown
# Projektregler - TodoApp

Denna app är en todo-lista för iOS byggd i SwiftUI.
Fokus på clean code, ADHD-vänlighet och säkerhet.
```

### 2. Kodstil
```markdown
## Kodstil

- Använd svenska kommentarer
- Max 80 tecken per rad
- Två radbrytningar mellan funktioner
- Namngivning: camelCase för variabler, PascalCase för klasser
```

### 3. Projektstruktur
```markdown
## Projektstruktur

views/        - SwiftUI Views
viewmodels/   - ViewModels
models/       - Data models
services/     - Business logic
utilities/    - Hjälpfunktioner
```

### 4. Do's och Dont's
```markdown
## Do's
- Använd @State för lokal state
- Lägg till felhantering
- Skriv enhetstester
- Kommentera svår logik

## Dont's
- Aldrig hardkoda hemliga nycklar
- Aldrig global mutable state
- Aldrig för stora Views (max 300 rader)
- Aldrig dangerouslySetInnerHTML
```

### 5. Säkerhetskrav (Om Relevant)
```markdown
## Säkerhet

- Autentisering krävs för alla API-anrop
- Validera all användarinput
- Använd HTTPS endast
- Loopa aldrig känslig data
```

### 6. AI-specifika Instruktioner
```markdown
## AI-instruktioner

- Ask Mode för frågor, Agent Mode för implementation
- Bryt komplexa uppgifter i mindre steg
- Använd konkreta exempel
- Referera till befintliga kod-mönster
```

## Exempel - Komplett .cursorrules

```markdown
# TodoApp - Cursor Regler

En enkel todo-app för iOS byggd i SwiftUI.

## Kodstil

- Svenska kommentarer och variabelnamn
- camelCase för variabler, PascalCase för klasser
- Max 80 tecken per rad
- Två radbrytningar mellan funktioner

## Struktur

models/      - Todo, User data models
views/       - SwiftUI UI components
viewmodels/  - Business logic
services/    - API och databasekommunikation

## Do's
- Använd @State för lokal state
- Lägg till error handling
- Skriv tests för models
- Kommentera svår logik

## Dont's
- Aldrig hardkoda nycklar
- Aldrig global mutable state
- Aldrig för stora Views (max 300 rader)
- Aldrig osäker nätverkskommunikation

## Säkerhet
- Autentisering för alla API-anrop
- Validera all användarinput
- HTTPS endast i produktion
- Loopa aldrig lösenord eller tokens

## Workflow
1. Ask Mode: "Hur ska jag struktera detta?"
2. Agent Mode: "Implementera enligt strukturen"
3. Test: "Lägg till tester"
4. Review: "Refaktorera för klarhet"
```

## ADHD-vänliga Tips

### Korta Regler
```
DÅLIGT: 50 rader med detaljerade instruktioner
BÄTTRE: 5-10 korta, tydliga punkter
```

### Konkreta Exempel
```
DÅLIGT: "Använd bra kodstil"
BÄTTRE: "camelCase för variabler: let todoTitle = ..."
```

### Priorities Tydligt
```markdown
## Priority 1: Säkerhet
- Autentisering alltid
- Validera input
- Inga hemliga nycklar

## Priority 2: Kodkvalitet
- Enhetstester
- Kommentarer
- DRY-princip

## Priority 3: Nice-to-have
- Optimeringar
- Loggning
- Dokumentation
```

## Vanliga Misstag

### För Många Regler
```
DÅLIGT: 200 rader med varje möjlig regel
BÄTTRE: 30-50 rader med viktigaste reglerna
```

### För Vaga Regler
```
DÅLIGT: "Skriv bra kod"
BÄTTRE: "Använd explicit typing, undvik Any"
```

### Inte Uppdaterat
```
DÅLIGT: .cursorrules från förra året
BÄTTRE: Uppdateras när nya patterns etableras
```

### Blandar Projekt-Regler Med Memory
```
DÅLIGT: Säkerhetsprinciper som borde vara i Memory
BÄTTRE: Projekt-specifika regler i .cursorrules
```

## Integration Med Memory

.cursorrules bör REFERERA till Memories, inte duplicera:

```markdown
# Memory Management

Vid sessionstart, läs dessa Memories:
- UTF-8 och Svenska stavning (ID: 10327035)
- Security-First Design (ID: 10327036)

Se docs/CURSOR_MEMORY_USAGE.md för detaljer
```

## Uppdatering

### När Uppdatera
- Ny arkitektur-pattern etableras
- Säkerhetspolicy ändras
- Team-regler fastställs
- Problemmönster upptäcks

### Commit-meddelande
```
docs: Update .cursorrules with security requirements
```

## Checklista - Bra .cursorrules

- [ ] Tydlig projektöversikt
- [ ] Kodstilsregler (max 10 punkter)
- [ ] Projektstruktur
- [ ] Do's och Dont's
- [ ] Säkerhetskrav (om relevant)
- [ ] AI-instruktioner
- [ ] Max 50-60 rader
- [ ] Uppdaterad denna månad
- [ ] Refererar till Memories (inte dupliceras)
- [ ] Konkreta exempel
