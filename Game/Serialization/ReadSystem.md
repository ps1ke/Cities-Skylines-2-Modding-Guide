# Game.Serialization.ReadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IReadBufferProvider<Game.Serialization.ReadBuffer>`  

## Code

```csharp
public class ReadSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IReadBufferProvider<Game.Serialization.ReadBuffer>
{
    private Game.Serialization.LoadGameSystem m_DeserializationSystem;
    private Game.Serialization.SerializerSystem m_SerializerSystem;
    private Colossal.IO.AssetDatabase.StreamBinaryReader m_Reader;

    public ReadSystem();

    private System.Void Clear();
    public Game.Serialization.ReadBuffer GetBuffer(Colossal.Serialization.Entities.BufferFormat format);
    public Game.Serialization.ReadBuffer GetBuffer(Colossal.Serialization.Entities.BufferFormat format, Unity.Jobs.JobHandle& dependency);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private static System.Void ReadData<T>(Colossal.IO.AssetDatabase.StreamBinaryReader reader, T& data);
    private static System.Void ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data);
    private static System.Void ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data, Unity.Jobs.JobHandle& dependency);
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_DeserializationSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_DeserializationSystem;
```

- `private Game.Serialization.SerializerSystem m_SerializerSystem`  

```csharp
private Game.Serialization.SerializerSystem m_SerializerSystem;
```

- `private Colossal.IO.AssetDatabase.StreamBinaryReader m_Reader`  

```csharp
private Colossal.IO.AssetDatabase.StreamBinaryReader m_Reader;
```


## Constructors

- `public ReadSystem()`  

```csharp
[Preserve]
	public ReadSystem()
	{
	}
```


## Methods

- `private Clear() : System.Void`  

```csharp
private void Clear()
	{
		if (m_Reader != null)
		{
			m_Reader.Dispose();
			m_Reader = null;
		}
	}
```

- `public GetBuffer(Colossal.Serialization.Entities.BufferFormat format) : Game.Serialization.ReadBuffer`  

```csharp
public unsafe ReadBuffer GetBuffer(BufferFormat format, out JobHandle dependency)
	{
		dependency = default(JobHandle);
		if (m_DeserializationSystem.dataDescriptor == AsyncReadDescriptor.Invalid)
		{
			return null;
		}
		if (m_Reader == null)
		{
			m_Reader = new StreamBinaryReader(m_DeserializationSystem.dataDescriptor, 65536L);
		}
		BufferHeader data = default(BufferHeader);
		if (format.IsCompressed())
		{
			ReadData(m_Reader, out data);
			m_SerializerSystem.totalSize += sizeof(BufferHeader);
		}
		else
		{
			ReadData(m_Reader, out data.size);
			m_SerializerSystem.totalSize += 4;
		}
		ReadBuffer readBuffer = new ReadBuffer(data.size);
		m_SerializerSystem.totalSize += data.size;
		if (format.IsCompressed())
		{
			NativeArray<byte> nativeArray = new NativeArray<byte>(data.compressedSize, Allocator.Persistent);
			ReadData(m_Reader, nativeArray, out dependency);
			dependency = CompressionUtils.Decompress(SerializationUtils.BufferToCompressionFormat(format), nativeArray, readBuffer.buffer, dependency);
			nativeArray.Dispose(dependency);
		}
		else if (format == BufferFormat.Raw)
		{
			ReadData(m_Reader, readBuffer.buffer, out dependency);
		}
		else
		{
			COSystemBase.baseLog.WarnFormat("Unsupported BufferFormat {0}", format);
		}
		return readBuffer;
	}
```

- `public GetBuffer(Colossal.Serialization.Entities.BufferFormat format, Unity.Jobs.JobHandle& dependency) : Game.Serialization.ReadBuffer`  

```csharp
public unsafe ReadBuffer GetBuffer(BufferFormat format, out JobHandle dependency)
	{
		dependency = default(JobHandle);
		if (m_DeserializationSystem.dataDescriptor == AsyncReadDescriptor.Invalid)
		{
			return null;
		}
		if (m_Reader == null)
		{
			m_Reader = new StreamBinaryReader(m_DeserializationSystem.dataDescriptor, 65536L);
		}
		BufferHeader data = default(BufferHeader);
		if (format.IsCompressed())
		{
			ReadData(m_Reader, out data);
			m_SerializerSystem.totalSize += sizeof(BufferHeader);
		}
		else
		{
			ReadData(m_Reader, out data.size);
			m_SerializerSystem.totalSize += 4;
		}
		ReadBuffer readBuffer = new ReadBuffer(data.size);
		m_SerializerSystem.totalSize += data.size;
		if (format.IsCompressed())
		{
			NativeArray<byte> nativeArray = new NativeArray<byte>(data.compressedSize, Allocator.Persistent);
			ReadData(m_Reader, nativeArray, out dependency);
			dependency = CompressionUtils.Decompress(SerializationUtils.BufferToCompressionFormat(format), nativeArray, readBuffer.buffer, dependency);
			nativeArray.Dispose(dependency);
		}
		else if (format == BufferFormat.Raw)
		{
			ReadData(m_Reader, readBuffer.buffer, out dependency);
		}
		else
		{
			COSystemBase.baseLog.WarnFormat("Unsupported BufferFormat {0}", format);
		}
		return readBuffer;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_DeserializationSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_SerializerSystem = base.World.GetOrCreateSystemManaged<SerializerSystem>();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		Clear();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		Clear();
	}
```

- `private static ReadData<T>(Colossal.IO.AssetDatabase.StreamBinaryReader reader, T& data) : System.Void`  

```csharp
private static System.Void ReadData<T>(Colossal.IO.AssetDatabase.StreamBinaryReader reader, T& data);
```

- `private static ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data) : System.Void`  

```csharp
private unsafe static void ReadData(StreamBinaryReader reader, NativeArray<byte> data, out JobHandle dependency)
	{
		void* unsafePtr = data.GetUnsafePtr();
		reader.ReadBytes(unsafePtr, data.Length, out dependency);
	}
```

- `private static ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data, Unity.Jobs.JobHandle& dependency) : System.Void`  

```csharp
private unsafe static void ReadData(StreamBinaryReader reader, NativeArray<byte> data, out JobHandle dependency)
	{
		void* unsafePtr = data.GetUnsafePtr();
		reader.ReadBytes(unsafePtr, data.Length, out dependency);
	}
```


## Nested types

- `Game.Serialization.ReadSystem+BufferHeader`  
- `Game.Serialization.ReadSystem+<>c`  

