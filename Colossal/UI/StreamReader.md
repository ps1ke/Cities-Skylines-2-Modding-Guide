# Colossal.UI.StreamReader

**Assembly:** `Colossal.UI`  
**Namespace:** `Colossal.UI`  

**Type:** class public  

**Base:** `cohtml.Net.UnitySyncStreamReader`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class StreamReader : cohtml.Net.UnitySyncStreamReader, System.IDisposable
{
    private System.IO.Stream m_Stream;
    private static System.Collections.Generic.List<Colossal.UI.StreamReader> s_StreamReaders;

    public StreamReader(System.IO.Stream stream);
    public StreamReader(System.String path);
    public StreamReader(System.Byte[] data);

    public virtual System.Void Close();
    public static System.Void DisposeReaders();
    public virtual System.UInt32 GetSize();
    public virtual System.UInt32 Read(System.UInt32 offset, System.IntPtr buffer, System.UInt32 count);
}
```


## Fields

- `private System.IO.Stream m_Stream`  

```csharp
private System.IO.Stream m_Stream;
```

- `private static System.Collections.Generic.List<Colossal.UI.StreamReader> s_StreamReaders`  

```csharp
private static System.Collections.Generic.List<Colossal.UI.StreamReader> s_StreamReaders;
```


## Constructors

- `public StreamReader(System.IO.Stream stream)`  

```csharp
public StreamReader(System.IO.Stream stream);
```

- `public StreamReader(System.String path)`  

```csharp
public StreamReader(System.String path);
```

- `public StreamReader(System.Byte[] data)`  

```csharp
public StreamReader(System.Byte[] data);
```


## Methods

- `public virtual Close() : System.Void`  

```csharp
public virtual System.Void Close();
```

- `public static DisposeReaders() : System.Void`  

```csharp
public static System.Void DisposeReaders();
```

- `public virtual GetSize() : System.UInt32`  

```csharp
public virtual System.UInt32 GetSize();
```

- `public virtual Read(System.UInt32 offset, System.IntPtr buffer, System.UInt32 count) : System.UInt32`  

```csharp
public virtual System.UInt32 Read(System.UInt32 offset, System.IntPtr buffer, System.UInt32 count);
```


