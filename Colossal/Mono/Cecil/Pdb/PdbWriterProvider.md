# Colossal.Mono.Cecil.Pdb.PdbWriterProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Pdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

## Code

```csharp
public sealed class PdbWriterProvider : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider
{
    public PdbWriterProvider();

    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
    private static System.Boolean HasPortablePdbSymbols(Colossal.Mono.Cecil.ModuleDefinition module);
}
```


## Constructors

- `public PdbWriterProvider()`  

```csharp
public PdbWriterProvider();
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

- `private static HasPortablePdbSymbols(Colossal.Mono.Cecil.ModuleDefinition module) : System.Boolean`  

```csharp
private static System.Boolean HasPortablePdbSymbols(Colossal.Mono.Cecil.ModuleDefinition module);
```


