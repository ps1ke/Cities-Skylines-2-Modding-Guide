# Colossal.Localization.HeaderCsvFileSource

**Assembly:** `Colossal.Localization`  
**Namespace:** `Colossal.Localization`  

**Type:** class public  

**Base:** `Colossal.Localization.CSVFileSource`  
**Implements:** `Colossal.IDictionarySource`  

## Code

```csharp
public class HeaderCsvFileSource : Colossal.Localization.CSVFileSource, Colossal.IDictionarySource
{
    private System.String <keyColumnHeader>k__BackingField;
    private System.String <valueColumnHeader>k__BackingField;
    private System.Int32 <headerRowIndex>k__BackingField;

    public System.String keyColumnHeader { get; set; }
    public System.String valueColumnHeader { get; set; }
    public System.Int32 headerRowIndex { get; set; }

    public HeaderCsvFileSource();

    protected virtual System.Void GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex);
}
```


## Fields

- `private System.String <keyColumnHeader>k__BackingField`  

```csharp
private System.String <keyColumnHeader>k__BackingField;
```

- `private System.String <valueColumnHeader>k__BackingField`  

```csharp
private System.String <valueColumnHeader>k__BackingField;
```

- `private System.Int32 <headerRowIndex>k__BackingField`  

```csharp
private System.Int32 <headerRowIndex>k__BackingField;
```


## Properties

- `public System.String keyColumnHeader { get; set }`  

```csharp
public System.String keyColumnHeader { get; set; }
```

- `public System.String valueColumnHeader { get; set }`  

```csharp
public System.String valueColumnHeader { get; set; }
```

- `public System.Int32 headerRowIndex { get; set }`  

```csharp
public System.Int32 headerRowIndex { get; set; }
```


## Constructors

- `public HeaderCsvFileSource()`  

```csharp
public HeaderCsvFileSource();
```


## Methods

- `protected virtual GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex) : System.Void`  

```csharp
protected virtual System.Void GetIndices(System.Collections.Generic.List<System.String[]> rows, System.Int32& keyColumnIndex, System.Int32& valueColumnIndex, System.Int32& startRowIndex);
```


