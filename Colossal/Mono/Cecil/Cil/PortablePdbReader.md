# Colossal.Mono.Cecil.Cil.PortablePdbReader

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.Mono.Cecil.Cil.ISymbolReader`, `System.IDisposable`  

## Code

```csharp
public sealed class PortablePdbReader : Colossal.Mono.Cecil.Cil.ISymbolReader, System.IDisposable
{
    private readonly Colossal.Mono.Cecil.PE.Image image;
    private readonly Colossal.Mono.Cecil.ModuleDefinition module;
    private readonly Colossal.Mono.Cecil.MetadataReader reader;
    private readonly Colossal.Mono.Cecil.MetadataReader debug_reader;

    private System.Boolean IsEmbedded { private get; }

    internal PortablePdbReader(Colossal.Mono.Cecil.PE.Image image, Colossal.Mono.Cecil.ModuleDefinition module);

    public System.Void Dispose();
    public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
    private static System.Boolean IsMatchingEntry(Colossal.Mono.Cecil.Metadata.PdbHeap heap, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);
    public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
    public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
    private System.Void ReadCustomDebugInformations(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
    private static System.Int32 ReadInt32(System.Byte[] bytes, System.Int32 start);
    private System.Void ReadModule();
    private System.Void ReadScope(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info);
    private System.Void ReadSequencePoints(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info);
    private System.Void ReadStateMachineKickOffMethod(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.PE.Image image`  

```csharp
private readonly Colossal.Mono.Cecil.PE.Image image;
```

- `private readonly Colossal.Mono.Cecil.ModuleDefinition module`  

```csharp
private readonly Colossal.Mono.Cecil.ModuleDefinition module;
```

- `private readonly Colossal.Mono.Cecil.MetadataReader reader`  

```csharp
private readonly Colossal.Mono.Cecil.MetadataReader reader;
```

- `private readonly Colossal.Mono.Cecil.MetadataReader debug_reader`  

```csharp
private readonly Colossal.Mono.Cecil.MetadataReader debug_reader;
```


## Properties

- `private System.Boolean IsEmbedded { private get }`  

```csharp
private System.Boolean IsEmbedded { private get; }
```


## Constructors

- `internal PortablePdbReader(Colossal.Mono.Cecil.PE.Image image, Colossal.Mono.Cecil.ModuleDefinition module)`  

```csharp
internal PortablePdbReader(Colossal.Mono.Cecil.PE.Image image, Colossal.Mono.Cecil.ModuleDefinition module);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetWriterProvider() : Colossal.Mono.Cecil.Cil.ISymbolWriterProvider`  

```csharp
public Colossal.Mono.Cecil.Cil.ISymbolWriterProvider GetWriterProvider();
```

- `private static IsMatchingEntry(Colossal.Mono.Cecil.Metadata.PdbHeap heap, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry) : System.Boolean`  

```csharp
private static System.Boolean IsMatchingEntry(Colossal.Mono.Cecil.Metadata.PdbHeap heap, Colossal.Mono.Cecil.Cil.ImageDebugHeaderEntry entry);
```

- `public ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header) : System.Boolean`  

```csharp
public System.Boolean ProcessDebugHeader(Colossal.Mono.Cecil.Cil.ImageDebugHeader header);
```

- `public Read(Colossal.Mono.Cecil.MethodDefinition method) : Colossal.Mono.Cecil.Cil.MethodDebugInformation`  

```csharp
public Colossal.Mono.Cecil.Cil.MethodDebugInformation Read(Colossal.Mono.Cecil.MethodDefinition method);
```

- `private ReadCustomDebugInformations(Colossal.Mono.Cecil.Cil.MethodDebugInformation info) : System.Void`  

```csharp
private System.Void ReadCustomDebugInformations(Colossal.Mono.Cecil.Cil.MethodDebugInformation info);
```

- `private static ReadInt32(System.Byte[] bytes, System.Int32 start) : System.Int32`  

```csharp
private static System.Int32 ReadInt32(System.Byte[] bytes, System.Int32 start);
```

- `private ReadModule() : System.Void`  

```csharp
private System.Void ReadModule();
```

- `private ReadScope(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info) : System.Void`  

```csharp
private System.Void ReadScope(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info);
```

- `private ReadSequencePoints(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info) : System.Void`  

```csharp
private System.Void ReadSequencePoints(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info);
```

- `private ReadStateMachineKickOffMethod(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info) : System.Void`  

```csharp
private System.Void ReadStateMachineKickOffMethod(Colossal.Mono.Cecil.Cil.MethodDebugInformation method_info);
```


