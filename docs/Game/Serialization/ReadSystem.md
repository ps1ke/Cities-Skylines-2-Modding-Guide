# Game.Serialization.ReadSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IReadBufferProvider<Game.Serialization.ReadBuffer>`  

## Fields

- `private Game.Serialization.LoadGameSystem m_DeserializationSystem`  
- `private Game.Serialization.SerializerSystem m_SerializerSystem`  
- `private Colossal.IO.AssetDatabase.StreamBinaryReader m_Reader`  

## Constructors

- `public ReadSystem()`  

## Methods

- `private Clear() : System.Void`  
- `public GetBuffer(Colossal.Serialization.Entities.BufferFormat format) : Game.Serialization.ReadBuffer`  
- `public GetBuffer(Colossal.Serialization.Entities.BufferFormat format, Unity.Jobs.JobHandle& dependency) : Game.Serialization.ReadBuffer`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private static ReadData<T>(Colossal.IO.AssetDatabase.StreamBinaryReader reader, T& data) : System.Void`  
- `private static ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data) : System.Void`  
- `private static ReadData(Colossal.IO.AssetDatabase.StreamBinaryReader reader, Unity.Collections.NativeArray<System.Byte> data, Unity.Jobs.JobHandle& dependency) : System.Void`  

## Nested types

- `Game.Serialization.ReadSystem+BufferHeader`  
- `Game.Serialization.ReadSystem+<>c`  

