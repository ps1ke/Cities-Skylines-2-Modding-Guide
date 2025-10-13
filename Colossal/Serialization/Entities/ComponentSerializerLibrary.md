# Colossal.Serialization.Entities.ComponentSerializerLibrary

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class ComponentSerializerLibrary : System.IDisposable
{
    private Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32> m_SerializerMap;
    private System.Collections.Generic.List<Colossal.Serialization.Entities.ComponentSerializer> m_Serializers;
    private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable;
    private Unity.Entities.SystemBase m_System;
    private Unity.Entities.EntityTypeHandle m_EntityTypeHandle;
    private Unity.Collections.NativeArray<System.Int32> m_DataSizes;
    private System.Boolean <isDirty>k__BackingField;

    public System.Boolean isDirty { get; private set; }

    public ComponentSerializerLibrary();

    public System.Void AddObsoleteOverhead(System.Int32 overhead);
    public System.Void AddOverhead(System.Int32 index, System.Int32 overhead);
    public System.Void Dispose();
    public Unity.Entities.EntityTypeHandle GetEntityTypeHandle();
    public System.Int32 GetObsoleteSerializedSize(System.Int32& overhead);
    public Colossal.Serialization.Entities.ComponentSerializer GetObsoleteSerializer();
    public System.Int32 GetSerializedSize(System.Int32 index, System.Int32& overhead);
    public Colossal.Serialization.Entities.ComponentSerializer GetSerializer(System.Int32 index);
    public System.Int32 GetSerializerCount();
    public Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32> GetSerializerMap();
    public System.Collections.Generic.Dictionary<System.String, System.Type> GetTypeTable();
    public System.Void Initialize(Unity.Entities.SystemBase system, System.Collections.Generic.List`1[[Unity.Entities.ComponentType, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serializableComponents);
    public System.Void Reset();
    public System.Void SetDirty();
    public System.Boolean TryGetSerializerIndex(Unity.Entities.ComponentType type, System.Int32& index);
    public System.Void Update(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateTypeTable(System.Type type);
}
```


## Fields

- `private Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32> m_SerializerMap`  

```csharp
private Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32> m_SerializerMap;
```

- `private System.Collections.Generic.List<Colossal.Serialization.Entities.ComponentSerializer> m_Serializers`  

```csharp
private System.Collections.Generic.List<Colossal.Serialization.Entities.ComponentSerializer> m_Serializers;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable;
```

- `private Unity.Entities.SystemBase m_System`  

```csharp
private Unity.Entities.SystemBase m_System;
```

- `private Unity.Entities.EntityTypeHandle m_EntityTypeHandle`  

```csharp
private Unity.Entities.EntityTypeHandle m_EntityTypeHandle;
```

- `private Unity.Collections.NativeArray<System.Int32> m_DataSizes`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_DataSizes;
```

- `private System.Boolean <isDirty>k__BackingField`  

```csharp
private System.Boolean <isDirty>k__BackingField;
```


## Properties

- `public System.Boolean isDirty { get; private set }`  

```csharp
public System.Boolean isDirty { get; private set; }
```


## Constructors

- `public ComponentSerializerLibrary()`  

```csharp
public ComponentSerializerLibrary();
```


## Methods

- `public AddObsoleteOverhead(System.Int32 overhead) : System.Void`  

```csharp
public System.Void AddObsoleteOverhead(System.Int32 overhead);
```

- `public AddOverhead(System.Int32 index, System.Int32 overhead) : System.Void`  

```csharp
public System.Void AddOverhead(System.Int32 index, System.Int32 overhead);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetEntityTypeHandle() : Unity.Entities.EntityTypeHandle`  

```csharp
public Unity.Entities.EntityTypeHandle GetEntityTypeHandle();
```

- `public GetObsoleteSerializedSize(System.Int32& overhead) : System.Int32`  

```csharp
public System.Int32 GetObsoleteSerializedSize(System.Int32& overhead);
```

- `public GetObsoleteSerializer() : Colossal.Serialization.Entities.ComponentSerializer`  

```csharp
public Colossal.Serialization.Entities.ComponentSerializer GetObsoleteSerializer();
```

- `public GetSerializedSize(System.Int32 index, System.Int32& overhead) : System.Int32`  

```csharp
public System.Int32 GetSerializedSize(System.Int32 index, System.Int32& overhead);
```

- `public GetSerializer(System.Int32 index) : Colossal.Serialization.Entities.ComponentSerializer`  

```csharp
public Colossal.Serialization.Entities.ComponentSerializer GetSerializer(System.Int32 index);
```

- `public GetSerializerCount() : System.Int32`  

```csharp
public System.Int32 GetSerializerCount();
```

- `public GetSerializerMap() : Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32>`  

```csharp
public Unity.Collections.NativeParallelHashMap<Unity.Entities.ComponentType, System.Int32> GetSerializerMap();
```

- `public GetTypeTable() : System.Collections.Generic.Dictionary<System.String, System.Type>`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Type> GetTypeTable();
```

- `public Initialize(Unity.Entities.SystemBase system, System.Collections.Generic.List`1[[Unity.Entities.ComponentType, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serializableComponents) : System.Void`  

```csharp
public System.Void Initialize(Unity.Entities.SystemBase system, System.Collections.Generic.List`1[[Unity.Entities.ComponentType, Unity.Entities, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& serializableComponents);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public SetDirty() : System.Void`  

```csharp
public System.Void SetDirty();
```

- `public TryGetSerializerIndex(Unity.Entities.ComponentType type, System.Int32& index) : System.Boolean`  

```csharp
public System.Boolean TryGetSerializerIndex(Unity.Entities.ComponentType type, System.Int32& index);
```

- `public Update(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void Update(Colossal.Serialization.Entities.Context context);
```

- `private UpdateTypeTable(System.Type type) : System.Void`  

```csharp
private System.Void UpdateTypeTable(System.Type type);
```


