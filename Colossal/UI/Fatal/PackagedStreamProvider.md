# Colossal.UI.Fatal.PackagedStreamProvider

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Fatal.IFileStreamProvider`  

## Code

```csharp
public class PackagedStreamProvider : Colossal.UI.Fatal.IFileStreamProvider
{
    private readonly System.String m_Name;
    private readonly System.String m_Path;
    private readonly System.Int64 m_Offset;
    private readonly System.Int64 m_Size;

    public System.String name { get; }

    public PackagedStreamProvider(System.String name, System.String path, System.Int64 offset, System.Int64 size);

    public Colossal.UI.IFontStreamProvider GetFontStreamProvider();
    public System.IO.Stream OpenRead();
}
```


## Fields

- `private readonly System.String m_Name`  

```csharp
private readonly System.String m_Name;
```

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


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```


## Constructors

- `public PackagedStreamProvider(System.String name, System.String path, System.Int64 offset, System.Int64 size)`  

```csharp
public PackagedStreamProvider(System.String name, System.String path, System.Int64 offset, System.Int64 size);
```


## Methods

- `public GetFontStreamProvider() : Colossal.UI.IFontStreamProvider`  

```csharp
public Colossal.UI.IFontStreamProvider GetFontStreamProvider();
```

- `public OpenRead() : System.IO.Stream`  

```csharp
public System.IO.Stream OpenRead();
```


