# Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct LocalVariableEntry
{
    public readonly System.Int32 Index;
    public readonly System.String Name;
    public readonly System.Int32 BlockIndex;

    public LocalVariableEntry(System.Int32 index, System.String name, System.Int32 block);
    internal LocalVariableEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.Int32 Index`  

```csharp
public readonly System.Int32 Index;
```

- `public readonly System.String Name`  

```csharp
public readonly System.String Name;
```

- `public readonly System.Int32 BlockIndex`  

```csharp
public readonly System.Int32 BlockIndex;
```


## Constructors

- `public LocalVariableEntry(System.Int32 index, System.String name, System.Int32 block)`  

```csharp
public LocalVariableEntry(System.Int32 index, System.String name, System.Int32 block);
```

- `internal LocalVariableEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal LocalVariableEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
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


