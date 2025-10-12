# Colossal.Localization.LocalizationDictionary

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private Colossal.Logging.ILog log`  
- `private readonly System.String <localeID>k__BackingField`  
- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationDictionary+Entry> m_Dict`  
- `private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <indexCounts>k__BackingField`  

## Properties

- `public System.String localeID { get }`  
- `public System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts { get }`  
- `public System.Int32 entryCount { get }`  
- `public System.Collections.Generic.IEnumerable<System.String> entryIDs { get }`  
- `public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries { get }`  

## Constructors

- `public LocalizationDictionary(System.String localeID)`  

## Methods

- `public Add(System.String entryID, System.String value, System.Boolean fallback = False) : System.Void`  
- `public Clear() : System.Void`  
- `public ContainsID(System.String entryID, System.Boolean ignoreFallbackEntries = False) : System.Boolean`  
- `public GetIndexedLocaleIDs(System.String localeID) : System.String[]`  
- `public MergeFrom(Colossal.Localization.LocalizationDictionary other, System.Boolean fallback) : System.Void`  
- `public TryGetValue(System.String entryID, System.String& value) : System.Boolean`  

## Nested types

- `Colossal.Localization.LocalizationDictionary+Entry`  
- `Colossal.Localization.LocalizationDictionary+<get_entries>d__18`  

