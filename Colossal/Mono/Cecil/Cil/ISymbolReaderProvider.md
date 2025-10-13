# Colossal.Mono.Cecil.Cil.ISymbolReaderProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ISymbolReaderProvider
{
    public abstract Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public abstract Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Methods

- `public abstract GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
```

- `public abstract GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream) : Colossal.Mono.Cecil.Cil.ISymbolReader`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
```


