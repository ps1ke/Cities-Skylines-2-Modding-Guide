# Colossal.Mono.Cecil.Cil.EmbeddedPortablePdbReaderProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

## Code

```csharp
public sealed class EmbeddedPortablePdbReaderProvider : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider
{
    public EmbeddedPortablePdbReaderProvider();

    private static System.IO.Stream GetPortablePdbStream(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);
    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Constructors

- `public EmbeddedPortablePdbReaderProvider()`  

```csharp
public EmbeddedPortablePdbReaderProvider();
```


## Methods

- `private static GetPortablePdbStream(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry) : System.IO.Stream`  

```csharp
private static System.IO.Stream GetPortablePdbStream(Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);
```

- `public GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
```

- `public GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
```


