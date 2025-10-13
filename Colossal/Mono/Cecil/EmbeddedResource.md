# Colossal.Mono.Cecil.EmbeddedResource

**Assembly:** `Colossal.Mono.Cecil`  
**Namespace:** `Colossal.Mono.Cecil`  

**Type:** class sealed public  

**Base:** `Colossal.Mono.Cecil.Resource`  

## Code

```csharp
public sealed class EmbeddedResource : Colossal.Mono.Cecil.Resource
{
    private readonly Colossal.Mono.Cecil.MetadataReader reader;
    private System.Nullable<System.UInt32> offset;
    private System.Byte[] data;
    private System.IO.Stream stream;

    public Colossal.Mono.Cecil.ResourceType ResourceType { get; }

    public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.Byte[] data);
    public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.IO.Stream stream);
    internal EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.UInt32 offset, Colossal.Mono.Cecil.MetadataReader reader);

    public System.Byte[] GetResourceData();
    public System.IO.Stream GetResourceStream();
    private static System.Byte[] ReadStream(System.IO.Stream stream);
}
```


## Fields

- `private readonly Colossal.Mono.Cecil.MetadataReader reader`  

```csharp
private readonly Colossal.Mono.Cecil.MetadataReader reader;
```

- `private System.Nullable<System.UInt32> offset`  

```csharp
private System.Nullable<System.UInt32> offset;
```

- `private System.Byte[] data`  

```csharp
private System.Byte[] data;
```

- `private System.IO.Stream stream`  

```csharp
private System.IO.Stream stream;
```


## Properties

- `public Colossal.Mono.Cecil.ResourceType ResourceType { get }`  

```csharp
public Colossal.Mono.Cecil.ResourceType ResourceType { get; }
```


## Constructors

- `public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.Byte[] data)`  

```csharp
public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.Byte[] data);
```

- `public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.IO.Stream stream)`  

```csharp
public EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.IO.Stream stream);
```

- `internal EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.UInt32 offset, Colossal.Mono.Cecil.MetadataReader reader)`  

```csharp
internal EmbeddedResource(System.String name, Colossal.Mono.Cecil.ManifestResourceAttributes attributes, System.UInt32 offset, Colossal.Mono.Cecil.MetadataReader reader);
```


## Methods

- `public GetResourceData() : System.Byte[]`  

```csharp
public System.Byte[] GetResourceData();
```

- `public GetResourceStream() : System.IO.Stream`  

```csharp
public System.IO.Stream GetResourceStream();
```

- `private static ReadStream(System.IO.Stream stream) : System.Byte[]`  

```csharp
private static System.Byte[] ReadStream(System.IO.Stream stream);
```


