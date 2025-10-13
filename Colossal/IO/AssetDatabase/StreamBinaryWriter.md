# Colossal.IO.AssetDatabase.StreamBinaryWriter

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Unity.Entities.Serialization.BinaryWriter`, `System.IDisposable`  

## Code

```csharp
public class StreamBinaryWriter : Unity.Entities.Serialization.BinaryWriter, System.IDisposable
{
    private System.IO.Stream stream;
    private System.Byte[] buffer;

    public System.Int64 Position { get; set; }
    public System.Int64 Length { get; }

    public StreamBinaryWriter(System.String fileName, System.Int32 bufferSize);
    public StreamBinaryWriter(System.IO.Stream stream, System.Int32 bufferSize);

    public System.Void Dispose();
    public System.Void WriteBytes(System.Void* data, System.Int32 bytes);
}
```


## Fields

- `private System.IO.Stream stream`  

```csharp
private System.IO.Stream stream;
```

- `private System.Byte[] buffer`  

```csharp
private System.Byte[] buffer;
```


## Properties

- `public System.Int64 Position { get; set }`  

```csharp
public System.Int64 Position { get; set; }
```

- `public System.Int64 Length { get }`  

```csharp
public System.Int64 Length { get; }
```


## Constructors

- `public StreamBinaryWriter(System.String fileName, System.Int32 bufferSize = 65536)`  

```csharp
public StreamBinaryWriter(System.String fileName, System.Int32 bufferSize);
```

- `public StreamBinaryWriter(System.IO.Stream stream, System.Int32 bufferSize = 65536)`  

```csharp
public StreamBinaryWriter(System.IO.Stream stream, System.Int32 bufferSize);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public WriteBytes(System.Void* data, System.Int32 bytes) : System.Void`  

```csharp
public System.Void WriteBytes(System.Void* data, System.Int32 bytes);
```


