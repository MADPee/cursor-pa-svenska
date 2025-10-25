# Agent-Ansvar - Arbetsmönster För AI-Agenter

Denna guide förklarar hur AI-agenter bör hantera långsiktigt arbete och kunskap-management i Cursor.

## Vad är En Agent?

I denna kontext: en AI-modell som assisterar under en session med specifik roll (Frontend Developer, Security Auditor, etc.).

## Typ 1: Single-Session Agent

Agenten arbetar bara denna session, resultaten sparas på disk.

### Agent-Ansvar

1. Läs projektets regler
   - .cursorrules
   - Befintlig dokumentation
   - Tidigare beslut (ADRs)

2. Utför Uppgiften
   - Implementera feature
   - Refaktorera kod
   - Fixa buggar

3. Dokumentera Ändringar
   - Commit-meddelanden
   - Uppdatera README
   - Lägg till comments

4. Verifiera Kvalitet
   - TypeScript kompilering
   - ESLint passar
   - Build-test

### Exempel: Frontend Developer Agent

```
Session start:
- Läs .cursorrules för kodstil
- Läs befintliga komponenter för mönster
- Förstå projektstruktur

Implementation:
- Skapa AddRecipeUrlDialog.tsx
- Följa kodstil från .cursorrules
- Uppdatera Dashboard.tsx

Quality Check:
- TypeScript compilation passa
- ESLint passa
- Commit med beskrivande meddelande
```

## Typ 2: Multi-Session Agent (Med Memory)

Agenten arbetar över flera sessioner och använder Memory för persistent kunskap.

### Agent-Ansvar

1. Vid Sessionsstart
   - Läs relevanta Memory-poster
   - Läs .cursorrules
   - Förstå tidigare beslut

2. Under Arbetet
   - Applicera kunskap från Memory
   - Följa etablerade mönster
   - Dokumentera ändringar

3. Lägg Märke Till Ny Kunskap
   - Är detta långsiktigt värde?
   - Bör det sparas i Memory?
   - Uppdatera Memory om relevant

4. Dokumentera För Nästa Session
   - Descriptiv commit-meddelande
   - Uppdatera relevanta dokumentation
   - Referera Memory-IDs om relevant

### Exempel: Security Auditor Agent

```
Session 1:
- Läs Memory: "Security-First Design"
- Auditar edge function
- Skapar Memory: "SSRF-protection pattern"
- Dokumenterar i SECURITY_AUDIT_REPORT.md

Session 2 (Senare):
- Läs tidigare Memory
- Auditar ny feature
- Applicerar tidigare pattern
- Uppdaterar Memory med nya fynd
```

## Memory-Management För Agenter

### När Att Skapa Memory
- Efter 2-3 sessioner av samma typ av arbete
- En återkommande pattern är etablerad
- Det finns långsiktigt värde för framtida sessioner

### Format För Memory-Skapande
1. Identifiera mönstret
2. Dokumentera i commit-meddelande
3. Skapa Memory med `update_memory` tool
4. Referera Memory-ID i kod/dokumentation

### Commit-Meddelande Med Memory
```
feat: Add image optimization edge function

- Implement optimize-and-upload-image function
- Security controls: SSRF, size limit, timeout
- Image optimization with Sharp library

Memory Updated:
- ID: 10327036 (Security-First Design)
- Added: Image upload security pattern
```

## Arbeitsflöde För Multi-Agent Handoff

### Agent 1: Frontend Developer
```
1. Läs .cursorrules
2. Implementera feature
3. Commit: "feat: Add URL input component"
```

### Handoff Till Agent 2: Security Auditor
```
1. Läs .cursorrules
2. Läs Previous Commit
3. Auditar implementationen
4. Commit: "security: Audit URL input feature"
5. Om relevant: Skapa eller uppdatera Security Memory
```

### Handoff Till Agent 3: Testing Agent
```
1. Läs .cursorrules
2. Läs Previous Audits
3. Skriver tester
4. Commit: "test: Add URL input E2E tests"
```

## Ansvar Vid Fel

Om en agent hittar ett problem från en tidigare agent:

1. Loggat Det
   ```
   Issue: Security check missing in Component X
   Introduced by: Frontend Developer (commit ABC123)
   ```

2. Dokumenterat Varför Det Hände
   ```
   Reason: Security pattern inte känd vid tillfället
   ```

3. Fixat Det
   ```
   Fix: Lägg till validation per .cursorrules
   ```

4. Uppdaterat Memory Om Relevant
   ```
   Memory: "Security checklist för URL input"
   ```

## Checklist - Agent-Ansvar

### Vid Sessionsstart
- [ ] Läs .cursorrules
- [ ] Läs relevanta Memory-poster
- [ ] Förstå projektstruktur
- [ ] Läs tidigare beslut (ADRs, commits)

### Under Arbetet
- [ ] Applicera kunskap från .cursorrules
- [ ] Följa etablerade kodmönster
- [ ] Uppdatera dokumentation vid ändringar
- [ ] Verifiera quality (lint, test, build)

### Vid Sessionsslut
- [ ] Descriptiv commit-meddelande
- [ ] Uppdatera README/docs om relevant
- [ ] Märk ny kunskap för Memory
- [ ] Referera Memory-IDs i dokumentation

## Exempel: Receptapp Agent Workflow

### Dag 1: Frontend Developer
```
- Läs .cursorrules (UTF-8, Security-First)
- Läs Memory: "Security-First Design"
- Implementera AddRecipeUrlDialog.tsx
- Commit med: "References Memory ID: 10327036"
```

### Dag 2: Backend Developer
```
- Läs .cursorrules
- Läs Memory från dag 1
- Implementera optimize-and-upload-image
- Märker: "SSRF-pattern bör sparas i Memory"
```

### Dag 3: Security Auditor
```
- Läs .cursorrules
- Läs all Memory
- Auditar både komponenter
- Uppdaterar Memory: "Image upload security"
- Skapar: SECURITY_AUDIT_REPORT.md
```

## Framtida Optimering

### Version 2.0
- Automated checklist per agent-typ
- Memory-reading built-in i prompts
- Auto-generate commit messages

### Version 3.0
- Multi-agent coordination
- Automatic handoff detection
- Knowledge graph för Memory
