# Colossal.Mono.Cecil.Mdb.MdbReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Mdb`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReader`, `System.IDisposable`  

## Code

```csharp
public sealed class MdbReader : Colossal.Mono.Cecil.Cil.ISymbolReader, System.IDisposable
{
    private readonly Colossal.Mono.Cecil.ModuleDefinition module;
    private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symbol_file;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents;

    public MdbReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symFile);

    private static System.Boolean AddScope(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope);
    public System.Void Dispose();
    private Colossal.Mono.Cecil.Cil.Document GetDocument(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file);
    public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
    private Colossal.Mono.Cecil.Cil.SequencePoint LineToSequencePoint(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry line);
    public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
    public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
    private static System.Int32 ReadCodeSize(Colossal.Mono.Cecil.MethodDefinition method);
    private System.Void ReadLineNumbers(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private static System.Void ReadLocalVariables(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.ScopeDebugInformation[] scopes);
    private static Colossal.Mono.Cecil.Cil.ScopeDebugInformation[] ReadScopes(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
private readonly Colossal.Mono.Cecil.ModuleDefinition module;
```

- `private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symbol_file`  

```csharp
private readonly Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symbol_file;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents;
```


## Constructors

- `public MdbReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symFile)`  

```csharp
public MdbReader(Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.CompilerServices.SymbolWriter.MonoSymbolFile symFile);
```


## Methods

- `private static AddScope(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope) : System.Boolean`  

```csharp
private static System.Boolean AddScope(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private GetDocument(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file) : Colossal.Mono.Cecil.Cil.Document`  

```csharp
private Colossal.Mono.Cecil.Cil.Document GetDocument(Colossal.Mono.CompilerServices.SymbolWriter.SourceFileEntry file);
```

- `public GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
```

- `private LineToSequencePoint(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry line) : Colossal.Mono.Cecil.Cil.SequencePoint`  

```csharp
private Colossal.Mono.Cecil.Cil.SequencePoint LineToSequencePoint(Colossal.Mono.CompilerServices.SymbolWriter.LineNumberEntry line);
```

- `public ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  

```csharp
public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
```

- `public Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  

```csharp
public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
```

- `private static ReadCodeSize(Colossal.Mono.Cecil.MethodDefinition method) : System.Int32`  

```csharp
private static System.Int32 ReadCodeSize(Colossal.Mono.Cecil.MethodDefinition method);
```

- `private ReadLineNumbers(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void ReadLineNumbers(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private static ReadLocalVariables(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.ScopeDebugInformation[] scopes) : System.Void`  

```csharp
private static System.Void ReadLocalVariables(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.ScopeDebugInformation[] scopes);
```

- `private static ReadScopes(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : Colossal.Mono.Cecil.Cil.ScopeDebugInformation[]`  

```csharp
private static Colossal.Mono.Cecil.Cil.ScopeDebugInformation[] ReadScopes(Colossal.Mono.CompilerServices.SymbolWriter.MethodEntry entry, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```


## Nested types

- `Colossal.Mono.Cecil.Mdb.MdbReader+<>c`  

