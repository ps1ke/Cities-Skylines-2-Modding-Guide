# Game.Prefabs.PollutionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.PollutionData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PollutionData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.PollutionData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_GroundPollution;
    public System.Single m_AirPollution;
    public System.Single m_NoisePollution;
    public System.Boolean m_ScaleWithRenters;

    public System.Void AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public System.Void Combine(Game.Prefabs.PollutionData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Single GetValue(Game.Prefabs.BuildingStatusType statusType);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_GroundPollution`  

```csharp
public System.Single m_GroundPollution;
```

- `public System.Single m_AirPollution`  

```csharp
public System.Single m_AirPollution;
```

- `public System.Single m_NoisePollution`  

```csharp
public System.Single m_NoisePollution;
```

- `public System.Boolean m_ScaleWithRenters`  

```csharp
public System.Boolean m_ScaleWithRenters;
```


## Methods

- `public AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public System.Void AddArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
```

- `public Combine(Game.Prefabs.PollutionData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.PollutionData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetValue(Game.Prefabs.BuildingStatusType statusType) : System.Single`  

```csharp
public System.Single GetValue(Game.Prefabs.BuildingStatusType statusType);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


