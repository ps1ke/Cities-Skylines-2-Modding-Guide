# Colossal.Mono.Cecil.Pdb.NativePdbWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Pdb`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriter`, `System.IDisposable`  

## Code

```csharp
public class NativePdbWriter : Colossal.Mono.Cecil.Cil.ISymbolWriter, System.IDisposable
{
    private readonly Colossal.Mono.Cecil.ModuleDefinition module;
    private readonly Colossal.Mono.Cecil.MetadataBuilder metadata;
    private readonly Colossal.Mono.Cecil.Pdb.SymWriter writer;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Pdb.SymDocumentWriter> documents;
    private readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.Cil.ImportDebugInformation, Colossal.Mono.Cecil.MetadataToken> import_info_to_parent;

    internal NativePdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.Pdb.SymWriter writer);

    private System.Void DefineAsyncCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void DefineConstant(Colossal.Mono.Cecil.Cil.ConstantDebugInformation constant);
    private System.Void DefineCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken import_parent);
    private System.Void DefineLocalVariable(Colossal.Mono.Cecil.Cil.VariableDebugInformation variable, System.Int32 local_var_token, System.Int32 start_offset, System.Int32 end_offset);
    private System.Void DefineScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken& import_parent);
    private System.Void DefineSequencePoints(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points);
    public System.Void Dispose();
    public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
    private Colossal.Mono.Cecil.Pdb.SymDocumentWriter GetDocument(Colossal.Mono.Cecil.Cil.Document document);
    public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
    public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
private readonly Colossal.Mono.Cecil.ModuleDefinition module;
```

- `private readonly Colossal.Mono.Cecil.MetadataBuilder metadata`  

```csharp
private readonly Colossal.Mono.Cecil.MetadataBuilder metadata;
```

- `private readonly Colossal.Mono.Cecil.Pdb.SymWriter writer`  

```csharp
private readonly Colossal.Mono.Cecil.Pdb.SymWriter writer;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Pdb.SymDocumentWriter> documents`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Pdb.SymDocumentWriter> documents;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.Cil.ImportDebugInformation, Colossal.Mono.Cecil.MetadataToken> import_info_to_parent`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.Mono.Cecil.Cil.ImportDebugInformation, Colossal.Mono.Cecil.MetadataToken> import_info_to_parent;
```


## Constructors

- `internal NativePdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.Pdb.SymWriter writer)`  

```csharp
internal NativePdbWriter(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.Pdb.SymWriter writer);
```


## Methods

- `private DefineAsyncCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void DefineAsyncCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private DefineConstant(Colossal.Mono.Cecil.Cil.ConstantDebugInformation constant) : System.Void`  

```csharp
private System.Void DefineConstant(Colossal.Mono.Cecil.Cil.ConstantDebugInformation constant);
```

- `private DefineCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken import_parent) : System.Void`  

```csharp
private System.Void DefineCustomMetadata(Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken import_parent);
```

- `private DefineLocalVariable(Colossal.Mono.Cecil.Cil.VariableDebugInformation variable, System.Int32 local_var_token, System.Int32 start_offset, System.Int32 end_offset) : System.Void`  

```csharp
private System.Void DefineLocalVariable(Colossal.Mono.Cecil.Cil.VariableDebugInformation variable, System.Int32 local_var_token, System.Int32 start_offset, System.Int32 end_offset);
```

- `private DefineScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken& import_parent) : System.Void`  

```csharp
private System.Void DefineScope(Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info, Colossal.Mono.Cecil.MetadataToken& import_parent);
```

- `private DefineSequencePoints(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points) : System.Void`  

```csharp
private System.Void DefineSequencePoints(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.SequencePoint> sequence_points);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetDebugHeader() : Colossal.Mono.Cecil.Cil.ImageDebugHeader`  

```csharp
public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
```

- `private GetDocument(Colossal.Mono.Cecil.Cil.Document document) : Colossal.Mono.Cecil.Pdb.SymDocumentWriter`  

```csharp
private Colossal.Mono.Cecil.Pdb.SymDocumentWriter GetDocument(Colossal.Mono.Cecil.Cil.Document document);
```

- `public GetReaderProvider() : Colossal.Mono.Cecil.Cil.ISymbolReaderProvider`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
```

- `public Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```


## Nested types

- `Colossal.Mono.Cecil.Pdb.NativePdbWriter+<>c`  

