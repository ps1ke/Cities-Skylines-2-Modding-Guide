# Colossal.Localization.MemorySource

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.IDictionarySource`  

## Code

```csharp
public class MemorySource : Colossal.IDictionarySource
{
    private readonly System.Collections.Generic.Dictionary<System.String, System.String> m_Dict;

    public MemorySource(System.Collections.Generic.Dictionary<System.String, System.String> dict);

    public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
    public System.Void Unload();
}
```


## Fields

- `private readonly System.Collections.Generic.Dictionary<System.String, System.String> m_Dict`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, System.String> m_Dict;
```


## Constructors

- `public MemorySource(System.Collections.Generic.Dictionary<System.String, System.String> dict)`  

```csharp
public MemorySource(System.Collections.Generic.Dictionary<System.String, System.String> dict);
```


## Methods

- `public ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  

```csharp
public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
```

- `public Unload() : System.Void`  

```csharp
public System.Void Unload();
```


