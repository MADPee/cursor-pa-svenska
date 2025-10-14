# IntelliSense-dialogs

Cursor analyserar automatiskt ditt projekt och föreslår konfigurationer för bättre kodkomplettering och felhantering.

## C++ IntelliSense Dialog

### Vad händer?

Cursor upptäcker att ditt projekt har en `Makefile` och föreslår att konfigurera C++ IntelliSense för bättre kodkomplettering och felhantering.

### När klicka "Yes"?

**För C/C++ projekt:**
- Native iOS/Android libraries
- Game engines (Unity, Unreal)
- System programming
- Embedded development
- Cross-platform C++ libraries

**För mixed language projects:**
- Swift + C++ bridges
- Objective-C++ (.mm files)
- JNI (Java Native Interface)
- Python C extensions

### När klicka "No"?

**För rent Swift/iOS projekt:**
- Som Familjetavlan (100% Swift/SwiftUI)
- Makefile används för Swift build automation
- Ingen C++ kod i projektet

**För andra språk:**
- JavaScript/TypeScript projekt
- Python projekt
- Web development (HTML/CSS/JS)

## Praktiskt exempel

### Scenario: Swift-projekt med Makefile

```
Dialog: "Would you like to configure C++ IntelliSense for this workspace using information from your Makefiles?"

Svar: Klicka "No"

Anledning: 
- Projektet är 100% Swift
- Makefile används för automation (build, test, QA)
- C++ IntelliSense ger ingen fördel
```

### Scenario: C++ projekt

```
Dialog: "Would you like to configure C++ IntelliSense for this workspace using information from your Makefiles?"

Svar: Klicka "Yes"

Anledning:
- Projektet innehåller .cpp/.hpp filer
- Makefile kompilerar C++ kod
- IntelliSense förbättrar kodkomplettering
```

## Cursor's intelligens

Cursor analyserar automatiskt:
- Projektstruktur
- Makefile innehåll
- Filtyper i workspace
- Dependencies

Den föreslår bara C++ IntelliSense när det faktiskt finns C++ kod eller build-konfigurationer som indikerar C++ usage.

## Tips

- **Läs dialogen noggrant** - Cursor förklarar vad den föreslår
- **Känn ditt projekt** - vet vilka språk du använder
- **Du kan ändra senare** - konfigurationen går att justera i settings
- **Fokusera på ditt språk** - välj IntelliSense för språk du faktiskt använder

## Andra IntelliSense-dialogs

Cursor kan föreslå konfiguration för:
- TypeScript
- Python
- Rust
- Go
- Andra språk baserat på projektstruktur

Samma princip gäller - klicka "Yes" för språk du använder, "No" för språk du inte använder.