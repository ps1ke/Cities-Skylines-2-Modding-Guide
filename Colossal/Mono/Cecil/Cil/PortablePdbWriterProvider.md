# Colossal.Mono.Cecil.Cil.PortablePdbWriterProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

## Code

```csharp
public sealed class PortablePdbWriterProvider : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider
{
    public PortablePdbWriterProvider();

    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
    private Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Disposable<System.IO.Stream> stream);
}
```


## Constructors

- `public PortablePdbWriterProvider()`  

```csharp
public PortablePdbWriterProvider();
```


## Methods

- `public GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolWriter`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
```

- `public GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream) : Colossal.Mono.Cecil.Cil.ISymbolWriter`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
```

- `private GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Disposable<System.IO.Stream> stream) : Colossal.Mono.Cecil.Cil.ISymbolWriter`  

```csharp
private Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Disposable<System.IO.Stream> stream);
```


