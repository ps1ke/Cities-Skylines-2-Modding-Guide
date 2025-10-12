# Game.Serialization.WriteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IWriteBufferProvider<Game.Serialization.WriteBuffer>`  

## Fields

- `private Game.Serialization.SaveGameSystem m_SerializationSystem`  
- `private Game.Serialization.SerializerSystem m_SerializerSystem`  
- `private System.Collections.Generic.List<System.ValueTuple<Game.Serialization.WriteBuffer, Colossal.Serialization.Entities.BufferFormat>> m_Buffers`  
- `private Unity.Jobs.JobHandle m_WriteDependency`  
- `private System.Runtime.InteropServices.GCHandle m_WriterHandle`  

## Properties

- `public Unity.Jobs.JobHandle writeDependency { get }`  

## Constructors

- `public WriteSystem()`  

## Methods

- `public AddBuffer(Colossal.Serialization.Entities.BufferFormat format) : Game.Serialization.WriteBuffer`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private WriteBuffer(Game.Serialization.WriteBuffer buffer, Colossal.Serialization.Entities.BufferFormat format) : System.Void`  
- `private static WriteData<T>(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, T data) : System.Void`  
- `private static WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeArray<System.Byte> data) : System.Void`  
- `private static WriteData(Colossal.IO.AssetDatabase.StreamBinaryWriter writer, Unity.Collections.NativeSlice<System.Byte> data) : System.Void`  

## Nested types

- `Game.Serialization.WriteSystem+WriteRawBufferJob`  
- `Game.Serialization.WriteSystem+WriteCompressedBufferJob`  
- `Game.Serialization.WriteSystem+DisposeWriterJob`  
- `Game.Serialization.WriteSystem+BufferHeader`  

