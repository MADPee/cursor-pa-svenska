# Memory och .cursorrules Integration

Hur man samordnar Memory (persistent) och .cursorrules (session-specifik) för optimal Cursor-användning.

## Skillnaden - Quick Reference

| Aspekt | Memory | .cursorrules |
|--------|--------|------------|
| Scope | Global (alla projekt) | Projekt-specifik |
| Persistens | Mellan sessioner | Enskild session |
| Storlek | Kort (max 300 ord) | Medel (30-60 rader) |
| Uppdatering | Manuell via tool | Via git commit |
| Användning | Kunskap | Regler |

## Praktisk Integration

### .cursorrules Refererar Till Memory

```markdown
# Projektregler

## Memory Management
Vid sessionsstart, läs dessa Memories:
- ID: 10327035 (UTF-8 och Svenska stavning)
- ID: 10327036 (Security-First Design)

Se docs/CURSOR_MEMORY_USAGE.md för detaljer
```

Fördel: .cursorrules blir kortare, Memory uppdateras oberoende.

### Memory Sparar Långsiktiga Mönster

Exempel från Receptapp:

**Memory 1:**
```
Title: UTF-8 och Svenska stavning
Knowledge: Använd alltid Å, Ä, Ö. 
Säker (inte sikker). Förbättrad (inte forbattrad).
Inga emojis i output.
```

**Memory 2:**
```
Title: Security-First Design
Knowledge: Edge Functions MÅSTE ha JWT-auth, 
input-validering, SSRF-skydd, timeout, safe error handling.
Security Auditor Agent har veto-rätt.
```

.cursorrules refererar bara till Memory-IDs.

## Implementeringsmönster

### Pattern 1: Projekt-Specifik .cursorrules + Global Memory

```
.cursorrules:
- Kodstil för detta projekt
- Struktur för detta projekt
- Referens: "Se Memory ID 10327035 för UTF-8"

Memory:
- UTF-8 regler (återanvänds i alla projekt)
- Security-First principer (återanvänds i alla projekt)
```

Bästa för: Multi-projekt teams.

### Pattern 2: Detaljerad .cursorrules + Backup i Memory

```
.cursorrules:
- Komplett guide för detta projekt
- Alla regler explicit

Memory:
- De viktigaste reglerna sparade
- För snabb referens mellan sessioner
```

Bästa för: Stora projekt med stabila regler.

### Pattern 3: Minimal .cursorrules + Rich Memory

```
.cursorrules:
- Bara 10 rader
- Huvudsakligen referens till Memory

Memory:
- Detaljerade guider
- Best practices
- Domain-kunskap
```

Bästa för: Etablerade projekt med många agenter.

## Workflow-Exempel: Receptapp

### Dag 1: Initialisering

.cursorrules skapas:
```markdown
# Receptapp Cursor Regler

Security-First utveckling.

## Memory Management
Läs dessa vid sessionstart:
- ID: 10327035 (UTF-8 och Svenska stavning)
- ID: 10327036 (Security-First Design)
```

Memory skapas:
- UTF-8 (ID: 10327035)
- Security-First (ID: 10327036)

### Dag 2: Frontend Developer Session

1. Läs .cursorrules
2. Läs Memory från IDs
3. Implementera URL-input
4. Commit: "References Memory 10327036"

### Dag 3: Security Auditor Session

1. Läs .cursorrules
2. Läs Memory från IDs
3. Auditar implementationen
4. Märker: "Bör lägga till Image Upload Pattern till Memory"

### Dag 4: Backend Developer Session

1. Läs .cursorrules
2. Läs Memory
3. Implementera edge function
4. Uppdatera Memory: "Image Upload Security Pattern"

## Maintenance-Checklist

### Veckovis
- [ ] Är .cursorrules uppdaterad med nya commits?
- [ ] Är Memory IDs refererade i .cursorrules?

### Månatlig
- [ ] Läs alla Memories igen
- [ ] Är de fortfarande relevanta?
- [ ] Behöver uppdateras baserat på nya patterns?

### Kvartalsvis
- [ ] Är några Memories för överhölt?
- [ ] Kan nya Memories skapas för nya patterns?
- [ ] Är .cursorrules och Memory väl organiserade?

## Vanliga Misstag

### Duplicering
```
DÅLIGT: Säkerhetsprinciper i både Memory och .cursorrules
BÄTTRE: Memory innehåller regler, .cursorrules refererar
```

### Ingen Referens
```
DÅLIGT: .cursorrules nämner aldrig Memory
BÄTTRE: "Se Memory ID: 10327036 för Security-First"
```

### Föräldr Memory
```
DÅLIGT: Skapar Memory en gång, uppdaterar aldrig
BÄTTRE: Uppdaterar Memory när nya patterns etableras
```

### För Många IDs
```
DÅLIGT: .cursorrules refererar 20 Memory-poster
BÄTTRE: Refererar bara 3-5 viktigaste
```

## Best Practice: 3-Tier System

### Tier 1: .cursorrules (Session-specifik)
```
- Projektöversikt
- Kodstil för detta projekt
- Struktur för detta projekt
- Referens till Memory
```

### Tier 2: Memory (Global, Långsiktigt)
```
- UTF-8 och stavning
- Security principer
- Domain-kunskap
- Recurring patterns
```

### Tier 3: Dokumentation (Referens)
```
- TECHNICAL.md
- SECURITY.md
- ADRs
- Implementation guides
```

Användning:
- Nya agenter läser .cursorrules först
- Sedan läser Memory enligt referens
- Vid frågor, konsultera Tier 3 dokumentation

## Framtida Integration

### Version 2.0
- Cursor visar Memory-referens i .cursorrules
- Auto-highlight av Memory-IDs i editor
- Quick-jump från ID till Memory-innehål

### Version 3.0
- Automatic Memory-reading baserat på .cursorrules
- Conflict detection mellan Memory och .cursorrules
- Memory versioning och history
