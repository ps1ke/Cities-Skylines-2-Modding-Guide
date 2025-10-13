# Colossal.UI.FileSystemFontProvider

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.IFontStreamProvider`  

## Code

```csharp
public class FileSystemFontProvider : Colossal.UI.IFontStreamProvider
{
    private readonly System.String m_Path;

    public FileSystemFontProvider(System.String path);

    public Colossal.UI.StreamReader GetStreamReader();
}
```


## Fields

- `private readonly System.String m_Path`  

```csharp
private readonly System.String m_Path;
```


## Constructors

- `public FileSystemFontProvider(System.String path)`  

```csharp
public FileSystemFontProvider(System.String path);
```


## Methods

- `public GetStreamReader() : Colossal.UI.StreamReader`  

```csharp
public Colossal.UI.StreamReader GetStreamReader();
```


