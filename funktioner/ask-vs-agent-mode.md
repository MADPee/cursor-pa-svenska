# Ask Mode vs Agent Mode

Cursor har två huvudsakliga lägen för AI-interaktion. Förstå skillnaden för bättre arbetsflöde.

## Ask Mode (Fråga-läge)

### Vad det är
- Du ställer frågor och får svar
- AI:n kan inte ändra din kod
- Som en intelligent kollega som ger råd

### När använda
- **Förstå kod** - "Vad gör denna funktion?"
- **Felsökning** - "Varför får jag detta fel?"
- **Planering** - "Hur ska jag strukturera detta?"
- **Lärande** - "Förklara detta koncept"

### Exempel
```
Du: "Vad är skillnaden mellan @State och @ObservedObject i SwiftUI?"

AI: @State är för lokal state inom en view...
```

## Agent Mode (Agent-läge)

### Vad det är
- AI:n kan läsa och ändra din kod
- Kan skapa nya filer
- Kan köra kommandon
- Som en programmeringspartner

### När använda
- **Implementation** - "Implementera denna funktion"
- **Refaktorering** - "Refaktorera denna kod"
- **Debugging** - "Fixa detta fel"
- **Nya features** - "Lägg till denna funktionalitet"

### Exempel
```
Du: "Implementera en login-funktion med Firebase"

AI: [Skapar LoginView.swift, LoginViewModel.swift, uppdaterar ContentView.swift]
```

## Praktiska exempel

### Scenario 1: Ny funktion
```
1. Ask Mode: "Hur ska jag strukturera en settings-sida i SwiftUI?"
2. Agent Mode: "Implementera settings-sidan enligt strukturen vi diskuterade"
```

### Scenario 2: Felsökning
```
1. Ask Mode: "Varför får jag 'Cannot find type' fel?"
2. Agent Mode: "Fixa import-problemet och lägg till saknade dependencies"
```

### Scenario 3: Kodförståelse
```
Ask Mode: "Förklara denna algoritm steg för steg"
[AI förklarar utan att ändra kod]
```

## ADHD-vänliga tips

### Korta sessioner
- **Ask Mode**: 5-10 minuter för snabba frågor
- **Agent Mode**: 15-30 minuter för implementation

### Tydliga instruktioner
```
❌ "Gör något med denna kod"
✅ "Refaktorera validateEmail funktionen för bättre läsbarhet"
```

### En uppgift åt gången
- Ställ en fråga i Ask Mode
- Implementera svaret i Agent Mode
- Testa resultatet
- Upprepa

## Byt mellan lägen

### Till Ask Mode
- Klicka på "Ask" i chatten
- Eller börja med "Fråga:" i meddelandet

### Till Agent Mode
- Klicka på "Agent" i chatten
- Eller börja med "Implementera:" i meddelandet

## Vanliga misstag

### Använder Ask Mode för implementation
```
❌ Ask Mode: "Skapa en login-funktion"
✅ Agent Mode: "Skapa en login-funktion"
```

### Använder Agent Mode för frågor
```
❌ Agent Mode: "Vad är skillnaden mellan Array och Set?"
✅ Ask Mode: "Vad är skillnaden mellan Array och Set?"
```

## Sammanfattning

| Ask Mode | Agent Mode |
|----------|------------|
| Frågor och svar | Kodändringar |
| Förståelse | Implementation |
| Planering | Execution |
| Lärande | Produktivitet |

**Regel:** Ask för att förstå, Agent för att göra.