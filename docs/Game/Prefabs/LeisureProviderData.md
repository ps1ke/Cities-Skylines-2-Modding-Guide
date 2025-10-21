# Game.Prefabs.LeisureProviderData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct LeisureProviderData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Efficiency;
    public Game.Economy.Resource m_Resources;
    public Game.Agents.LeisureType m_LeisureType;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Efficiency`  

```csharp
public System.Int32 m_Efficiency;
```

- `public Game.Economy.Resource m_Resources`  

```csharp
public Game.Economy.Resource m_Resources;
```

- `public Game.Agents.LeisureType m_LeisureType`  

```csharp
public Game.Agents.LeisureType m_LeisureType;
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


