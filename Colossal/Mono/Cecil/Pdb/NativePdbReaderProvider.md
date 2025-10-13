# Colossal.Mono.Cecil.Pdb.NativePdbReaderProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Pdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

## Code

```csharp
public sealed class NativePdbReaderProvider : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider
{
    public NativePdbReaderProvider();

    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Constructors

- `public NativePdbReaderProvider()`  

```csharp
public NativePdbReaderProvider();
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


