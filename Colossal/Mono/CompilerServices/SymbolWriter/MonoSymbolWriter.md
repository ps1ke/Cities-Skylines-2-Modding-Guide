# Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.CompilerServices.SymbolWriter`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class MonoSymbolWriter
{
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> methods;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources;
    private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units;
    protected readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file;
    private System.String filename;
    private Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder current_method;
    private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> current_method_stack;

    public Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile { get; }

    public MonoSymbolWriter(System.String filename);

    public System.Void CloseCompilerGeneratedBlock(System.Int32 end_offset);
    public System.Void CloseMethod();
    public System.Void CloseNamespace();
    public System.Void CloseScope(System.Int32 end_offset);
    public System.Void DefineAnonymousScope(System.Int32 id);
    public System.Void DefineCapturedLocal(System.Int32 scope_id, System.String name, System.String captured_name);
    public System.Void DefineCapturedParameter(System.Int32 scope_id, System.String name, System.String captured_name);
    public System.Void DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name);
    public System.Void DefineCapturedThis(System.Int32 scope_id, System.String captured_name);
    public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry DefineCompilationUnit(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source);
    public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry DefineDocument(System.String url);
    public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry DefineDocument(System.String url, System.Byte[] guid, System.Byte[] checksum);
    public System.Void DefineLocalVariable(System.Int32 index, System.String name);
    public System.Int32 DefineNamespace(System.String name, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry unit, System.String[] using_clauses, System.Int32 parent);
    public System.Void DefineScopeVariable(System.Int32 scope, System.Int32 index);
    public System.Void EndIteratorBody(System.Int32 end_offset);
    public System.Void EndIteratorDispatcher(System.Int32 end_offset);
    public System.Void MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden);
    public System.Void OpenCompilerGeneratedBlock(System.Int32 start_offset);
    public Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder OpenMethod(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit file, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method);
    public System.Int32 OpenScope(System.Int32 start_offset);
    public System.Void StartIteratorBody(System.Int32 start_offset);
    public System.Void StartIteratorDispatcher(System.Int32 start_offset);
    public System.Void WriteSymbolFile(System.Guid guid);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> methods`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> methods;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry> sources;
```

- `private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units`  

```csharp
private System.Collections.Generic.List<Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry> comp_units;
```

- `protected readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file`  

```csharp
protected readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile file;
```

- `private System.String filename`  

```csharp
private System.String filename;
```

- `private Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder current_method`  

```csharp
private Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder current_method;
```

- `private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> current_method_stack`  

```csharp
private System.Collections.Generic.Stack<Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder> current_method_stack;
```


## Properties

- `public Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile { get }`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile SymbolFile { get; }
```


## Constructors

- `public MonoSymbolWriter(System.String filename)`  

```csharp
public MonoSymbolWriter(System.String filename);
```


## Methods

- `public CloseCompilerGeneratedBlock(System.Int32 end_offset) : System.Void`  

```csharp
public System.Void CloseCompilerGeneratedBlock(System.Int32 end_offset);
```

- `public CloseMethod() : System.Void`  

```csharp
public System.Void CloseMethod();
```

- `public CloseNamespace() : System.Void`  

```csharp
public System.Void CloseNamespace();
```

- `public CloseScope(System.Int32 end_offset) : System.Void`  

```csharp
public System.Void CloseScope(System.Int32 end_offset);
```

- `public DefineAnonymousScope(System.Int32 id) : System.Void`  

```csharp
public System.Void DefineAnonymousScope(System.Int32 id);
```

- `public DefineCapturedLocal(System.Int32 scope_id, System.String name, System.String captured_name) : System.Void`  

```csharp
public System.Void DefineCapturedLocal(System.Int32 scope_id, System.String name, System.String captured_name);
```

- `public DefineCapturedParameter(System.Int32 scope_id, System.String name, System.String captured_name) : System.Void`  

```csharp
public System.Void DefineCapturedParameter(System.Int32 scope_id, System.String name, System.String captured_name);
```

- `public DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name) : System.Void`  

```csharp
public System.Void DefineCapturedScope(System.Int32 scope_id, System.Int32 id, System.String captured_name);
```

- `public DefineCapturedThis(System.Int32 scope_id, System.String captured_name) : System.Void`  

```csharp
public System.Void DefineCapturedThis(System.Int32 scope_id, System.String captured_name);
```

- `public DefineCompilationUnit(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source) : Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry DefineCompilationUnit(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry source);
```

- `public DefineDocument(System.String url) : Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry DefineDocument(System.String url);
```

- `public DefineDocument(System.String url, System.Byte[] guid, System.Byte[] checksum) : Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry DefineDocument(System.String url, System.Byte[] guid, System.Byte[] checksum);
```

- `public DefineLocalVariable(System.Int32 index, System.String name) : System.Void`  

```csharp
public System.Void DefineLocalVariable(System.Int32 index, System.String name);
```

- `public DefineNamespace(System.String name, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry unit, System.String[] using_clauses, System.Int32 parent) : System.Int32`  

```csharp
public System.Int32 DefineNamespace(System.String name, Colossal.Mono.CompilerServices.SymbolWriter.CompileUnitEntry unit, System.String[] using_clauses, System.Int32 parent);
```

- `public DefineScopeVariable(System.Int32 scope, System.Int32 index) : System.Void`  

```csharp
public System.Void DefineScopeVariable(System.Int32 scope, System.Int32 index);
```

- `public EndIteratorBody(System.Int32 end_offset) : System.Void`  

```csharp
public System.Void EndIteratorBody(System.Int32 end_offset);
```

- `public EndIteratorDispatcher(System.Int32 end_offset) : System.Void`  

```csharp
public System.Void EndIteratorDispatcher(System.Int32 end_offset);
```

- `public MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden) : System.Void`  

```csharp
public System.Void MarkSequencePoint(System.Int32 offset, Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file, System.Int32 line, System.Int32 column, System.Boolean is_hidden);
```

- `public OpenCompilerGeneratedBlock(System.Int32 start_offset) : System.Void`  

```csharp
public System.Void OpenCompilerGeneratedBlock(System.Int32 start_offset);
```

- `public OpenMethod(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit file, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method) : Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder`  

```csharp
public Colossal.Mono.CompilerServices.SymbolWriter.SourceMethodBuilder OpenMethod(Colossal.Mono.CompilerServices.SymbolWriter.ICompileUnit file, System.Int32 ns_id, Colossal.Mono.CompilerServices.SymbolWriter.IMethodDef method);
```

- `public OpenScope(System.Int32 start_offset) : System.Int32`  

```csharp
public System.Int32 OpenScope(System.Int32 start_offset);
```

- `public StartIteratorBody(System.Int32 start_offset) : System.Void`  

```csharp
public System.Void StartIteratorBody(System.Int32 start_offset);
```

- `public StartIteratorDispatcher(System.Int32 start_offset) : System.Void`  

```csharp
public System.Void StartIteratorDispatcher(System.Int32 start_offset);
```

- `public WriteSymbolFile(System.Guid guid) : System.Void`  

```csharp
public System.Void WriteSymbolFile(System.Guid guid);
```


