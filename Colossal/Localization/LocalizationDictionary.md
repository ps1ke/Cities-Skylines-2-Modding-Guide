# Colossal.Localization.LocalizationDictionary

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class LocalizationDictionary
{
    private Colossal.Logging.ILog log;
    private readonly System.String <localeID>k__BackingField;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationDictionary+Entry> m_Dict;
    private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <indexCounts>k__BackingField;

    public System.String localeID { get; }
    public System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts { get; }
    public System.Int32 entryCount { get; }
    public System.Collections.Generic.IEnumerable<System.String> entryIDs { get; }
    public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries { get; }

    public LocalizationDictionary(System.String localeID);

    public System.Void Add(System.String entryID, System.String value, System.Boolean fallback);
    public System.Void Clear();
    public System.Boolean ContainsID(System.String entryID, System.Boolean ignoreFallbackEntries);
    public System.String[] GetIndexedLocaleIDs(System.String localeID);
    public System.Void MergeFrom(Colossal.Localization.LocalizationDictionary other, System.Boolean fallback);
    public System.Boolean TryGetValue(System.String entryID, System.String& value);
}
```


## Fields

- `private Colossal.Logging.ILog log`  

```csharp
private Colossal.Logging.ILog log;
```

- `private readonly System.String <localeID>k__BackingField`  

```csharp
private readonly System.String <localeID>k__BackingField;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationDictionary+Entry> m_Dict`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Localization.LocalizationDictionary+Entry> m_Dict;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <indexCounts>k__BackingField`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.Int32> <indexCounts>k__BackingField;
```


## Properties

- `public System.String localeID { get }`  

```csharp
public System.String localeID { get; }
```

- `public System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts { get }`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts { get; }
```

- `public System.Int32 entryCount { get }`  

```csharp
public System.Int32 entryCount { get; }
```

- `public System.Collections.Generic.IEnumerable<System.String> entryIDs { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.String> entryIDs { get; }
```

- `public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries { get }`  

```csharp
public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> entries { get; }
```


## Constructors

- `public LocalizationDictionary(System.String localeID)`  

```csharp
public LocalizationDictionary(System.String localeID);
```


## Methods

- `public Add(System.String entryID, System.String value, System.Boolean fallback = False) : System.Void`  

```csharp
public System.Void Add(System.String entryID, System.String value, System.Boolean fallback);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public ContainsID(System.String entryID, System.Boolean ignoreFallbackEntries = False) : System.Boolean`  

```csharp
public System.Boolean ContainsID(System.String entryID, System.Boolean ignoreFallbackEntries);
```

- `public GetIndexedLocaleIDs(System.String localeID) : System.String[]`  

```csharp
public System.String[] GetIndexedLocaleIDs(System.String localeID);
```

- `public MergeFrom(Colossal.Localization.LocalizationDictionary other, System.Boolean fallback) : System.Void`  

```csharp
public System.Void MergeFrom(Colossal.Localization.LocalizationDictionary other, System.Boolean fallback);
```

- `public TryGetValue(System.String entryID, System.String& value) : System.Boolean`  

```csharp
public System.Boolean TryGetValue(System.String entryID, System.String& value);
```


## Nested types

- `Colossal.Localization.LocalizationDictionary+Entry`  
- `Colossal.Localization.LocalizationDictionary+<get_entries>d__18`  

