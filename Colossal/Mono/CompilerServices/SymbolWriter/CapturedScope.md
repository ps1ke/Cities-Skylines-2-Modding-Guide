# Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CapturedScope
{
    public readonly System.Int32 Scope;
    public readonly System.String CapturedName;

    public CapturedScope(System.Int32 scope, System.String captured_name);
    internal CapturedScope(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.Int32 Scope`  

```csharp
public readonly System.Int32 Scope;
```

- `public readonly System.String CapturedName`  

```csharp
public readonly System.String CapturedName;
```


## Constructors

- `public CapturedScope(System.Int32 scope, System.String captured_name)`  

```csharp
public CapturedScope(System.Int32 scope, System.String captured_name);
```

- `internal CapturedScope(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal CapturedScope(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
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


