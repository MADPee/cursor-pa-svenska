# Svenska Kodning - UTF-8 Och Best Practices

Guide för att skriva kod på svenska med korrekt UTF-8-hantering.

## UTF-8 Grunderna

Svenska tecken som måste fungera:
- Å (majuskel)
- Ä (majuskel)
- Ö (majuskel)
- å (gemen)
- ä (gemen)
- ö (gemen)

## Kodstil - Svenska Kommentarer

### Variabelnamn (Engelska - Standard)
```swift
let todoTitle = "Handla mat"
let userEmail = "user@example.com"
let isLoading = true
```

### Kommentarer (Svenska - Rekommenderat)

```swift
// Validera email-format enligt RFC 5322
func validateEmail(_ email: String) -> Bool {
    let pattern = "[A-Z0-9a-z._%+-]+@[A-Za-z0-9.-]+\\.[A-Za-z]{2,64}"
    let regex = try! NSRegularExpression(pattern: pattern)
    let range = NSRange(email.startIndex..., in: email)
    return regex.firstMatch(in: email, range: range) != nil
}

// Lagra användarens preferences lokalt
func saveUserPreferences(_ prefs: UserPreferences) {
    let encoder = JSONEncoder()
    let data = try! encoder.encode(prefs)
    UserDefaults.standard.set(data, forKey: "userPrefs")
}
```

## Vanliga Svenska Termer I Kod

### Do's - Tillåtna Svenska Termer

```swift
// Kommentarer på svenska
let receptTitel = "Pannkakor"        // Receptets namn
let ingredienser = ["mjöl", "mjölk"] // Lista över ingredienser
let instruktioner = "Blanda allt"    // Steg-för-steg instruktioner

// Svenska ord i konstanter
let MAX_RECEPT_TITEL = 200
let MATLAGNINGS_TIPPS = ["snabbt", "enkelt"]
```

### Dont's - Felaktig Kodning

```swift
// DÅLIGT: Fel stavning
let sikker_bildbehandling = true      // Bör vara "säker"
let forbattrad_algoritm = false       // Bör vara "förbättrad"
let sakerhetskontroll = true          // Bör vara "säkerhetskontroll"

// DÅLIGT: Emojis i kod
let saker_epostvalidering = true      // Inga emojis
```

## Enhetstester Med Svenska Kommentarer

```swift
class TodoValidatorTests: XCTestCase {
    
    // Testa validering av tom todo-titel
    func testEmptyTitleValidation() {
        let validator = TodoValidator()
        XCTAssertFalse(validator.isValid(title: ""))
    }
    
    // Testa maximal längd på titel
    func testMaxTitleLength() {
        let validator = TodoValidator()
        let longTitle = String(repeating: "a", count: 201)
        XCTAssertFalse(validator.isValid(title: longTitle))
    }
    
    // Testa speciella tecken i titel
    func testSpecialCharactersInTitle() {
        let validator = TodoValidator()
        XCTAssertTrue(validator.isValid(title: "Todo med åäö"))
    }
}
```

## API-Dokumentation Med Svenska

```swift
/// Hämtar användarens sparade recept från servern.
/// 
/// - Parameter userId: Användarens unika identifierare
/// - Returns: Lista över recept eller nil om hämtningen misslyckas
/// - Throws: `APIError` om nätverkskommunikationen misslyckas
/// 
/// Denna funktion är asynkron och kan ta upp till 5 sekunder.
/// Använd denna funktion från huvudtråden för att undvika
/// UI-frysning.
/// 
/// Exempel:
/// ```
/// let recept = try await fetchUserRecipes(userId: "abc123")
/// for recipe in recept {
///     print("Recept: \(recipe.title)")
/// }
/// ```
func fetchUserRecipes(userId: String) async throws -> [Recipe] {
    // Implementation
}
```

## Commit-Meddelanden Med Svenska

```
feat: Lägg till receptvalidering

- Validera recepttitel (max 200 tecken)
- Validera ingredienslista (minst 1 ingrediens)
- Lägg till enhetstester för validering
- Uppdatera API-dokumentation

Fixes #123
```

## Loggning Med Svenska

```swift
// BÄTTRE: Tydliga svenska meddelanden
os_log("Receptet sparades framgångsrikt", log: .default, type: .info)
os_log("Kunde inte hämta recept från servern", log: .default, type: .error)

// Fel meddelanden med kontext
os_log("Validering misslyckades för recepttitel: %{public}@",
       log: .default, type: .error, title)
```

## Felmeddelanden För Användare

```swift
// Användarens fel - svenska meddelanden
let errorMessage = "Recepttiteln kan inte vara längre än 200 tecken"

// Tekniska fel - logg på svenska, visa generisk på UI
os_log("JSON parse error: %@", error.description)
userFacingMessage = "Det uppstod ett fel när receptet sparades"
```

## Naming Conventions

### Variabler (camelCase, Engelska)
```swift
let userEmail = "user@example.com"
let isLoading = true
let numberOfRecipes = 42
```

### Konstanter (UPPERCASE, Engelska eller Svenska)
```swift
let MAX_RECIPE_TITLE = 200
let MIN_INGREDIENTS = 1
let TIMEOUT_SECONDS = 10
```

### Funktioner (camelCase, Engelska)
```swift
func validateRecipeTitle(_ title: String) -> Bool
func saveRecipeLocally(_ recipe: Recipe)
func fetchRecipesFromServer(userId: String) async throws -> [Recipe]
```

### Klasser (PascalCase, Engelska)
```swift
class RecipeValidator
class TodoManager
class APIClient
```

## JSON/API Responses (Engelska - Standard)

```json
{
  "recipe_id": "abc123",
  "recipe_title": "Pannkakor",
  "created_at": "2025-10-25T12:00:00Z",
  "ingredients": ["mjöl", "mjölk", "ägg"],
  "instructions": ["Blanda allt", "Steka på panna"]
}
```

Kommentar i koden:
```swift
// API returnerar receptet med svenska ingredienser och instruktioner
let recipe = try decoder.decode(Recipe.self, from: jsonData)
```

## Best Practices Sammanfattning

Do's:
- Svenska kommentarer för klarhet
- Korrekt UTF-8 stavning (Å, Ä, Ö)
- Engelska variabel- och funktionsnamn
- Svenska felmeddelanden för användare
- Svenska i dokumentation och commits

Dont's:
- Fel stavning (sikker, forbattrad, etc.)
- Emojis i kod
- Blandad svenska/engelska i samma namn
- Kodad UTF-8 (alltid korrekt stavning direkt)
- Hardkodade felmeddelanden

## Checklist

- [ ] Alla kommentarer på svenska med korrekt stavning
- [ ] Variabelnamn på engelska (camelCase)
- [ ] Funktionsnamn på engelska (camelCase)
- [ ] UTF-8 tecken funkar: Å, Ä, Ö
- [ ] Inga emojis i kod
- [ ] Enhetstester med svenska kommentarer
- [ ] API-dokumentation på svenska
- [ ] Commit-meddelanden på svenska
