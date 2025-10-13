# Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class CodeBlockEntry
{
    public System.Int32 Index;
    public System.Int32 Parent;
    public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type BlockType;
    public System.Int32 StartOffset;
    public System.Int32 EndOffset;

    public CodeBlockEntry(System.Int32 index, System.Int32 parent, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset);
    internal CodeBlockEntry(System.Int32 index, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    public System.Void Close(System.Int32 end_offset);
    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public System.Int32 Index`  

```csharp
public System.Int32 Index;
```

- `public System.Int32 Parent`  

```csharp
public System.Int32 Parent;
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type BlockType`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type BlockType;
```

- `public System.Int32 StartOffset`  

```csharp
public System.Int32 StartOffset;
```

- `public System.Int32 EndOffset`  

```csharp
public System.Int32 EndOffset;
```


## Constructors

- `public CodeBlockEntry(System.Int32 index, System.Int32 parent, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset)`  

```csharp
public CodeBlockEntry(System.Int32 index, System.Int32 parent, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type type, System.Int32 start_offset);
```

- `internal CodeBlockEntry(System.Int32 index, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal CodeBlockEntry(System.Int32 index, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
```


## Methods

- `public Close(System.Int32 end_offset) : System.Void`  

```csharp
public System.Void Close(System.Int32 end_offset);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

```csharp
internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
```


## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry+Type`  

