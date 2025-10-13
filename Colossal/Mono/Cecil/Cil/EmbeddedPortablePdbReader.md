# Colossal.Mono.Cecil.Cil.EmbeddedPortablePdbReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReader`, `System.IDisposable`  

## Code

```csharp
public sealed class EmbeddedPortablePdbReader : Colossal.Mono.Cecil.Cil.ISymbolReader, System.IDisposable
{
    private readonly Colossal.Mono.Cecil.Cil.PortablePdbReader reader;

    internal EmbeddedPortablePdbReader(Colossal.Mono.Cecil.Cil.PortablePdbReader reader);

    public System.Void Dispose();
    public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
    public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
    public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.Cil.PortablePdbReader reader`  

```csharp
private readonly Colossal.Mono.Cecil.Cil.PortablePdbReader reader;
```


## Constructors

- `internal EmbeddedPortablePdbReader(Colossal.Mono.Cecil.Cil.PortablePdbReader reader)`  

```csharp
internal EmbeddedPortablePdbReader(Colossal.Mono.Cecil.Cil.PortablePdbReader reader);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
```

- `public ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  

```csharp
public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
```

- `public Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  

```csharp
public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
```


