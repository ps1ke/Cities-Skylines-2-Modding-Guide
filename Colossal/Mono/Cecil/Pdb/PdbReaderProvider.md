# Colossal.Mono.Cecil.Pdb.PdbReaderProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Pdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

## Code

```csharp
public sealed class PdbReaderProvider : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider
{
    public PdbReaderProvider();

    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Constructors

- `public PdbReaderProvider()`  

```csharp
public PdbReaderProvider();
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


