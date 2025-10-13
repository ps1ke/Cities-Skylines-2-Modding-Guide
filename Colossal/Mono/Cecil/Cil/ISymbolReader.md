# Colossal.Mono.Cecil.Cil.ISymbolReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

## Code

```csharp
public abstract interface ISymbolReader : System.IDisposable
{
    public abstract Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
    public abstract System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
    public abstract Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
}
```


## Methods

- `public abstract GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
```

- `public abstract ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  

```csharp
public abstract System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
```

- `public abstract Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  

```csharp
public abstract Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
```


