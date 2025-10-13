# Game.Serialization.WriteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IWriteBufferProvider<Game.Serialization.WriteBuffer>`  

## Code

```csharp
public class WriteSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IWriteBufferProvider<Game.Serialization.WriteBuffer>
{
    private Game.Serialization.SaveGameSystem m_SerializationSystem;
    private Game.Serialization.SerializerSystem m_SerializerSystem;
    private System.Collections.Generic.List<System.ValueTuple<Game.Serialization.WriteBuffer, Colossal.Serialization.Entities.BufferFormat>> m_Buffers;
    private Unity.Jobs.JobHandle m_WriteDependency;
    private System.Runtime.InteropServices.GCHandle m_WriterHandle;

    public Unity.Jobs.JobHandle writeDependency { get; }

    public WriteSystem();

    public Game.Serialization.WriteBuffer AddBuffer(Colossal.Serialization.Entities.BufferFormat format);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void WriteBuffer(Game.Serialization.WriteBuffer buffer, Colossal.Serialization.Entities.BufferFormat format);
    private static System.Void WriteData<T>(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, T data);
    private static System.Void WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeArray<System.Byte> data);
    private static System.Void WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeSlice<System.Byte> data);
}
```


## Fields

- `private Game.Serialization.SaveGameSystem m_SerializationSystem`  

```csharp
private Game.Serialization.SaveGameSystem m_SerializationSystem;
```

- `private Game.Serialization.SerializerSystem m_SerializerSystem`  

```csharp
private Game.Serialization.SerializerSystem m_SerializerSystem;
```

- `private System.Collections.Generic.List<System.ValueTuple<Game.Serialization.WriteBuffer, Colossal.Serialization.Entities.BufferFormat>> m_Buffers`  

```csharp
private System.Collections.Generic.List<System.ValueTuple<Game.Serialization.WriteBuffer, Colossal.Serialization.Entities.BufferFormat>> m_Buffers;
```

- `private Unity.Jobs.JobHandle m_WriteDependency`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependency;
```

- `private System.Runtime.InteropServices.GCHandle m_WriterHandle`  

```csharp
private System.Runtime.InteropServices.GCHandle m_WriterHandle;
```


## Properties

- `public Unity.Jobs.JobHandle writeDependency { get }`  

```csharp
public Unity.Jobs.JobHandle writeDependency { get; }
```


## Constructors

- `public WriteSystem()`  

```csharp
public WriteSystem();
```


## Methods

- `public AddBuffer(Colossal.Serialization.Entities.BufferFormat format) : Game.Serialization.WriteBuffer`  

```csharp
public Game.Serialization.WriteBuffer AddBuffer(Colossal.Serialization.Entities.BufferFormat format);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private WriteBuffer(Game.Serialization.WriteBuffer buffer, Colossal.Serialization.Entities.BufferFormat format) : System.Void`  

```csharp
private System.Void WriteBuffer(Game.Serialization.WriteBuffer buffer, Colossal.Serialization.Entities.BufferFormat format);
```

- `private static WriteData<T>(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, T data) : System.Void`  

```csharp
private static System.Void WriteData<T>(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, T data);
```

- `private static WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeArray<System.Byte> data) : System.Void`  

```csharp
private static System.Void WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeArray<System.Byte> data);
```

- `private static WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeSlice<System.Byte> data) : System.Void`  

```csharp
private static System.Void WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeSlice<System.Byte> data);
```


## Nested types

- `Game.Serialization.WriteSystem+WriteRawBufferJob`  
- `Game.Serialization.WriteSystem+WriteCompressedBufferJob`  
- `Game.Serialization.WriteSystem+DisposeWriterJob`  
- `Game.Serialization.WriteSystem+BufferHeader`  

