# Colossal.Localization.TypeScriptLocalizationCodeGenerator

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TypeScriptLocalizationCodeGenerator
{
    private static System.Void AppendEntry(System.Text.StringBuilder s, System.String group, Colossal.Localization.TypeScriptLocalizationCodeGenerator+EntryInfo entryInfo);
    private static System.Void AppendGroup(System.Text.StringBuilder s, Colossal.Localization.TypeScriptLocalizationCodeGenerator+GroupInfo group, System.Int32 indentLevel);
    private static System.Void AppendIndent(System.Text.StringBuilder s, System.Int32 indentLevel);
    public static System.String GenerateCode(System.Collections.Generic.IEnumerable<Colossal.Localization.LocalizationEntry> entries, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
}
```


## Methods

- `private static AppendEntry(System.Text.StringBuilder s, System.String group, Colossal.Localization.TypeScriptLocalizationCodeGenerator+EntryInfo entryInfo) : System.Void`  

```csharp
private static System.Void AppendEntry(System.Text.StringBuilder s, System.String group, Colossal.Localization.TypeScriptLocalizationCodeGenerator+EntryInfo entryInfo);
```

- `private static AppendGroup(System.Text.StringBuilder s, Colossal.Localization.TypeScriptLocalizationCodeGenerator+GroupInfo group, System.Int32 indentLevel) : System.Void`  

```csharp
private static System.Void AppendGroup(System.Text.StringBuilder s, Colossal.Localization.TypeScriptLocalizationCodeGenerator+GroupInfo group, System.Int32 indentLevel);
```

- `private static AppendIndent(System.Text.StringBuilder s, System.Int32 indentLevel) : System.Void`  

```csharp
private static System.Void AppendIndent(System.Text.StringBuilder s, System.Int32 indentLevel);
```

- `public static GenerateCode(System.Collections.Generic.IEnumerable<Colossal.Localization.LocalizationEntry> entries, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.String`  

```csharp
public static System.String GenerateCode(System.Collections.Generic.IEnumerable<Colossal.Localization.LocalizationEntry> entries, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
```


## Nested types

- `Colossal.Localization.TypeScriptLocalizationCodeGenerator+GroupInfo`  
- `Colossal.Localization.TypeScriptLocalizationCodeGenerator+EntryInfo`  

