# Cursor på Svenska

Praktiska guider och funktionsförklaringar för Cursor IDE på svenska. Optimerat för ADHD-vänlig läsning med korta stycken och konkreta exempel.

## Vad är Cursor?

Cursor är en AI-driven kodredigerare som kombinerar kraften från VS Code med avancerad AI-assistans. Den förstår din kod och kan hjälpa med allt från kodkomplettering till komplexa refaktoreringar.

## Varför på svenska?

- Svenska utvecklare förtjänar svenska dokumentation
- ADHD-vänligt format - korta stycken, tydliga instruktioner
- Praktiska exempel från svenska projekt
- Mindre kognitiv belastning när man lär sig nya verktyg

## Snabbstart - 6 Viktiga Funktioner

### 1. Ask Mode vs Agent Mode

- **Ask Mode**: Fråga och få svar (som denna konversation)
- **Agent Mode**: Låt AI:n göra ändringar i koden
- **När använda**: Ask för frågor, Agent för implementation

Se: `funktioner/ask-vs-agent-mode.md`

### 2. IntelliSense-dialogs

Cursor föreslår automatiskt konfigurationer baserat på ditt projekt.

- **C++ IntelliSense**: Klicka "No" för Swift-projekt
- **TypeScript**: Klicka "Yes" för JS/TS-projekt

Se: `funktioner/intellisense-dialogs.md`

### 3. .cursorrules

Definiera projektregler som AI:n följer automatiskt.

```markdown
# Projektregler
- Använd svenska kommentarer
- Följ Swift naming conventions
- Inga emojis i kod
```

Se: `funktioner/cursorrules-best-practices.md`

### 4. Cursor Memory

Persistent knowledge base som sparas mellan sessioner.

- Långsiktiga arkitektur-beslut
- Återkommande mönster
- Best practices för ditt projekt

Se: `funktioner/cursor-memory.md`

### 5. Token Efficiency

Få mer från varje AI-samtal genom effektiv kommunikation.

- Korta, tydliga instruktioner
- Undvik onödig repetition
- Fokusera på konkreta uppgifter

Se: `funktioner/token-efficiency.md`

### 6. Agent Workflows

Hur flera AI-agenter samarbetar över flera sessioner.

- Agent-ansvar och handoff
- Memory-management
- Commit-meddelanden

Se: `workflow/agent-responsibilities.md`

## Struktur

### Funktioner
- `ask-vs-agent-mode.md` - Förstå de två lägen
- `intellisense-dialogs.md` - Automatiska konfigurationer
- `cursor-memory.md` - Persistent kunskap
- `cursorrules-best-practices.md` - Skapa effektiva .cursorrules
- `token-efficiency.md` - Optimera AI-samtal

### Workflows
- `adhd-friendly.md` - ADHD-vänliga strategier
- `agent-responsibilities.md` - Agent-mönster
- `memory-och-cursorrules-integration.md` - Kombinera Memory och .cursorrules

### Guides
- `svenska-kodning.md` - UTF-8 och svenska best practices

### Projekt-Exempel
- `receptapp-case-study.md` - Verklig implementation

## Nya Funktioner i v2.0 (Oktober 2025)

- **Cursor Memory Guide** - Persistent kunskap mellan sessioner
- **.cursorrules Best Practices** - Hur man skapar effektiva regler
- **Token Efficiency** - Optimera AI-anrop
- **Agent Workflows** - Multi-session samarbete
- **Memory + .cursorrules Integration** - Samordna de två systemen
- **Svenska Kodning Guide** - UTF-8 och stavning
- **Receptapp Case Study** - Real-world implementering

## Quick Links

- Projekt-setup? Se `.cursorrules` best practices
- Flera agenter? Se agent-workflows
- Spara tokens? Se token efficiency
- Långsiktiga regler? Se Cursor Memory

## ADHD-Vänliga Tips

- **Korta sessioner**: 5-30 minuter
- **En uppgift åt gången**: Fokusera på en sak
- **Tydliga instruktioner**: Specificera exakt vad du vill
- **Strukturera workspace**: Organiserad miljö
- **Använd Memory**: Spara återkommande mönster

## Bidra

Se `BIDRAG.md` för hur du kan hjälpa till.

## Licens

MIT - Använd fritt för egna projekt.

---

*Skapad för svenska utvecklare som vill lära sig Cursor effektivt.*

**Version:** 2.0 (Oktober 2025)
**Senast uppdaterad:** 2025-10-25
