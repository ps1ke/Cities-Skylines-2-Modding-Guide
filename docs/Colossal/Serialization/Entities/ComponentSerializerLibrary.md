# Colossal.Serialization.Entities.ComponentSerializerLibrary

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32> m_SerializerMap`  
- `private System.Collections.Generic.List<Colossal.Serialization.Entities.ComponentSerializer> m_Serializers`  
- `private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable`  
- `private Unity.Entities.SystemBase m_System`  
- `private Unity.Entities.EntityTypeHandle m_EntityTypeHandle`  
- `private Unity.Collections.NativeArray<System.Int32> m_DataSizes`  
- `private System.Boolean <isDirty>k__BackingField`  

## Properties

- `public System.Boolean isDirty { get; private set }`  

## Constructors

- `public ComponentSerializerLibrary()`  

## Methods

- `public AddObsoleteOverhead(System.Int32 overhead) : System.Void`  
- `public AddOverhead(System.Int32 index, System.Int32 overhead) : System.Void`  
- `public Dispose() : System.Void`  
- `public GetEntityTypeHandle() : Unity.Entities.EntityTypeHandle`  
- `public GetObsoleteSerializedSize(System.Int32& overhead) : System.Int32`  
- `public GetObsoleteSerializer() : Colossal.Serialization.Entities.ComponentSerializer`  
- `public GetSerializedSize(System.Int32 index, System.Int32& overhead) : System.Int32`  
- `public GetSerializer(System.Int32 index) : Colossal.Serialization.Entities.ComponentSerializer`  
- `public GetSerializerCount() : System.Int32`  
- `public GetSerializerMap() : Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32>`  
- `public GetTypeTable() : System.Collections.Generic.Dictionary<System.String, System.Type>`  
- `public Initialize(Unity.Entities.SystemBase system, System.Collections.Generic.List`1[[Unity.Entities.ComponentType, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serializableComponents) : System.Void`  
- `public Reset() : System.Void`  
- `public SetDirty() : System.Void`  
- `public TryGetSerializerIndex(Unity.Entities.ComponentType type, System.Int32& index) : System.Boolean`  
- `public Update(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private UpdateTypeTable(System.Type type) : System.Void`  

