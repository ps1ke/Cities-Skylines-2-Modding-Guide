# Colossal.Localization.LocalizationCompiler

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class LocalizationCompiler
{
    private readonly System.String m_RawPath;
    private readonly System.String m_CompiledPath;
    private readonly Colossal.Logging.ILog m_Log;
    private static const System.String kFallbackLocaleID;

    public LocalizationCompiler(System.String rawPath, System.String compiledPath, Colossal.Logging.ILog log);

    private System.Void AddLanguageEntries(System.Collections.Generic.List<Colossal.Localization.LocalizationCompiler+LocaleInfo> localeInfos);
    private System.Boolean Load(System.String localeID, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries);
    private System.Boolean LoadAndValidate(System.String localeID, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> fallbackEntries, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries);
    private System.Collections.Generic.List<System.Collections.Generic.KeyValuePair<System.String, System.String>> LoadLocaleSource(Colossal.IDictionarySource source);
    public System.Void ValidateAndCompileLocales(System.Collections.Generic.HashSet<System.String> localeIDs, System.Boolean exportToTs);
    private System.Collections.Generic.IEnumerable<Colossal.Localization.LocalizationEntry> ValidEntries(Colossal.Localization.LocalizationCompiler+LocaleInfo info);
    private System.Void WriteLocale(Colossal.Localization.LocalizationCompiler+LocaleInfo info);
}
```


## Fields

- `private readonly System.String m_RawPath`  

```csharp
private readonly System.String m_RawPath;
```

- `private readonly System.String m_CompiledPath`  

```csharp
private readonly System.String m_CompiledPath;
```

- `private readonly Colossal.Logging.ILog m_Log`  

```csharp
private readonly Colossal.Logging.ILog m_Log;
```

- `private static const System.String kFallbackLocaleID`  

```csharp
private static const System.String kFallbackLocaleID;
```


## Constructors

- `public LocalizationCompiler(System.String rawPath, System.String compiledPath, Colossal.Logging.ILog log)`  

```csharp
public LocalizationCompiler(System.String rawPath, System.String compiledPath, Colossal.Logging.ILog log);
```


## Methods

- `private AddLanguageEntries(System.Collections.Generic.List<Colossal.Localization.LocalizationCompiler+LocaleInfo> localeInfos) : System.Void`  

```csharp
private System.Void AddLanguageEntries(System.Collections.Generic.List<Colossal.Localization.LocalizationCompiler+LocaleInfo> localeInfos);
```

- `private Load(System.String localeID, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries) : System.Boolean`  

```csharp
private System.Boolean Load(System.String localeID, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries);
```

- `private LoadAndValidate(System.String localeID, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> fallbackEntries, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries) : System.Boolean`  

```csharp
private System.Boolean LoadAndValidate(System.String localeID, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> fallbackEntries, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries);
```

- `private LoadLocaleSource(Colossal.IDictionarySource source) : System.Collections.Generic.List<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  

```csharp
private System.Collections.Generic.List<System.Collections.Generic.KeyValuePair<System.String, System.String>> LoadLocaleSource(Colossal.IDictionarySource source);
```

- `public ValidateAndCompileLocales(System.Collections.Generic.HashSet<System.String> localeIDs, System.Boolean exportToTs) : System.Void`  

```csharp
public System.Void ValidateAndCompileLocales(System.Collections.Generic.HashSet<System.String> localeIDs, System.Boolean exportToTs);
```

- `private ValidEntries(Colossal.Localization.LocalizationCompiler+LocaleInfo info) : System.Collections.Generic.IEnumerable<Colossal.Localization.LocalizationEntry>`  

```csharp
private System.Collections.Generic.IEnumerable<Colossal.Localization.LocalizationEntry> ValidEntries(Colossal.Localization.LocalizationCompiler+LocaleInfo info);
```

- `private WriteLocale(Colossal.Localization.LocalizationCompiler+LocaleInfo info) : System.Void`  

```csharp
private System.Void WriteLocale(Colossal.Localization.LocalizationCompiler+LocaleInfo info);
```


## Nested types

- `Colossal.Localization.LocalizationCompiler+LocaleInfo`  
- `Colossal.Localization.LocalizationCompiler+<>c`  
- `Colossal.Localization.LocalizationCompiler+<ValidEntries>d__11`  

