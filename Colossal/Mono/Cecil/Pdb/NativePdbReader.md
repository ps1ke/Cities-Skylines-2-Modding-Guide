# Colossal.Mono.Cecil.Pdb.NativePdbReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Pdb`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReader`, `System.IDisposable`  

## Code

```csharp
public class NativePdbReader : Colossal.Mono.Cecil.Cil.ISymbolReader, System.IDisposable
{
    private readonly Colossal.Mono.Disposable<System.IO.Stream> pdb_file;
    private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents;
    private readonly System.Collections.Generic.Dictionary<System.UInt32, Microsoft.Cci.Pdb.PdbFunction> functions;
    private readonly System.Collections.Generic.Dictionary<Microsoft.Cci.Pdb.PdbScope, Colossal.Mono.Cecil.Cil.ImportDebugInformation> imports;

    internal NativePdbReader(Colossal.Mono.Disposable<System.IO.Stream> file);

    private static System.Boolean AddScope(Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> scopes, Colossal.Mono.Cecil.Cil.ScopeDebugInformation scope);
    public System.Void Dispose();
    private Colossal.Mono.Cecil.Cil.Document GetDocument(Microsoft.Cci.Pdb.PdbSource source);
    private Colossal.Mono.Cecil.Cil.ImportDebugInformation GetImport(System.UInt32 token, Colossal.Mono.Cecil.ModuleDefinition module);
    private static Colossal.Mono.Cecil.Cil.ImportDebugInformation GetImport(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.ModuleDefinition module);
    public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
    private static System.Boolean IsMatchingEntry(Microsoft.Cci.Pdb.PdbInfo info, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);
    public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
    public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
    private static System.Int32 ReadInt32(System.Byte[] bytes, System.Int32 start);
    private static System.Void ReadLine(Microsoft.Cci.Pdb.PdbLine line, Colossal.Mono.Cecil.Cil.Document document, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void ReadLines(Microsoft.Cci.Pdb.PdbLines lines, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope[] scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private Colossal.Mono.Cecil.Cil.ScopeDebugInformation ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void ReadSequencePoints(Microsoft.Cci.Pdb.PdbFunction function, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
}
```


## Fields

- `private readonly Colossal.Mono.Disposable<System.IO.Stream> pdb_file`  

```csharp
private readonly Colossal.Mono.Disposable<System.IO.Stream> pdb_file;
```

- `private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.String, Colossal.Mono.Cecil.Cil.Document> documents;
```

- `private readonly System.Collections.Generic.Dictionary<System.UInt32, Microsoft.Cci.Pdb.PdbFunction> functions`  

```csharp
private readonly System.Collections.Generic.Dictionary<System.UInt32, Microsoft.Cci.Pdb.PdbFunction> functions;
```

- `private readonly System.Collections.Generic.Dictionary<Microsoft.Cci.Pdb.PdbScope, Colossal.Mono.Cecil.Cil.ImportDebugInformation> imports`  

```csharp
private readonly System.Collections.Generic.Dictionary<Microsoft.Cci.Pdb.PdbScope, Colossal.Mono.Cecil.Cil.ImportDebugInformation> imports;
```


## Constructors

- `internal NativePdbReader(Colossal.Mono.Disposable<System.IO.Stream> file)`  

```csharp
internal NativePdbReader(Colossal.Mono.Disposable<System.IO.Stream> file);
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

- `private GetDocument(Microsoft.Cci.Pdb.PdbSource source) : Colossal.Mono.Cecil.Cil.Document`  

```csharp
private Colossal.Mono.Cecil.Cil.Document GetDocument(Microsoft.Cci.Pdb.PdbSource source);
```

- `private GetImport(System.UInt32 token, Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.Cil.ImportDebugInformation`  

```csharp
private Colossal.Mono.Cecil.Cil.ImportDebugInformation GetImport(System.UInt32 token, Colossal.Mono.Cecil.ModuleDefinition module);
```

- `private static GetImport(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.ModuleDefinition module) : Colossal.Mono.Cecil.Cil.ImportDebugInformation`  

```csharp
private static Colossal.Mono.Cecil.Cil.ImportDebugInformation GetImport(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.ModuleDefinition module);
```

- `public GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
```

- `private static IsMatchingEntry(Microsoft.Cci.Pdb.PdbInfo info, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry) : System.Boolean`  

```csharp
private static System.Boolean IsMatchingEntry(Microsoft.Cci.Pdb.PdbInfo info, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);
```

- `public ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  

```csharp
public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
```

- `public Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  

```csharp
public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
```

- `private static ReadInt32(System.Byte[] bytes, System.Int32 start) : System.Int32`  

```csharp
private static System.Int32 ReadInt32(System.Byte[] bytes, System.Int32 start);
```

- `private static ReadLine(Microsoft.Cci.Pdb.PdbLine line, Colossal.Mono.Cecil.Cil.Document document, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private static System.Void ReadLine(Microsoft.Cci.Pdb.PdbLine line, Colossal.Mono.Cecil.Cil.Document document, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private ReadLines(Microsoft.Cci.Pdb.PdbLines lines, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void ReadLines(Microsoft.Cci.Pdb.PdbLines lines, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope[] scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation>`  

```csharp
private Colossal.Mono.Collections.Generic.Collection<Colossal.Mono.Cecil.Cil.ScopeDebugInformation> ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope[] scopes, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : Colossal.Mono.Cecil.Cil.ScopeDebugInformation`  

```csharp
private Colossal.Mono.Cecil.Cil.ScopeDebugInformation ReadScopeAndLocals(Microsoft.Cci.Pdb.PdbScope scope, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private ReadSequencePoints(Microsoft.Cci.Pdb.PdbFunction function, Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void ReadSequencePoints(Microsoft.Cci.Pdb.PdbFunction function, Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```


## Nested types

- `Colossal.Mono.Cecil.Pdb.NativePdbReader+<>c`  

