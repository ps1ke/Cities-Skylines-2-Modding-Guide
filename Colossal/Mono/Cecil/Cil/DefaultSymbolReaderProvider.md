# Colossal.Mono.Cecil.Cil.DefaultSymbolReaderProvider

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

## Code

```csharp
public class DefaultSymbolReaderProvider : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider
{
    private readonly System.Boolean throw_if_no_symbol;

    public DefaultSymbolReaderProvider();
    public DefaultSymbolReaderProvider(System.Boolean throwIfNoSymbol);

    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.String fileName);
    public Colossal.Mono.Cecil.Cil.ISymbolReader GetSymbolReader(Colossal.Mono.Cecil.ModuleDefinition module, System.IO.Stream symbolStream);
}
```


## Fields

- `private readonly System.Boolean throw_if_no_symbol`  

```csharp
private readonly System.Boolean throw_if_no_symbol;
```


## Constructors

- `public DefaultSymbolReaderProvider()`  

```csharp
public DefaultSymbolReaderProvider();
```

- `public DefaultSymbolReaderProvider(System.Boolean throwIfNoSymbol)`  

```csharp
public DefaultSymbolReaderProvider(System.Boolean throwIfNoSymbol);
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


