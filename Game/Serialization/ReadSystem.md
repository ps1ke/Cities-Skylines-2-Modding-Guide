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
public ReadSystem();
```


## Methods

- `private Clear() : System.Void`  

```csharp
private System.Void Clear();
```

- `public GetBuffer(Colossal.Serialization.Entities.BufferFormat format) : Game.Serialization.ReadBuffer`  

```csharp
public Game.Serialization.ReadBuffer GetBuffer(Colossal.Serialization.Entities.BufferFormat format);
```

- `public GetBuffer(Colossal.Serialization.Entities.BufferFormat format, Unity.Jobs.JobHandle& dependency) : Game.Serialization.ReadBuffer`  

```csharp
public Game.Serialization.ReadBuffer GetBuffer(Colossal.Serialization.Entities.BufferFormat format, Unity.Jobs.JobHandle& dependency);
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

- `private static ReadData<T>(Colossal.IO.AssetDatabase.StreamBinaryReader reader, T& data) : System.Void`  

```csharp
private static System.Void ReadData<T>(Colossal.IO.AssetDatabase.StreamBinaryReader reader, T& data);
```

- `private static ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data) : System.Void`  

```csharp
private static System.Void ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data);
```

- `private static ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data, Unity.Jobs.JobHandle& dependency) : System.Void`  

```csharp
private static System.Void ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data, Unity.Jobs.JobHandle& dependency);
```


## Nested types

- `Game.Serialization.ReadSystem+BufferHeader`  
- `Game.Serialization.ReadSystem+<>c`  

