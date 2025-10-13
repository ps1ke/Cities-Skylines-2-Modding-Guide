# Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CapturedVariable
{
    public readonly System.String Name;
    public readonly System.String CapturedName;
    public readonly Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind Kind;

    public CapturedVariable(System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind);
    internal CapturedVariable(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.String Name`  

```csharp
public readonly System.String Name;
```

- `public readonly System.String CapturedName`  

```csharp
public readonly System.String CapturedName;
```

- `public readonly Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind Kind`  

```csharp
public readonly Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind Kind;
```


## Constructors

- `public CapturedVariable(System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind)`  

```csharp
public CapturedVariable(System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind);
```

- `internal CapturedVariable(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal CapturedVariable(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
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


## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind`  

