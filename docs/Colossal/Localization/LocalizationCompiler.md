# Colossal.Localization.LocalizationCompiler

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly System.String m_RawPath`  
- `private readonly System.String m_CompiledPath`  
- `private readonly Colossal.Logging.ILog m_Log`  
- `private static const System.String kFallbackLocaleID`  

## Constructors

- `public LocalizationCompiler(System.String rawPath, System.String compiledPath, Colossal.Logging.ILog log)`  

## Methods

- `private AddLanguageEntries(System.Collections.Generic.List<Colossal.Localization.LocalizationCompiler+LocaleInfo> localeInfos) : System.Void`  
- `private Load(System.String localeID, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries) : System.Boolean`  
- `private LoadAndValidate(System.String localeID, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts, System.Collections.Generic.List<Colossal.Localization.LocalizationEntry> fallbackEntries, System.String& systemLanguage, System.String& localizedName, System.Collections.Generic.List`1[[Colossal.Localization.LocalizationEntry, Colossal.Localization, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& entries) : System.Boolean`  
- `private LoadLocaleSource(Colossal.IDictionarySource source) : System.Collections.Generic.List<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  
- `public ValidateAndCompileLocales(System.Collections.Generic.HashSet<System.String> localeIDs, System.Boolean exportToTs) : System.Void`  
- `private ValidEntries(Colossal.Localization.LocalizationCompiler+LocaleInfo info) : System.Collections.Generic.IEnumerable<Colossal.Localization.LocalizationEntry>`  
- `private WriteLocale(Colossal.Localization.LocalizationCompiler+LocaleInfo info) : System.Void`  

## Nested types

- `Colossal.Localization.LocalizationCompiler+LocaleInfo`  
- `Colossal.Localization.LocalizationCompiler+<>c`  
- `Colossal.Localization.LocalizationCompiler+<ValidEntries>d__11`  

