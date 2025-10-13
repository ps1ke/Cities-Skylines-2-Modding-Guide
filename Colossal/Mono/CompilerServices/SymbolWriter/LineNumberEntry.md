# Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class LineNumberEntry
{
    public readonly System.Int32 Row;
    public System.Int32 Column;
    public System.Int32 EndRow;
    public System.Int32 EndColumn;
    public readonly System.Int32 File;
    public readonly System.Int32 Offset;
    public readonly System.Boolean IsHidden;
    public static readonly Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry Null;

    public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 offset);
    public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 offset);
    public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 offset, System.Boolean is_hidden);
    public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 end_row, System.Int32 end_column, System.Int32 offset, System.Boolean is_hidden);

    public virtual System.String ToString();
}
```


## Fields

- `public readonly System.Int32 Row`  

```csharp
public readonly System.Int32 Row;
```

- `public System.Int32 Column`  

```csharp
public System.Int32 Column;
```

- `public System.Int32 EndRow`  

```csharp
public System.Int32 EndRow;
```

- `public System.Int32 EndColumn`  

```csharp
public System.Int32 EndColumn;
```

- `public readonly System.Int32 File`  

```csharp
public readonly System.Int32 File;
```

- `public readonly System.Int32 Offset`  

```csharp
public readonly System.Int32 Offset;
```

- `public readonly System.Boolean IsHidden`  

```csharp
public readonly System.Boolean IsHidden;
```

- `public static readonly Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry Null`  

```csharp
public static readonly Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry Null;
```


## Constructors

- `public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 offset)`  

```csharp
public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 offset);
```

- `public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 offset)`  

```csharp
public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 offset);
```

- `public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 offset, System.Boolean is_hidden)`  

```csharp
public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 offset, System.Boolean is_hidden);
```

- `public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 end_row, System.Int32 end_column, System.Int32 offset, System.Boolean is_hidden)`  

```csharp
public LineNumberEntry(System.Int32 file, System.Int32 row, System.Int32 column, System.Int32 end_row, System.Int32 end_column, System.Int32 offset, System.Boolean is_hidden);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry+LocationComparer`  

