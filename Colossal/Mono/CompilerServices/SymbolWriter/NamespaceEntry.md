# Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct NamespaceEntry
{
    public readonly System.String Name;
    public readonly System.Int32 Index;
    public readonly System.Int32 Parent;
    public readonly System.String[] UsingClauses;

    public NamespaceEntry(System.String name, System.Int32 index, System.String[] using_clauses, System.Int32 parent);
    internal NamespaceEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.String Name`  

```csharp
public readonly System.String Name;
```

- `public readonly System.Int32 Index`  

```csharp
public readonly System.Int32 Index;
```

- `public readonly System.Int32 Parent`  

```csharp
public readonly System.Int32 Parent;
```

- `public readonly System.String[] UsingClauses`  

```csharp
public readonly System.String[] UsingClauses;
```


## Constructors

- `public NamespaceEntry(System.String name, System.Int32 index, System.String[] using_clauses, System.Int32 parent)`  

```csharp
public NamespaceEntry(System.String name, System.Int32 index, System.String[] using_clauses, System.Int32 parent);
```

- `internal NamespaceEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal NamespaceEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
```


## Methods

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

```csharp
internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
```


