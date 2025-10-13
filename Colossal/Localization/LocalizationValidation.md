# Colossal.Localization.LocalizationValidation

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class LocalizationValidation
{
    private static readonly System.Text.RegularExpressions.Regex kIdentifierPlain;
    private static readonly System.Text.RegularExpressions.Regex kIdentifierHashed;
    private static readonly System.Text.RegularExpressions.Regex kIdentifierIndexed;
    private static readonly System.Text.RegularExpressions.Regex kIdentifierHashedIndexed;
    private static readonly System.Text.RegularExpressions.Regex kSubstitutePlaceholder;

    private static System.Collections.Generic.List<System.String> GetArgNames(System.String text);
    public static System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> ParseEntries(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries, Colossal.Logging.ILog log);
    public static Colossal.Localization.LocalizationEntry ParseEntry(System.Collections.Generic.KeyValuePair<System.String, System.String> entry);
    private static System.Boolean ValidateArgNames(System.Collections.Generic.List<System.String> argNames, System.Collections.Generic.List<System.String> expected);
    public static System.Void ValidateEntries(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, Colossal.Logging.ILog log, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
    private static System.Boolean ValidateEntry(System.String localeID, Colossal.Localization.LocalizationEntry entry, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> existingEntries, Colossal.Logging.ILog log);
    private static System.Void ValidateIndices(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> group, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, Colossal.Logging.ILog log);
    public static System.Void ValidateTranslation(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> referenceEntries, Colossal.Logging.ILog log);
}
```


## Fields

- `private static readonly System.Text.RegularExpressions.Regex kIdentifierPlain`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kIdentifierPlain;
```

- `private static readonly System.Text.RegularExpressions.Regex kIdentifierHashed`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kIdentifierHashed;
```

- `private static readonly System.Text.RegularExpressions.Regex kIdentifierIndexed`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kIdentifierIndexed;
```

- `private static readonly System.Text.RegularExpressions.Regex kIdentifierHashedIndexed`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kIdentifierHashedIndexed;
```

- `private static readonly System.Text.RegularExpressions.Regex kSubstitutePlaceholder`  

```csharp
private static readonly System.Text.RegularExpressions.Regex kSubstitutePlaceholder;
```


## Methods

- `private static GetArgNames(System.String text) : System.Collections.Generic.List<System.String>`  

```csharp
private static System.Collections.Generic.List<System.String> GetArgNames(System.String text);
```

- `public static ParseEntries(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries, Colossal.Logging.ILog log) : System.Collections.Generic.List<Colossal.Localization.LocalizationEntry>`  

```csharp
public static System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> ParseEntries(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries, Colossal.Logging.ILog log);
```

- `public static ParseEntry(System.Collections.Generic.KeyValuePair<System.String, System.String> entry) : Colossal.Localization.LocalizationEntry`  

```csharp
public static Colossal.Localization.LocalizationEntry ParseEntry(System.Collections.Generic.KeyValuePair<System.String, System.String> entry);
```

- `private static ValidateArgNames(System.Collections.Generic.List<System.String> argNames, System.Collections.Generic.List<System.String> expected) : System.Boolean`  

```csharp
private static System.Boolean ValidateArgNames(System.Collections.Generic.List<System.String> argNames, System.Collections.Generic.List<System.String> expected);
```

- `public static ValidateEntries(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, Colossal.Logging.ILog log, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Void`  

```csharp
public static System.Void ValidateEntries(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, Colossal.Logging.ILog log, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
```

- `private static ValidateEntry(System.String localeID, Colossal.Localization.LocalizationEntry entry, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> existingEntries, Colossal.Logging.ILog log) : System.Boolean`  

```csharp
private static System.Boolean ValidateEntry(System.String localeID, Colossal.Localization.LocalizationEntry entry, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> existingEntries, Colossal.Logging.ILog log);
```

- `private static ValidateIndices(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> group, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, Colossal.Logging.ILog log) : System.Void`  

```csharp
private static System.Void ValidateIndices(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> group, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, Colossal.Logging.ILog log);
```

- `public static ValidateTranslation(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> referenceEntries, Colossal.Logging.ILog log) : System.Void`  

```csharp
public static System.Void ValidateTranslation(System.String localeID, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> entries, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> referenceEntries, Colossal.Logging.ILog log);
```


