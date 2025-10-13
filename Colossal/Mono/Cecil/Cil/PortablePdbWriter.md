# Colossal.Mono.Cecil.Cil.PortablePdbWriter

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolWriter`, `System.IDisposable`  

## Code

```csharp
public sealed class PortablePdbWriter : Colossal.Mono.Cecil.Cil.ISymbolWriter, System.IDisposable
{
    private readonly Colossal.Mono.Cecil.MetadataBuilder pdb_metadata;
    private readonly Colossal.Mono.Cecil.ModuleDefinition module;
    private readonly Colossal.Mono.Cecil.PE.ImageWriter writer;
    private Colossal.Mono.Cecil.MetadataBuilder module_metadata;

    private System.Boolean IsEmbedded { private get; }

    internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module);
    internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.PE.ImageWriter writer);

    private System.Void CheckMethodDebugInformationTable();
    public System.Void Dispose();
    public Colossal.Mono.Cecil.Cil.ImageDebugHeader GetDebugHeader();
    public Colossal.Mono.Cecil.Cil.ISymbolReaderProvider GetReaderProvider();
    public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private System.Void WritePdbFile();
    private System.Void WritePdbHeap();
    private System.Void WriteTableHeap();
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.MetadataBuilder pdb_metadata`  

```csharp
private readonly Colossal.Mono.Cecil.MetadataBuilder pdb_metadata;
```

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
private readonly Colossal.Mono.Cecil.ModuleDefinition module;
```

- `private readonly Colossal.Mono.Cecil.PE.ImageWriter writer`  

```csharp
private readonly Colossal.Mono.Cecil.PE.ImageWriter writer;
```

- `private Colossal.Mono.Cecil.MetadataBuilder module_metadata`  

```csharp
private Colossal.Mono.Cecil.MetadataBuilder module_metadata;
```


## Properties

- `private System.Boolean IsEmbedded { private get }`  

```csharp
private System.Boolean IsEmbedded { private get; }
```


## Constructors

- `internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module)`  

```csharp
internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module);
```

- `internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.PE.ImageWriter writer)`  

```csharp
internal PortablePdbWriter(Colossal.Mono.Cecil.MetadataBuilder pdb_metadata, Colossal.Mono.Cecil.ModuleDefinition module, Colossal.Mono.Cecil.PE.ImageWriter writer);
```


## Methods

- `private CheckMethodDebugInformationTable() : System.Void`  

```csharp
private System.Void CheckMethodDebugInformationTable();
```

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

- `public Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
public System.Void Write(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private WritePdbFile() : System.Void`  

```csharp
private System.Void WritePdbFile();
```

- `private WritePdbHeap() : System.Void`  

```csharp
private System.Void WritePdbHeap();
```

- `private WriteTableHeap() : System.Void`  

```csharp
private System.Void WriteTableHeap();
```


