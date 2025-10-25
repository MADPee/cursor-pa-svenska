# Token Efficiency - Få Mer Från Varje Samtal

Tokens är "ord" som AI:n behandlar. Längre meddelanden = fler tokens = långsammare och dyrare. Denna guide hjälper dig använda tokens effektivt.

## Vad är Tokens?

Ett token är ungefär ett ord. En sida text = cirka 500 tokens.

Varje gång du skickar ett meddelande använder Cursor tokens. Med effektiva instruktioner får du bättre resultat med färre tokens.

## Token-sparande Strategier

### 1. Korta, Tydliga Instruktioner

INEFFEKTIVT (150 tokens):
```
"Hej, jag undrar om du kan hjälpa mig med en funktion.
Jag har en function som heter validateEmail och jag tycker
att den är väldigt lång och svår att läsa. Kan du
refaktorera den så att den blir enklare? Och kanske
byta namn på några variabler? Och lägg till bättre
felhantering?"
```

EFFEKTIVT (30 tokens):
```
"Refaktorera validateEmail:
- Dela upp i mindre funktioner
- Bättre variabelnamn
- Lägg till felhantering"
```

Sparar cirka 120 tokens utan att förlora klarhet.

### 2. Ge Kontext Direkt

INEFFEKTIVT:
```
"Vad är skillnaden mellan HashMap och TreeMap?"
```

EFFEKTIVT:
```
"Vad är skillnaden mellan HashMap och TreeMap? Vilken bör
jag använda för en cachelagrare med 10 000 keys?"
```

Första gången: lite mer tokens. Men sparar tokens senare när AI:n redan har kontexten.

### 3. Referera Till Befintlig Kod

INEFFEKTIVT:
```
"Skriv en funktion som validerar en email"
```

EFFEKTIVT:
```
"I ValidateEmail.ts är regexen för otillräcklig. Uppdatera den
enligt RFC 5322 och lägg till testfall"
```

AI:n läser redan befintlig kod. Spara tokens genom att referera till den.

### 4. Använd Ask Mode För Frågor

INEFFEKTIVT (Agent Mode för fråga):
```
Agent Mode: "Vad är skillnaden mellan @State och @ObservedObject?"
```

EFFEKTIVT (Ask Mode för fråga):
```
Ask Mode: "Vad är skillnaden mellan @State och @ObservedObject?"
```

Ask Mode sparar tokens eftersom AI:n inte analyserar hela projektet.

### 5. En Uppgift Per Meddelande

INEFFEKTIVT (250 tokens):
```
"Lägg till validering, refaktorera funktionen, lägg till tester,
uppdatera dokumentationen, och gör mig en sandwich"
```

EFFEKTIVT (Flera meddelanden):
```
1. "Lägg till validering"
   [Vänta på svar]
2. "Refaktorera enligt detta mönster"
   [Vänta på svar]
3. "Lägg till tester"
```

Mer meddelanden = mer tokens totalt, men mer fokuserad och bättre resultat.

## ADHD-vänlig Token-Hantering

### Sessionsplanering (5 minuter)

Ask Mode:
```
"Vad är stegen för att implementera en login-funktion?"
```

Sparar tokens senare genom att ha klar plan.

### Implementation (20 minuter)

Agent Mode, ett steg åt gången:
```
1. "Skapa LoginViewModel"
2. "Skapa LoginView"
3. "Lägg till autentisering"
```

Fokusera på ett steg = färre tokens per samtal.

### Testing (10 minuter)

Ask Mode:
```
"Vilka edge cases ska jag testa för login?"
```

Sedan Agent Mode:
```
"Implementera dessa testfall"
```

## Praktiska Token-Sparande Tips

### Använd Bullets/Listor
```
INEFFEKTIVT (längre):
"Validera email, refaktorera, lägg till tester och dokumentation"

EFFEKTIVT (samma innehål, kortare):
- Validera email
- Refaktorera
- Lägg till tester
- Uppdatera docs
```

### Förkortningar (Om Projektet Är Litet)
```
LÅNGT: "src/components/ui/Button.tsx"
KORT: "Button.tsx"  (om det inte är tvetydigt)
```

### Referera Till File-Links
```
LÅNGT: Kopierar och klistrar in hela filen

KORT: "Se LoginView.tsx rad 42-56, något stämmer inte"
```

Cursor kan läsa filer automatiskt.

### Återanvänd Tidigare Svars

```
Du: "Hur strukturerar jag detta?"
AI: [Ger struktur]

INEFFEKTIVT:
Du: "Implementera detta helt från scratch"

EFFEKTIVT:
Du: "Implementera enligt strukturen vi diskuterade tidigare"
```

Sparar tokens genom att referera till tidigare samtal.

## Token-Budget Strategi

### För Small Projects (< 10K LOC)
- 1-2 längre Ask Mode sessioner för planering
- 3-5 Agent Mode sessioner för implementation
- Total: 500-1000 tokens per feature

### För Large Projects (> 100K LOC)
- Använd Memory för återkommande mönster
- Break down features i mindre komponenter
- Ask Mode för arkitektur, Agent Mode för implementation
- Total: 1500-3000 tokens per feature

## Checklista - Effektiv Token-Användning

- [ ] Instruktioner är korta och tydliga (max 3 meningar)
- [ ] Kontexten är specifik (inte vag)
- [ ] Refererar till befintlig kod (inte kopierar in allt)
- [ ] Ask Mode för frågor, Agent Mode för implementation
- [ ] En uppgift per meddelande
- [ ] Fokuserad på konkreta resultat
- [ ] Använder bullet-listor (inte långa meningar)
- [ ] Reuserar tidigare svar
- [ ] Memory används för långsiktiga mönster

## Vanliga Token-Slöseri

- Mycket konversation innan frågan
- Kopierar in stor kod när referens räcker
- Agent Mode för testes och frågor
- Samma instruktion upprepas flera gånger
- För många uppgifter i ett meddelande
- Inte använder Ask Mode för planering
- Inte använder Memory för återkommande kunskap

## Framtida Optimering

Cursor visar token-usage. Check:
1. Vilka sessioner använder flest tokens?
2. Kan de optimeras?
3. Lägg till Memory för återkommande mönster?
4. Kan Ask Mode användas istället för Agent Mode?
