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
[Preserve]
	public WriteSystem()
	{
	}
```


## Methods

- `public AddBuffer(Colossal.Serialization.Entities.BufferFormat format) : Game.Serialization.WriteBuffer`  

```csharp
public WriteBuffer AddBuffer(BufferFormat format)
	{
		int num = 0;
		for (int i = 0; i < m_Buffers.Count; i++)
		{
			var (writeBuffer, format2) = m_Buffers[i];
			if (!writeBuffer.isCompleted)
			{
				break;
			}
			WriteBuffer(writeBuffer, format2);
			num++;
		}
		if (num != 0)
		{
			m_Buffers.RemoveRange(0, num);
		}
		WriteBuffer writeBuffer2 = new WriteBuffer();
		m_Buffers.Add((writeBuffer2, format));
		return writeBuffer2;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SerializationSystem = base.World.GetOrCreateSystemManaged<SaveGameSystem>();
		m_SerializerSystem = base.World.GetOrCreateSystemManaged<SerializerSystem>();
		m_Buffers = new List<(WriteBuffer, BufferFormat)>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_WriteDependency.Complete();
		for (int i = 0; i < m_Buffers.Count; i++)
		{
			m_Buffers[i].Item1.Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		for (int i = 0; i < m_Buffers.Count; i++)
		{
			var (buffer, format) = m_Buffers[i];
			WriteBuffer(buffer, format);
		}
		m_Buffers.Clear();
		if (m_WriterHandle.IsAllocated)
		{
			DisposeWriterJob jobData = new DisposeWriterJob
			{
				m_WriterHandle = m_WriterHandle
			};
			m_WriterHandle = default(GCHandle);
			m_WriteDependency = jobData.Schedule(m_WriteDependency);
		}
	}
```

- `private WriteBuffer(Game.Serialization.WriteBuffer buffer, Colossal.Serialization.Entities.BufferFormat format) : System.Void`  

```csharp
private void WriteBuffer(WriteBuffer buffer, BufferFormat format)
	{
		if (!m_WriterHandle.IsAllocated)
		{
			StreamBinaryWriter value = new StreamBinaryWriter(m_SerializationSystem.stream);
			m_WriterHandle = GCHandle.Alloc(value);
		}
		buffer.CompleteDependencies();
		if (format == BufferFormat.Raw)
		{
			m_SerializerSystem.totalSize += 4 + buffer.buffer.Length;
			WriteRawBufferJob jobData = new WriteRawBufferJob
			{
				m_Buffer = buffer.buffer,
				m_WriterHandle = m_WriterHandle
			};
			m_WriteDependency = jobData.Schedule(m_WriteDependency);
			buffer.buffer.Dispose(m_WriteDependency);
		}
		else if (format.IsCompressed())
		{
			m_SerializerSystem.totalSize += 8 + buffer.buffer.Length;
			CompressionFormat format2 = SerializationUtils.BufferToCompressionFormat(format);
			CompressedBytesStorage compressedBytesStorage = new CompressedBytesStorage(format2, buffer.buffer.Length, Allocator.Persistent);
			int compressionLevel = 3;
			JobHandle jobHandle = CompressionUtils.Compress(format2, buffer.buffer.AsArray(), compressedBytesStorage, default(JobHandle), compressionLevel);
			WriteCompressedBufferJob jobData2 = new WriteCompressedBufferJob
			{
				m_CompressedData = compressedBytesStorage,
				m_UncompressedSize = buffer.buffer.Length,
				m_WriterHandle = m_WriterHandle
			};
			buffer.buffer.Dispose(jobHandle);
			m_WriteDependency = jobData2.Schedule(JobHandle.CombineDependencies(m_WriteDependency, jobHandle));
			compressedBytesStorage.Dispose(m_WriteDependency);
		}
		else
		{
			COSystemBase.baseLog.WarnFormat("Unsupported BufferFormat {0}", format);
		}
	}
```

- `private static WriteData<T>(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, T data) : System.Void`  

```csharp
private static System.Void WriteData<T>(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, T data);
```

- `private static WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeArray<System.Byte> data) : System.Void`  

```csharp
private unsafe static void WriteData(StreamBinaryWriter writer, NativeSlice<byte> data)
	{
		void* unsafeReadOnlyPtr = data.GetUnsafeReadOnlyPtr();
		writer.WriteBytes(unsafeReadOnlyPtr, data.Length);
	}
```

- `private static WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeSlice<System.Byte> data) : System.Void`  

```csharp
private unsafe static void WriteData(StreamBinaryWriter writer, NativeSlice<byte> data)
	{
		void* unsafeReadOnlyPtr = data.GetUnsafeReadOnlyPtr();
		writer.WriteBytes(unsafeReadOnlyPtr, data.Length);
	}
```


## Nested types

- `Game.Serialization.WriteSystem+WriteRawBufferJob`  
- `Game.Serialization.WriteSystem+WriteCompressedBufferJob`  
- `Game.Serialization.WriteSystem+DisposeWriterJob`  
- `Game.Serialization.WriteSystem+BufferHeader`  

