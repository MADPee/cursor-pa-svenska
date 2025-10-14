# ADHD-vänligt arbetsflöde

Tips och strategier för att använda Cursor effektivt med ADHD. Fokus på struktur, tydlighet och mindre kognitiv belastning.

## Grundprinciper

### Korta sessioner
- **5-10 minuter** för Ask Mode frågor
- **15-30 minuter** för Agent Mode implementation
- **Ta paus** mellan sessioner

### En uppgift åt gången
- Ställ en fråga → få svar → implementera → testa
- Undvik multitasking med AI:n
- Fokusera på konkreta steg

### Tydliga instruktioner
- Specificera exakt vad du vill ha
- Använd konkreta exempel
- Undvik vaga beskrivningar

## Praktiska strategier

### 1. Strukturera dina frågor

#### ❌ Otydligt
```
"Gör något med denna kod"
```

#### ✅ Tydligt
```
"Refaktorera validateEmail funktionen:
- Dela upp i mindre funktioner
- Lägg till bättre felhantering
- Använd regex för email-validering"
```

### 2. Använd .cursorrules för konsistens

Skapa `.cursorrules` fil i projektroten:

```markdown
# ADHD-vänliga regler
- Korta, tydliga kommentarer
- En funktion = en uppgift
- Använd svenska för kommentarer
- Inga emojis i kod
- Konsistent namngivning
```

### 3. Break down komplexa uppgifter

#### Stor uppgift
```
"Skapa en komplett e-handelsapp"
```

#### Mindre steg
```
1. "Skapa produktmodell"
2. "Implementera produktlista"
3. "Lägg till kundvagn"
4. "Skapa checkout-flöde"
```

### 4. Använd Ask Mode för planering

```
Ask: "Hur ska jag strukturera en SwiftUI settings-sida?"

Få svar med struktur och best practices

Agent: "Implementera settings-sidan enligt strukturen"
```

## ADHD-specifika tips

### Minimera distraktioner
- **Stäng onödiga flikar** - fokusera på aktuell uppgift
- **Använd fullscreen** - mindre visuell brus
- **Stäng notifikationer** - undvik avbrott

### Strukturera din workspace
```
projekt/
├── src/           # Källkod
├── docs/          # Dokumentation
├── tests/         # Tester
└── .cursorrules   # AI-regler
```

### Använd tydliga commit-meddelanden
```
❌ "fix stuff"
✅ "fix: email validation regex pattern"
```

## Cursor-specifika ADHD-tips

### Token efficiency
- **Korta instruktioner** - mindre kognitiv belastning
- **Konkreta exempel** - tydligare förståelse
- **En ändring åt gången** - fokusera på en sak

### Använd historik
- **Gå tillbaka** till tidigare konversationer
- **Referera** till tidigare lösningar
- **Bygg vidare** på etablerade mönster

### Leverage AI för struktur
```
Ask: "Vilken är bästa strukturen för denna SwiftUI app?"

Agent: "Implementera strukturen med separata Views för varje skärm"
```

## Vanliga fallgropar

### Överbelastning
- **Undvik** att be om för mycket samtidigt
- **Bryt ner** komplexa uppgifter
- **Ta pauser** mellan sessioner

### Perfektionism
- **Börja enkelt** - förbättra senare
- **Iterativ utveckling** - små steg framåt
- **Acceptera** "bra nog" som första version

### Distraktioner
- **Stäng sociala medier** under kodning
- **Använd pomodoro-timer** för fokus
- **Skapa dedikerad kodmiljö**

## Exempel på ADHD-vänligt arbetsflöde

### Session 1: Planering (5 min)
```
Ask: "Hur ska jag strukturera en todo-app i SwiftUI?"
[Få struktur och best practices]
```

### Session 2: Implementation (20 min)
```
Agent: "Implementera todo-app strukturen:
- TodoItem model
- TodoListView
- AddTodoView
- Basic CRUD operations"
```

### Session 3: Testning (10 min)
```
Ask: "Hur testar jag SwiftUI views?"
Agent: "Lägg till unit tests för TodoItem model"
```

### Session 4: Förbättring (15 min)
```
Agent: "Förbättra todo-app:
- Lägg till completion status
- Använd @State för local state
- Lägg till animations"
```

## Sammanfattning

- **Korta sessioner** - 5-30 minuter
- **En uppgift åt gången** - fokusera på en sak
- **Tydliga instruktioner** - specificera exakt vad du vill
- **Strukturera workspace** - organiserad miljö
- **Minimera distraktioner** - fokusera på kodning
- **Iterativ utveckling** - små steg framåt

**Kom ihåg:** Cursor är ett verktyg för att göra kodning enklare, inte mer komplext. Använd det för att minska kognitiv belastning, inte öka den.