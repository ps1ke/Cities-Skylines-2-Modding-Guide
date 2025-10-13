# Colossal.IO.AssetDatabase.StreamBinaryReader

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Unity.Entities.Serialization.BinaryReader`, `System.IDisposable`  

## Code

```csharp
public class StreamBinaryReader : Unity.Entities.Serialization.BinaryReader, System.IDisposable
{
    private readonly System.String filePath;
    private System.Int64 <Position>k__BackingField;

    public System.Int64 Position { get; set; }

    public StreamBinaryReader(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.Int64 bufferSize);

    public System.Void Dispose();
    public System.Void ReadBytes(System.Void* data, System.Int32 bytes);
    public System.Void ReadBytes(System.Void* data, System.Int32 bytes, Unity.Jobs.JobHandle& dependency);
}
```


## Fields

- `private readonly System.String filePath`  

```csharp
private readonly System.String filePath;
```

- `private System.Int64 <Position>k__BackingField`  

```csharp
private System.Int64 <Position>k__BackingField;
```


## Properties

- `public System.Int64 Position { get; set }`  

```csharp
public System.Int64 Position { get; set; }
```


## Constructors

- `public StreamBinaryReader(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.Int64 bufferSize = 65536)`  

```csharp
public StreamBinaryReader(Colossal.IO.AssetDatabase.AsyncReadDescriptor desc, System.Int64 bufferSize);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public ReadBytes(System.Void* data, System.Int32 bytes) : System.Void`  

```csharp
public System.Void ReadBytes(System.Void* data, System.Int32 bytes);
```

- `public ReadBytes(System.Void* data, System.Int32 bytes, Unity.Jobs.JobHandle& dependency) : System.Void`  

```csharp
public System.Void ReadBytes(System.Void* data, System.Int32 bytes, Unity.Jobs.JobHandle& dependency);
```


