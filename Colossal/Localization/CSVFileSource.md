# Colossal.Localization.CSVFileSource

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.IDictionarySource`  

## Code

```csharp
public abstract class CSVFileSource : Colossal.IDictionarySource
{
    private System.String <filePath>k__BackingField;
    private System.Char <columnDelimiter>k__BackingField;

    public System.String filePath { get; set; }
    public System.Char columnDelimiter { get; set; }

    protected CSVFileSource();

    protected abstract System.Void GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex);
    public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
    protected System.String[] SplitLine(System.String line);
    public virtual System.String ToString();
    public System.Void Unload();
}
```


## Fields

- `private System.String <filePath>k__BackingField`  

```csharp
private System.String <filePath>k__BackingField;
```

- `private System.Char <columnDelimiter>k__BackingField`  

```csharp
private System.Char <columnDelimiter>k__BackingField;
```


## Properties

- `public System.String filePath { get; set }`  

```csharp
public System.String filePath { get; set; }
```

- `public System.Char columnDelimiter { get; set }`  

```csharp
public System.Char columnDelimiter { get; set; }
```


## Constructors

- `protected CSVFileSource()`  

```csharp
protected CSVFileSource();
```


## Methods

- `protected abstract GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex) : System.Void`  

```csharp
protected abstract System.Void GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex);
```

- `public ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  

```csharp
public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
```

- `protected SplitLine(System.String line) : System.String[]`  

```csharp
protected System.String[] SplitLine(System.String line);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `public Unload() : System.Void`  

```csharp
public System.Void Unload();
```


## Nested types

- `Colossal.Localization.CSVFileSource+<ReadEntries>d__8`  

