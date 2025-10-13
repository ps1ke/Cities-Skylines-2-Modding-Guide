# Game.Prefabs.UtilityLaneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct UtilityLaneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_LocalConnectionPrefab;
    public Unity.Entities.Entity m_LocalConnectionPrefab2;
    public Unity.Entities.Entity m_NodeObjectPrefab;
    public System.Single m_VisualCapacity;
    public System.Single m_Hanging;
    public Game.Net.UtilityTypes m_UtilityTypes;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_LocalConnectionPrefab`  

```csharp
public Unity.Entities.Entity m_LocalConnectionPrefab;
```

- `public Unity.Entities.Entity m_LocalConnectionPrefab2`  

```csharp
public Unity.Entities.Entity m_LocalConnectionPrefab2;
```

- `public Unity.Entities.Entity m_NodeObjectPrefab`  

```csharp
public Unity.Entities.Entity m_NodeObjectPrefab;
```

- `public System.Single m_VisualCapacity`  

```csharp
public System.Single m_VisualCapacity;
```

- `public System.Single m_Hanging`  

```csharp
public System.Single m_Hanging;
```

- `public Game.Net.UtilityTypes m_UtilityTypes`  

```csharp
public Game.Net.UtilityTypes m_UtilityTypes;
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


