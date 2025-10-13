# Colossal.Mono.Cecil.Cil.EmbeddedPortablePdbWriterProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

## Code

```csharp
public sealed class EmbeddedPortablePdbWriterProvider : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider
{
    public EmbeddedPortablePdbWriterProvider();

    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Constructors

- `public EmbeddedPortablePdbWriterProvider()`  

```csharp
public EmbeddedPortablePdbWriterProvider();
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


