# Colossal.Serialization.Entities.SystemSerializerLibrary

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private System.Collections.Generic.Dictionary<System.Type, System.Int32> m_SerializerMap`  
- `private System.Collections.Generic.List<Colossal.Serialization.Entities.SystemSerializer> m_Serializers`  
- `private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable`  
- `private Unity.Collections.NativeArray<System.Int32> m_DataSizes`  
- `private System.Boolean <isDirty>k__BackingField`  

## Properties

- `public System.Boolean isDirty { get; private set }`  

## Constructors

- `public SystemSerializerLibrary()`  

## Methods

- `public AddObsoleteOverhead(System.Int32 overhead) : System.Void`  
- `public AddOverhead(System.Int32 index, System.Int32 overhead) : System.Void`  
- `public Dispose() : System.Void`  
- `public GetObsoleteSerializedSize(System.Int32& overhead) : System.Int32`  
- `public GetObsoleteSerializer() : Colossal.Serialization.Entities.SystemSerializer`  
- `public GetSerializedSize(System.Int32 index, System.Int32& overhead) : System.Int32`  
- `public GetSerializer(System.Int32 index) : Colossal.Serialization.Entities.SystemSerializer`  
- `public GetSerializerCount() : System.Int32`  
- `public GetTypeTable() : System.Collections.Generic.Dictionary<System.String, System.Type>`  
- `public Initialize(Unity.Entities.World world) : System.Void`  
- `public Reset() : System.Void`  
- `public SetDirty() : System.Void`  
- `public TryGetSerializerIndex(System.Type type, System.Int32& index) : System.Boolean`  
- `private UpdateTypeTable(System.Type type) : System.Void`  

