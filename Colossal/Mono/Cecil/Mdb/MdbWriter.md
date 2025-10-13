# Colossal.Mono.Cecil.Mdb.MdbWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Mdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriter`, `System.IDisposable`  

## Code

```csharp
public sealed class MdbWriter : Colossal.Mono.Cecil.Cil.ISymbolWriter, System.IDisposable
{
    private readonly Colossal.Mono.Cecil.ModuleDefinition module;
    private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter writer;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile> source_files;

    public MdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String assembly);

    public System.Void Dispose();
    public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
    public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
    private Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile GetSourceFile(Colossal.Mono.Cecil.Cil.Document document);
    private System.Void Populate(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequencePoints, System.Int32[] offsets, System.Int32[] startRows, System.Int32[] endRows, System.Int32[] startCols, System.Int32[] endCols, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile& file);
    public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void WriteRootScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void WriteScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void WriteScopes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void WriteScopeVariables(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
private readonly Colossal.Mono.Cecil.ModuleDefinition module;
```

- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter writer`  

```csharp
private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter writer;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile> source_files`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile> source_files;
```


## Constructors

- `public MdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String assembly)`  

```csharp
public MdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, System.String assembly);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  

```csharp
public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
```

- `public GetReaderProvider() : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
```

- `private GetSourceFile(Colossal.Mono.Cecil.Cil.Document document) : Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile`  

```csharp
private Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile GetSourceFile(Colossal.Mono.Cecil.Cil.Document document);
```

- `private Populate(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequencePoints, System.Int32[] offsets, System.Int32[] startRows, System.Int32[] endRows, System.Int32[] startCols, System.Int32[] endCols, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile& file) : System.Void`  

```csharp
private System.Void Populate(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequencePoints, System.Int32[] offsets, System.Int32[] startRows, System.Int32[] endRows, System.Int32[] startCols, System.Int32[] endCols, Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile& file);
```

- `public Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private WriteRootScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void WriteRootScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private WriteScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void WriteScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private WriteScopes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void WriteScopes(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private WriteScopeVariables(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope) : System.Void`  

```csharp
private System.Void WriteScopeVariables(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope);
```


## Nested types

- `Colossal.Mono.Cecil.Mdb.MdbWriter+SourceFile`  
- `Colossal.Mono.Cecil.Mdb.MdbWriter+SourceMethod`  

