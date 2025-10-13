# Colossal.UI.FileReader

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.UnityFileSystemReader`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class FileReader : cohtml.Net.UnityFileSystemReader, System.IDisposable
{
    private static Colossal.UI.FileReader m_Instance;

    public static Colossal.UI.FileReader Reader { get; }

    public FileReader();

    public virtual System.Void Dispose();
    private System.String NormalizePath(System.String path);
    public virtual cohtml.Net.UnitySyncStreamReader OpenFile(System.String path);
}
```


## Fields

- `private static Colossal.UI.FileReader m_Instance`  

```csharp
private static Colossal.UI.FileReader m_Instance;
```


## Properties

- `public static Colossal.UI.FileReader Reader { get }`  

```csharp
public static Colossal.UI.FileReader Reader { get; }
```


## Constructors

- `public FileReader()`  

```csharp
public FileReader();
```


## Methods

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `private NormalizePath(System.String path) : System.String`  

```csharp
private System.String NormalizePath(System.String path);
```

- `public virtual OpenFile(System.String path) : cohtml.Net.UnitySyncStreamReader`  

```csharp
public virtual cohtml.Net.UnitySyncStreamReader OpenFile(System.String path);
```


