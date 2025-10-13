# Colossal.Mono.Cecil.Cil.ISymbolWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface ISymbolWriter : System.IDisposable
{
    public abstract Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
    public abstract Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
    public abstract System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
}
```


## Methods

- `public abstract GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
```

- `public abstract GetReaderProvider() : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
```

- `public abstract Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
public abstract System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```


