# Game.Prefabs.PrefabData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Unity.Entities.IEnableableComponent`, `Colossal.Serialization.Entities.ISerializable`, `Colossal.Serialization.Entities.ISerializeAsEnabled`  

## Code

```csharp
public sealed struct PrefabData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Unity.Entities.IEnableableComponent, Colossal.Serialization.Entities.ISerializable, Colossal.Serialization.Entities.ISerializeAsEnabled
{
    public System.Int32 m_Index;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
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


