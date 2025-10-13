# Colossal.IDictionarySource

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IDictionarySource
{
    public abstract System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
    public abstract System.Void Unload();
}
```


## Methods

- `public abstract ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  

```csharp
public abstract System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
```

- `public abstract Unload() : System.Void`  

```csharp
public abstract System.Void Unload();
```


