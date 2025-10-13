# Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IComparable`  

## Code

```csharp
public class MethodEntry : System.IComparable
{
    public readonly System.Int32 CompileUnitIndex;
    public readonly System.Int32 Token;
    public readonly System.Int32 NamespaceID;
    private System.Int32 DataOffset;
    private System.Int32 LocalVariableTableOffset;
    private System.Int32 LineNumberTableOffset;
    private System.Int32 CodeBlockTableOffset;
    private System.Int32 ScopeVariableTableOffset;
    private System.Int32 RealNameOffset;
    private Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags;
    private System.Int32 index;
    public readonly Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry CompileUnit;
    private Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals;
    private Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks;
    private Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars;
    private Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable lnt;
    private System.String real_name;
    public readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile;
    public static const System.Int32 Size;

    public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags MethodFlags { get; }
    public System.Int32 Index { get; set; }

    internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader, System.Int32 index);
    internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id);

    private static System.Void CheckLineNumberTable(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] line_numbers);
    public System.Int32 CompareTo(System.Object obj);
    public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] GetCodeBlocks();
    public Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable GetLineNumberTable();
    public Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] GetLocals();
    public System.String GetRealName();
    public Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] GetScopeVariables();
    public System.Void ReadAll();
    public virtual System.String ToString();
    internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
    internal System.Void WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.Int32 CompileUnitIndex`  

```csharp
public readonly System.Int32 CompileUnitIndex;
```

- `public readonly System.Int32 Token`  

```csharp
public readonly System.Int32 Token;
```

- `public readonly System.Int32 NamespaceID`  

```csharp
public readonly System.Int32 NamespaceID;
```

- `private System.Int32 DataOffset`  

```csharp
private System.Int32 DataOffset;
```

- `private System.Int32 LocalVariableTableOffset`  

```csharp
private System.Int32 LocalVariableTableOffset;
```

- `private System.Int32 LineNumberTableOffset`  

```csharp
private System.Int32 LineNumberTableOffset;
```

- `private System.Int32 CodeBlockTableOffset`  

```csharp
private System.Int32 CodeBlockTableOffset;
```

- `private System.Int32 ScopeVariableTableOffset`  

```csharp
private System.Int32 ScopeVariableTableOffset;
```

- `private System.Int32 RealNameOffset`  

```csharp
private System.Int32 RealNameOffset;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags;
```

- `private System.Int32 index`  

```csharp
private System.Int32 index;
```

- `public readonly Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry CompileUnit`  

```csharp
public readonly Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry CompileUnit;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable lnt`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable lnt;
```

- `private System.String real_name`  

```csharp
private System.String real_name;
```

- `public readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile`  

```csharp
public readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile;
```

- `public static const System.Int32 Size`  

```csharp
public static const System.Int32 Size;
```


## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags MethodFlags { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags MethodFlags { get; }
```

- `public System.Int32 Index { get; set }`  

```csharp
public System.Int32 Index { get; set; }
```


## Constructors

- `internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader, System.Int32 index)`  

```csharp
internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader, System.Int32 index);
```

- `internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id)`  

```csharp
internal MethodEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id);
```


## Methods

- `private static CheckLineNumberTable(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] line_numbers) : System.Void`  

```csharp
private static System.Void CheckLineNumberTable(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] line_numbers);
```

- `public CompareTo(System.Object obj) : System.Int32`  

```csharp
public System.Int32 CompareTo(System.Object obj);
```

- `public GetCodeBlocks() : Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[]`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] GetCodeBlocks();
```

- `public GetLineNumberTable() : Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.LineNumberTable GetLineNumberTable();
```

- `public GetLocals() : Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[]`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] GetLocals();
```

- `public GetRealName() : System.String`  

```csharp
public System.String GetRealName();
```

- `public GetScopeVariables() : Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[]`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] GetScopeVariables();
```

- `public ReadAll() : System.Void`  

```csharp
public System.Void ReadAll();
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```

- `internal Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

```csharp
internal System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
```

- `internal WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

```csharp
internal System.Void WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
```


## Nested types

- `Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags`  

