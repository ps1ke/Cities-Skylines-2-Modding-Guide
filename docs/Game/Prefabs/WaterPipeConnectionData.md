# Game.Prefabs.WaterPipeConnectionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterPipeConnectionData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_FreshCapacity;
    public System.Int32 m_SewageCapacity;
    public System.Int32 m_StormCapacity;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_FreshCapacity`  

```csharp
public System.Int32 m_FreshCapacity;
```

- `public System.Int32 m_SewageCapacity`  

```csharp
public System.Int32 m_SewageCapacity;
```

- `public System.Int32 m_StormCapacity`  

```csharp
public System.Int32 m_StormCapacity;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


