# Colossal.Mono.Cecil.Cil.PortablePdbReaderProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

## Code

```csharp
public sealed class PortablePdbReaderProvider : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider
{
    public PortablePdbReaderProvider();

    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
    private Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Disposable<System.IO.Stream> symbolStream, System.String fileName);
}
```


## Constructors

- `public PortablePdbReaderProvider()`  

```csharp
public PortablePdbReaderProvider();
```


## Methods

- `public GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
```

- `public GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
```

- `private GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Disposable<System.IO.Stream> symbolStream, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

```csharp
private Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Disposable<System.IO.Stream> symbolStream, System.String fileName);
```


