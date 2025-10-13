# Colossal.Mono.Cecil.Cil.EmbeddedPortablePdbWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriter`, `System.IDisposable`  

## Code

```csharp
public sealed class EmbeddedPortablePdbWriter : Colossal.Mono.Cecil.Cil.ISymbolWriter, System.IDisposable
{
    private readonly System.IO.Stream stream;
    private readonly Colossal.Mono.Cecil.Cil.PortablePdbWriter writer;

    internal EmbeddedPortablePdbWriter(System.IO.Stream stream, Colossal.Mono.Cecil.Cil.PortablePdbWriter writer);

    public System.Void Dispose();
    public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
    public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
    public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
}
```


## Fields

- `private readonly System.IO.Stream stream`  

```csharp
private readonly System.IO.Stream stream;
```

- `private readonly Colossal.Mono.Cecil.Cil.PortablePdbWriter writer`  

```csharp
private readonly Colossal.Mono.Cecil.Cil.PortablePdbWriter writer;
```


## Constructors

- `internal EmbeddedPortablePdbWriter(System.IO.Stream stream, Colossal.Mono.Cecil.Cil.PortablePdbWriter writer)`  

```csharp
internal EmbeddedPortablePdbWriter(System.IO.Stream stream, Colossal.Mono.Cecil.Cil.PortablePdbWriter writer);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  

```csharp
public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
```

- `public GetReaderProvider() : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
```

- `public Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```


