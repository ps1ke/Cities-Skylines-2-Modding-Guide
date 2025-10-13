# Colossal.Serialization.Entities.SharedComponentDataSerializer`1+EntitySharedComponentData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct EntitySharedComponentData<TSharedComponentData>
{
    public System.Int32 m_FirstEntityIndex;
    public System.Int32 m_EntityCount;
    public TSharedComponentData m_Data;

    public EntitySharedComponentData(System.Int32 firstEntityIndex, System.Int32 entityCount, TSharedComponentData data);

}
```


## Fields

- `public System.Int32 m_FirstEntityIndex`  

```csharp
public System.Int32 m_FirstEntityIndex;
```

- `public System.Int32 m_EntityCount`  

```csharp
public System.Int32 m_EntityCount;
```

- `public TSharedComponentData m_Data`  

```csharp
public TSharedComponentData m_Data;
```


## Constructors

- `public EntitySharedComponentData(System.Int32 firstEntityIndex, System.Int32 entityCount, TSharedComponentData data)`  

```csharp
public EntitySharedComponentData(System.Int32 firstEntityIndex, System.Int32 entityCount, TSharedComponentData data);
```


