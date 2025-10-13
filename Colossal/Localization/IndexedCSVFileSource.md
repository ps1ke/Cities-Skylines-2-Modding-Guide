# Colossal.Localization.IndexedCSVFileSource

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `Colossal.Localization.CSVFileSource`  
**Implements:** `Colossal.IDictionarySource`  

## Code

```csharp
public class IndexedCSVFileSource : Colossal.Localization.CSVFileSource, Colossal.IDictionarySource
{
    private System.Int32 <keyColumn>k__BackingField;
    private System.Int32 <valueColumn>k__BackingField;
    private System.Int32 <startRow>k__BackingField;

    public System.Int32 keyColumn { get; set; }
    public System.Int32 valueColumn { get; set; }
    public System.Int32 startRow { get; set; }

    public IndexedCSVFileSource();

    protected virtual System.Void GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex);
}
```


## Fields

- `private System.Int32 <keyColumn>k__BackingField`  

```csharp
private System.Int32 <keyColumn>k__BackingField;
```

- `private System.Int32 <valueColumn>k__BackingField`  

```csharp
private System.Int32 <valueColumn>k__BackingField;
```

- `private System.Int32 <startRow>k__BackingField`  

```csharp
private System.Int32 <startRow>k__BackingField;
```


## Properties

- `public System.Int32 keyColumn { get; set }`  

```csharp
public System.Int32 keyColumn { get; set; }
```

- `public System.Int32 valueColumn { get; set }`  

```csharp
public System.Int32 valueColumn { get; set; }
```

- `public System.Int32 startRow { get; set }`  

```csharp
public System.Int32 startRow { get; set; }
```


## Constructors

- `public IndexedCSVFileSource()`  

```csharp
public IndexedCSVFileSource();
```


## Methods

- `protected virtual GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex) : System.Void`  

```csharp
protected virtual System.Void GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex);
```


