# Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ScopeVariable
{
    public readonly System.Int32 Scope;
    public readonly System.Int32 Index;

    public ScopeVariable(System.Int32 scope, System.Int32 index);
    internal ScopeVariable(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.Int32 Scope`  

```csharp
public readonly System.Int32 Scope;
```

- `public readonly System.Int32 Index`  

```csharp
public readonly System.Int32 Index;
```


## Constructors

- `public ScopeVariable(System.Int32 scope, System.Int32 index)`  

```csharp
public ScopeVariable(System.Int32 scope, System.Int32 index);
```

- `internal ScopeVariable(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal ScopeVariable(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

```csharp
internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
```


