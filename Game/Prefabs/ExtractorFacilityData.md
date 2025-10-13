# Game.Prefabs.ExtractorFacilityData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ExtractorFacilityData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Colossal.Mathematics.Bounds1 m_RotationRange;
    public Colossal.Mathematics.Bounds1 m_HeightOffset;
    public Game.Prefabs.ExtractorRequirementFlags m_Requirements;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_RotationRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_RotationRange;
```

- `public Colossal.Mathematics.Bounds1 m_HeightOffset`  

```csharp
public Colossal.Mathematics.Bounds1 m_HeightOffset;
```

- `public Game.Prefabs.ExtractorRequirementFlags m_Requirements`  

```csharp
public Game.Prefabs.ExtractorRequirementFlags m_Requirements;
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


