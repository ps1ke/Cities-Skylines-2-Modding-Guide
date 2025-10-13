# Colossal.UI.Fatal.FileSystemStreamProvider

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI.Fatal`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Fatal.IFileStreamProvider`  

## Code

```csharp
public class FileSystemStreamProvider : Colossal.UI.Fatal.IFileStreamProvider
{
    private System.String m_Path;

    public System.String name { get; }

    public FileSystemStreamProvider(System.String path);

    public Colossal.UI.IFontStreamProvider GetFontStreamProvider();
    public System.IO.Stream OpenRead();
}
```


## Fields

- `private System.String m_Path`  

```csharp
private System.String m_Path;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```


## Constructors

- `public FileSystemStreamProvider(System.String path)`  

```csharp
public FileSystemStreamProvider(System.String path);
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


