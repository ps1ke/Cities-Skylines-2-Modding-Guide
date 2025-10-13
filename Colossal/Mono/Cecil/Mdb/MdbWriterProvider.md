# Colossal.Mono.Cecil.Mdb.MdbWriterProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Mdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

## Code

```csharp
public sealed class MdbWriterProvider : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider
{
    public MdbWriterProvider();

    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolWriter GetSymbolWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Constructors

- `public MdbWriterProvider()`  

```csharp
public MdbWriterProvider();
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


