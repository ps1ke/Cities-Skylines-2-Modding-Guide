# Colossal.Serialization.Entities.SystemSerializerLibrary

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class SystemSerializerLibrary : System.IDisposable
{
    private System.Collections.Generic.Dictionary<System.Type, System.Int32> m_SerializerMap;
    private System.Collections.Generic.List<Colossal.Serialization.Entities.SystemSerializer> m_Serializers;
    private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable;
    private Unity.Collections.NativeArray<System.Int32> m_DataSizes;
    private System.Boolean <isDirty>k__BackingField;

    public System.Boolean isDirty { get; private set; }

    public SystemSerializerLibrary();

    public System.Void AddObsoleteOverhead(System.Int32 overhead);
    public System.Void AddOverhead(System.Int32 index, System.Int32 overhead);
    public System.Void Dispose();
    public System.Int32 GetObsoleteSerializedSize(System.Int32& overhead);
    public Colossal.Serialization.Entities.SystemSerializer GetObsoleteSerializer();
    public System.Int32 GetSerializedSize(System.Int32 index, System.Int32& overhead);
    public Colossal.Serialization.Entities.SystemSerializer GetSerializer(System.Int32 index);
    public System.Int32 GetSerializerCount();
    public System.Collections.Generic.Dictionary<System.String, System.Type> GetTypeTable();
    public System.Void Initialize(Unity.Entities.World world);
    public System.Void Reset();
    public System.Void SetDirty();
    public System.Boolean TryGetSerializerIndex(System.Type type, System.Int32& index);
    private System.Void UpdateTypeTable(System.Type type);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.Type, System.Int32> m_SerializerMap`  

```csharp
private System.Collections.Generic.Dictionary<System.Type, System.Int32> m_SerializerMap;
```

- `private System.Collections.Generic.List<Colossal.Serialization.Entities.SystemSerializer> m_Serializers`  

```csharp
private System.Collections.Generic.List<Colossal.Serialization.Entities.SystemSerializer> m_Serializers;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Type> m_TypeTable;
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

- `public SystemSerializerLibrary()`  

```csharp
public SystemSerializerLibrary();
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

- `public GetObsoleteSerializedSize(System.Int32& overhead) : System.Int32`  

```csharp
public System.Int32 GetObsoleteSerializedSize(System.Int32& overhead);
```

- `public GetObsoleteSerializer() : Colossal.Serialization.Entities.SystemSerializer`  

```csharp
public Colossal.Serialization.Entities.SystemSerializer GetObsoleteSerializer();
```

- `public GetSerializedSize(System.Int32 index, System.Int32& overhead) : System.Int32`  

```csharp
public System.Int32 GetSerializedSize(System.Int32 index, System.Int32& overhead);
```

- `public GetSerializer(System.Int32 index) : Colossal.Serialization.Entities.SystemSerializer`  

```csharp
public Colossal.Serialization.Entities.SystemSerializer GetSerializer(System.Int32 index);
```

- `public GetSerializerCount() : System.Int32`  

```csharp
public System.Int32 GetSerializerCount();
```

- `public GetTypeTable() : System.Collections.Generic.Dictionary<System.String, System.Type>`  

```csharp
public System.Collections.Generic.Dictionary<System.String, System.Type> GetTypeTable();
```

- `public Initialize(Unity.Entities.World world) : System.Void`  

```csharp
public System.Void Initialize(Unity.Entities.World world);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public SetDirty() : System.Void`  

```csharp
public System.Void SetDirty();
```

- `public TryGetSerializerIndex(System.Type type, System.Int32& index) : System.Boolean`  

```csharp
public System.Boolean TryGetSerializerIndex(System.Type type, System.Int32& index);
```

- `private UpdateTypeTable(System.Type type) : System.Void`  

```csharp
private System.Void UpdateTypeTable(System.Type type);
```


