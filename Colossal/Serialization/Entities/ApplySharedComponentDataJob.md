# Colossal.Serialization.Entities.SharedComponentDataSerializer`1+ApplySharedComponentDataJob

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public sealed struct ApplySharedComponentDataJob<TSharedComponentData> : Unity.Jobs.IJob
{
    public Unity.Collections.NativeList<Colossal.Serialization.Entities.SharedComponentDataSerializer<TSharedComponentData>> m_DeserializationData;
    public Unity.Collections.NativeList<Unity.Entities.Entity> m_DeserializedEntities;
    public Unity.Entities.ExclusiveEntityTransaction m_Transaction;

    public System.Void Execute();
}
```


## Fields

- `public Unity.Collections.NativeList<Colossal.Serialization.Entities.SharedComponentDataSerializer<TSharedComponentData>> m_DeserializationData`  

```csharp
public Unity.Collections.NativeList<Colossal.Serialization.Entities.SharedComponentDataSerializer<TSharedComponentData>> m_DeserializationData;
```

- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_DeserializedEntities`  

```csharp
public Unity.Collections.NativeList<Unity.Entities.Entity> m_DeserializedEntities;
```

- `public Unity.Entities.ExclusiveEntityTransaction m_Transaction`  

```csharp
public Unity.Entities.ExclusiveEntityTransaction m_Transaction;
```


## Methods

- `public Execute() : System.Void`  

```csharp
public System.Void Execute();
```


