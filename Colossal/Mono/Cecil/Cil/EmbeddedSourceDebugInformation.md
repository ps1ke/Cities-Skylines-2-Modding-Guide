# Colossal.Mono.Cecil.Cil.EmbeddedSourceDebugInformation

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil.Cil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Cil.CustomDebugInformation`  
**Implements:** `Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider`, `Colossal.Mono.Cecil.IMetadataTokenProvider`  

## Code

```csharp
public sealed class EmbeddedSourceDebugInformation : Colossal.Mono.Cecil.Cil.CustomDebugInformation, Colossal.Mono.Cecil.Cil.ICustomDebugInformationProvider, Colossal.Mono.Cecil.IMetadataTokenProvider
{
    internal System.UInt32 index;
    internal Colossal.Mono.Cecil.MetadataReader debug_reader;
    internal System.Boolean resolved;
    internal System.Byte[] content;
    internal System.Boolean compress;
    public static System.Guid KindIdentifier;

    public System.Byte[] Content { get; set; }
    public System.Boolean Compress { get; set; }
    public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }

    internal EmbeddedSourceDebugInformation(System.UInt32 index, Colossal.Mono.Cecil.MetadataReader debug_reader);
    public EmbeddedSourceDebugInformation(System.Byte[] content, System.Boolean compress);

    internal System.Byte[] ReadRawEmbeddedSourceDebugInformation();
    private System.Void Resolve();
}
```


## Fields

- `internal System.UInt32 index`  

```csharp
internal System.UInt32 index;
```

- `internal Colossal.Mono.Cecil.MetadataReader debug_reader`  

```csharp
internal Colossal.Mono.Cecil.MetadataReader debug_reader;
```

- `internal System.Boolean resolved`  

```csharp
internal System.Boolean resolved;
```

- `internal System.Byte[] content`  

```csharp
internal System.Byte[] content;
```

- `internal System.Boolean compress`  

```csharp
internal System.Boolean compress;
```

- `public static System.Guid KindIdentifier`  

```csharp
public static System.Guid KindIdentifier;
```


## Properties

- `public System.Byte[] Content { get; set }`  

```csharp
public System.Byte[] Content { get; set; }
```

- `public System.Boolean Compress { get; set }`  

```csharp
public System.Boolean Compress { get; set; }
```

- `public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get }`  

```csharp
public Colossal.Mono.Cecil.Cil.CustomDebugInformationKind Kind { get; }
```


## Constructors

- `internal EmbeddedSourceDebugInformation(System.UInt32 index, Colossal.Mono.Cecil.MetadataReader debug_reader)`  

```csharp
internal EmbeddedSourceDebugInformation(System.UInt32 index, Colossal.Mono.Cecil.MetadataReader debug_reader);
```

- `public EmbeddedSourceDebugInformation(System.Byte[] content, System.Boolean compress)`  

```csharp
public EmbeddedSourceDebugInformation(System.Byte[] content, System.Boolean compress);
```


## Methods

- `internal ReadRawEmbeddedSourceDebugInformation() : System.Byte[]`  

```csharp
internal System.Byte[] ReadRawEmbeddedSourceDebugInformation();
```

- `private Resolve() : System.Void`  

```csharp
private System.Void Resolve();
```


