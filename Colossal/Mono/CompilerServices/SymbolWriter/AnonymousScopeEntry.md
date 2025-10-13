# Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AnonymousScopeEntry
{
    public readonly System.Int32 ID;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable> captured_vars;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope> captured_scopes;

    public Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable[] CapturedVariables { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope[] CapturedScopes { get; }

    public AnonymousScopeEntry(System.Int32 id);
    internal AnonymousScopeEntry(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    internal System.Void AddCapturedScope(System.Int32 scope, System.String captured_name);
    internal System.Void AddCapturedVariable(System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind);
    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.Int32 ID`  

```csharp
public readonly System.Int32 ID;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable> captured_vars`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable> captured_vars;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope> captured_scopes`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope> captured_scopes;
```


## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable[] CapturedVariables { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable[] CapturedVariables { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope[] CapturedScopes { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CapturedScope[] CapturedScopes { get; }
```


## Constructors

- `public AnonymousScopeEntry(System.Int32 id)`  

```csharp
public AnonymousScopeEntry(System.Int32 id);
```

- `internal AnonymousScopeEntry(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal AnonymousScopeEntry(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
```


## Methods

- `internal AddCapturedScope(System.Int32 scope, System.String captured_name) : System.Void`  

```csharp
internal System.Void AddCapturedScope(System.Int32 scope, System.String captured_name);
```

- `internal AddCapturedVariable(System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind) : System.Void`  

```csharp
internal System.Void AddCapturedVariable(System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

```csharp
internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
```


