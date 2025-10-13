# Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit`  

## Code

```csharp
public class CompileUnitEntry : Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit
{
    public readonly System.Int32 Index;
    private System.Int32 DataOffset;
    private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file;
    private Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> include_files;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry> namespaces;
    private System.Boolean creating;

    public static System.Int32 Size { get; }
    private Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit.Entry { private get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry SourceFile { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry[] Namespaces { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] IncludeFiles { get; }

    public CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source);
    internal CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);

    public System.Void AddFile(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file);
    public System.Int32 DefineNamespace(System.String name, System.String[] using_clauses, System.Int32 parent);
    public System.Void ReadAll();
    private System.Void ReadData();
    internal System.Void Write(System.IO.BinaryWriter bw);
    internal System.Void WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
}
```


## Fields

- `public readonly System.Int32 Index`  

```csharp
public readonly System.Int32 Index;
```

- `private System.Int32 DataOffset`  

```csharp
private System.Int32 DataOffset;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> include_files`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> include_files;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry> namespaces`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry> namespaces;
```

- `private System.Boolean creating`  

```csharp
private System.Boolean creating;
```


## Properties

- `public static System.Int32 Size { get }`  

```csharp
public static System.Int32 Size { get; }
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit.Entry { private get }`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit.Entry { private get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry SourceFile { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry SourceFile { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry[] Namespaces { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.NamespaceEntry[] Namespaces { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] IncludeFiles { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] IncludeFiles { get; }
```


## Constructors

- `public CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source)`  

```csharp
public CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source);
```

- `internal CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader)`  

```csharp
internal CompileUnitEntry(Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file, Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader);
```


## Methods

- `public AddFile(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file) : System.Void`  

```csharp
public System.Void AddFile(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file);
```

- `public DefineNamespace(System.String name, System.String[] using_clauses, System.Int32 parent) : System.Int32`  

```csharp
public System.Int32 DefineNamespace(System.String name, System.String[] using_clauses, System.Int32 parent);
```

- `public ReadAll() : System.Void`  

```csharp
public System.Void ReadAll();
```

- `private ReadData() : System.Void`  

```csharp
private System.Void ReadData();
```

- `internal Write(System.IO.BinaryWriter bw) : System.Void`  

```csharp
internal System.Void Write(System.IO.BinaryWriter bw);
```

- `internal WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw) : System.Void`  

```csharp
internal System.Void WriteData(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw);
```


