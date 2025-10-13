# Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class MonoSymbolFile : System.IDisposable
{
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> methods;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units;
    private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry> anonymous_scopes;
    private Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable ot;
    private System.Int32 last_type_index;
    private System.Int32 last_method_index;
    private System.Int32 last_namespace_index;
    public readonly System.Int32 MajorVersion;
    public readonly System.Int32 MinorVersion;
    public System.Int32 NumLineNumbers;
    private Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader;
    private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> source_file_hash;
    private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> compile_unit_hash;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_list;
    private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_token_hash;
    private System.Collections.Generic.Dictionary<System.String, System.Int32> source_name_hash;
    private System.Guid guid;
    internal System.Int32 LineNumberCount;
    internal System.Int32 LocalCount;
    internal System.Int32 StringSize;
    internal System.Int32 LineNumberSize;
    internal System.Int32 ExtendedLineNumberSize;

    public System.Int32 CompileUnitCount { get; }
    public System.Int32 SourceCount { get; }
    public System.Int32 MethodCount { get; }
    public System.Int32 TypeCount { get; }
    public System.Int32 AnonymousScopeCount { get; }
    public System.Int32 NamespaceCount { get; }
    public System.Guid Guid { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable OffsetTable { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] Sources { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry[] CompileUnits { get; }
    public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry[] Methods { get; }
    internal Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader BinaryReader { internal get; }

    public MonoSymbolFile();
    private MonoSymbolFile(System.IO.Stream stream);

    public System.Int32 AddCompileUnit(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry entry);
    public System.Void AddMethod(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry);
    public System.Int32 AddSource(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source);
    public System.Void CreateSymbolFile(System.Guid guid, System.IO.FileStream fs);
    internal System.Void DefineAnonymousScope(System.Int32 id);
    internal System.Void DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name);
    internal System.Void DefineCapturedVariable(System.Int32 scope_id, System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind);
    public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id);
    public System.Void Dispose();
    protected virtual System.Void Dispose(System.Boolean disposing);
    public System.Int32 FindSource(System.String file_name);
    public Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry GetAnonymousScope(System.Int32 id);
    public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry GetCompileUnit(System.Int32 index);
    public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry GetMethod(System.Int32 index);
    public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry GetMethodByToken(System.Int32 token);
    internal System.Int32 GetNextMethodIndex();
    internal System.Int32 GetNextNamespaceIndex();
    internal System.Int32 GetNextTypeIndex();
    public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry GetSourceFile(System.Int32 index);
    private System.Void read_methods();
    public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.Reflection.Assembly assembly);
    public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.String mdbFilename);
    public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.String mdbFilename, System.Guid assemblyGuid);
    public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.IO.Stream stream);
    private System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw, System.Guid guid);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> methods`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> methods;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units;
```

- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry> anonymous_scopes`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry> anonymous_scopes;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable ot`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable ot;
```

- `private System.Int32 last_type_index`  

```csharp
private System.Int32 last_type_index;
```

- `private System.Int32 last_method_index`  

```csharp
private System.Int32 last_method_index;
```

- `private System.Int32 last_namespace_index`  

```csharp
private System.Int32 last_namespace_index;
```

- `public readonly System.Int32 MajorVersion`  

```csharp
public readonly System.Int32 MajorVersion;
```

- `public readonly System.Int32 MinorVersion`  

```csharp
public readonly System.Int32 MinorVersion;
```

- `public System.Int32 NumLineNumbers`  

```csharp
public System.Int32 NumLineNumbers;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader reader;
```

- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> source_file_hash`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> source_file_hash;
```

- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> compile_unit_hash`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> compile_unit_hash;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_list`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_list;
```

- `private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_token_hash`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry> method_token_hash;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Int32> source_name_hash`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Int32> source_name_hash;
```

- `private System.Guid guid`  

```csharp
private System.Guid guid;
```

- `internal System.Int32 LineNumberCount`  

```csharp
internal System.Int32 LineNumberCount;
```

- `internal System.Int32 LocalCount`  

```csharp
internal System.Int32 LocalCount;
```

- `internal System.Int32 StringSize`  

```csharp
internal System.Int32 StringSize;
```

- `internal System.Int32 LineNumberSize`  

```csharp
internal System.Int32 LineNumberSize;
```

- `internal System.Int32 ExtendedLineNumberSize`  

```csharp
internal System.Int32 ExtendedLineNumberSize;
```


## Properties

- `public System.Int32 CompileUnitCount { get }`  

```csharp
public System.Int32 CompileUnitCount { get; }
```

- `public System.Int32 SourceCount { get }`  

```csharp
public System.Int32 SourceCount { get; }
```

- `public System.Int32 MethodCount { get }`  

```csharp
public System.Int32 MethodCount { get; }
```

- `public System.Int32 TypeCount { get }`  

```csharp
public System.Int32 TypeCount { get; }
```

- `public System.Int32 AnonymousScopeCount { get }`  

```csharp
public System.Int32 AnonymousScopeCount { get; }
```

- `public System.Int32 NamespaceCount { get }`  

```csharp
public System.Int32 NamespaceCount { get; }
```

- `public System.Guid Guid { get }`  

```csharp
public System.Guid Guid { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable OffsetTable { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.OffsetTable OffsetTable { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] Sources { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry[] Sources { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry[] CompileUnits { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry[] CompileUnits { get; }
```

- `public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry[] Methods { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry[] Methods { get; }
```

- `internal Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader BinaryReader { internal get }`  

```csharp
internal Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryReader BinaryReader { internal get; }
```


## Constructors

- `public MonoSymbolFile()`  

```csharp
public MonoSymbolFile();
```

- `private MonoSymbolFile(System.IO.Stream stream)`  

```csharp
private MonoSymbolFile(System.IO.Stream stream);
```


## Methods

- `public AddCompileUnit(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry entry) : System.Int32`  

```csharp
public System.Int32 AddCompileUnit(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry entry);
```

- `public AddMethod(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry) : System.Void`  

```csharp
public System.Void AddMethod(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry);
```

- `public AddSource(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source) : System.Int32`  

```csharp
public System.Int32 AddSource(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source);
```

- `public CreateSymbolFile(System.Guid guid, System.IO.FileStream fs) : System.Void`  

```csharp
public System.Void CreateSymbolFile(System.Guid guid, System.IO.FileStream fs);
```

- `internal DefineAnonymousScope(System.Int32 id) : System.Void`  

```csharp
internal System.Void DefineAnonymousScope(System.Int32 id);
```

- `internal DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name) : System.Void`  

```csharp
internal System.Void DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name);
```

- `internal DefineCapturedVariable(System.Int32 scope_id, System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind) : System.Void`  

```csharp
internal System.Void DefineCapturedVariable(System.Int32 scope_id, System.String name, System.String captured_name, Colossal.Mono.CompilerServices.SymbolWriter.CapturedVariable+CapturedKind kind);
```

- `public DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id) : Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry DefineMethod(Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry comp_unit, System.Int32 token, Colossal.Mono.CompilerServices.SymbolWriter.ScopeVariable[] scope_vars, Colossal.Mono.CompilerServices.SymbolWriter.LocalVariableEntry[] locals, Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry[] lines, Colossal.Mono.CompilerServices.SymbolWriter.CodeBlockEntry[] code_blocks, System.String real_name, Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry+Flags flags, System.Int32 namespace_id);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `protected virtual Dispose(System.Boolean disposing) : System.Void`  

```csharp
protected virtual System.Void Dispose(System.Boolean disposing);
```

- `public FindSource(System.String file_name) : System.Int32`  

```csharp
public System.Int32 FindSource(System.String file_name);
```

- `public GetAnonymousScope(System.Int32 id) : Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.AnonymousScopeEntry GetAnonymousScope(System.Int32 id);
```

- `public GetCompileUnit(System.Int32 index) : Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry GetCompileUnit(System.Int32 index);
```

- `public GetMethod(System.Int32 index) : Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry GetMethod(System.Int32 index);
```

- `public GetMethodByToken(System.Int32 token) : Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry GetMethodByToken(System.Int32 token);
```

- `internal GetNextMethodIndex() : System.Int32`  

```csharp
internal System.Int32 GetNextMethodIndex();
```

- `internal GetNextNamespaceIndex() : System.Int32`  

```csharp
internal System.Int32 GetNextNamespaceIndex();
```

- `internal GetNextTypeIndex() : System.Int32`  

```csharp
internal System.Int32 GetNextTypeIndex();
```

- `public GetSourceFile(System.Int32 index) : Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry GetSourceFile(System.Int32 index);
```

- `private read_methods() : System.Void`  

```csharp
private System.Void read_methods();
```

- `public static ReadSymbolFile(System.Reflection.Assembly assembly) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  

```csharp
public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.Reflection.Assembly assembly);
```

- `public static ReadSymbolFile(System.String mdbFilename) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  

```csharp
public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.String mdbFilename);
```

- `public static ReadSymbolFile(System.String mdbFilename, System.Guid assemblyGuid) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  

```csharp
public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.String mdbFilename, System.Guid assemblyGuid);
```

- `public static ReadSymbolFile(System.IO.Stream stream) : Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile`  

```csharp
public static Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile ReadSymbolFile(System.IO.Stream stream);
```

- `private Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw, System.Guid guid) : System.Void`  

```csharp
private System.Void Write(Colossal.Mono.CompilerServices.SymbolWriter.MyBinaryWriter bw, System.Guid guid);
```


