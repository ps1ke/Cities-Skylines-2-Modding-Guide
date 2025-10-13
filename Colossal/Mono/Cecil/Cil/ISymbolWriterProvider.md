# Colossal.Mono.Cecil.Cil.ISymbolWriterProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface ISymbolWriterProvider
{
    public abstract Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public abstract Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Methods

- `public abstract GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName) : Colossal.Mono.Cecil.Cil.ISymbolWriter`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
```

- `public abstract GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream) : Colossal.Mono.Cecil.Cil.ISymbolWriter`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
```


