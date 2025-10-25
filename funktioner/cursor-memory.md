# Cursor Memory - Persistent Knowledge Base

Cursor Memory är en funktion som sparar kunskap mellan sessioner. Perfekt för långsiktiga projekt och återkommande mönster.

## Vad är Cursor Memory?

En persistent knowledge base som följer dig mellan alla sessioner. I motsatts till .cursorrules som är projekt-specifik, är Memory användar-global.

## När Använda Memory

Spara kunskap om:
- Långsiktiga arkitektur-beslut
- Projektspecifika best practices
- Återkommande problem-lösningar
- Domain-kunskap (allergener, recept, etc.)
- Agent-arbetsflöden

## När INTE Använda Memory

- Code snippets (använd .cursorrules istället)
- Temporära workarounds
- Information som redan dokumenteras
- En-gångs-problem

## Hur Man Skapar Memory

### Steg 1: Öppna Memory
I Cursor IDE, klicka på Memory-ikonen (eller använd Command Palette)

### Steg 2: Skapa Ny Memory
```
Title: [Kort beskrivning, max 5 ord]
Knowledge: [Innehål, max ca 300 ord]
```

### Exempel - Säker Edge Function Pattern

```
Title: "Edge Function Security Pattern"

Knowledge: "Alla Edge Functions i Receptapp MÅSTE ha:
1. JWT-autentisering via supabase.auth.getUser()
2. Input-validering med typ-kontroll
3. SSRF-skydd med domain-whitelist
4. Timeout-skydd (10 sekunder max)
5. Safe error handling utan dataleakage
6. verify_jwt=true i config.toml"
```

## Best Practices

### Håll Det Kort
- En huvudidé per memory
- Max två meningar
- Konkreta exempel

### Använd Tydligt Språk
- Svenska utan emojis
- Actionable information
- Undvik vaga beskrivningar

### Organisera Med Kategorier
- Prefix title med kategori
- Exempel: "Security: ...", "Pattern: ...", "Domain: ..."

## Integration Med .cursorrules

.cursorrules bör referera till memories:

```markdown
# Memory Management
Läs dessa memories vid sessionstart:
- UTF-8 och Svenska stavning
- Security-First Design
- Domain-kunskap för Receptapp
```

## Maintenance

### Månadlig Review
- Läs alla memories igen
- Är de fortfarande relevanta?
- Behöver uppdateras?
- Ta bort överhölt kunskap

### Sessionstart Checklist
- Läs relevanta memories
- Applicera kunskapen konsekvent
- Uppdatera memories vid ny kunskap

## Exempel - Receptapp Memories

### Memory 1: UTF-8 Och Svenska Stavning
```
Title: UTF-8 och Svenska stavning

Knowledge: Receptapp är svenskt projekt med UTF-8-krav.
Alltid: säker (inte sikker), förbättrad (inte forbattrad),
säkerhetsdömen. Svenska tecken Å, Ä, Ö obligatoriska.
Inga emojis i output. Läs .cursorrules före innehållsgenering.
```

### Memory 2: Security-First Design
```
Title: Security-First Design

Knowledge: Receptapp bygger på Security-First arkitektur.
Edge Functions MÅSTE ha: JWT-auth, input-validering,
SSRF-skydd, timeout, safe error handling. Security Auditor
Agent har veto-rätt. RLS-policyer och SECURITY DEFINER inte optional.
```

## Vanliga Misstag

### För Långt
```
DÅLIGT: Sparar hela arkitektur-guiden som memory
BÄTTRE: Sparar bara huvudprinciperna
```

### För Vagt
```
DÅLIGT: "Gör saker säkert"
BÄTTRE: "SSRF-skydd med domain-whitelist för externa URLs"
```

### Uppdateras Aldrig
```
DÅLIGT: Skaper memory en gång, använder aldrig igen
BÄTTRE: Läser memories varje session, uppdaterar vid ändringar
```

## Nästa Steg

1. Identifiera dina viktigaste mönster
2. Skapa memories för långsiktiga regler
3. Referera memories i .cursorrules
4. Uppdatera månatligen
