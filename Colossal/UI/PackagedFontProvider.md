# Colossal.UI.PackagedFontProvider

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.IFontStreamProvider`  

## Code

```csharp
public class PackagedFontProvider : Colossal.UI.IFontStreamProvider
{
    private readonly System.String m_Path;
    private readonly System.Int64 m_Offset;
    private readonly System.Int64 m_Size;

    public PackagedFontProvider(System.String path, System.Int64 offset, System.Int64 size);

    public Colossal.UI.StreamReader GetStreamReader();
}
```


## Fields

- `private readonly System.String m_Path`  

```csharp
private readonly System.String m_Path;
```

- `private readonly System.Int64 m_Offset`  

```csharp
private readonly System.Int64 m_Offset;
```

- `private readonly System.Int64 m_Size`  

```csharp
private readonly System.Int64 m_Size;
```


## Constructors

- `public PackagedFontProvider(System.String path, System.Int64 offset, System.Int64 size)`  

```csharp
public PackagedFontProvider(System.String path, System.Int64 offset, System.Int64 size);
```


## Methods

- `public GetStreamReader() : Colossal.UI.StreamReader`  

```csharp
public Colossal.UI.StreamReader GetStreamReader();
```


