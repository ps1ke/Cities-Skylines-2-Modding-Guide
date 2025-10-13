# Game.Prefabs.PlaceableObjectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PlaceableObjectData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_PlacementOffset;
    public System.UInt32 m_ConstructionCost;
    public System.Int32 m_XPReward;
    public System.Byte m_DefaultProbability;
    public Game.Objects.RotationSymmetry m_RotationSymmetry;
    public Game.Net.SubReplacementType m_SubReplacementType;
    public Game.Objects.PlacementFlags m_Flags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_PlacementOffset`  

```csharp
public Unity.Mathematics.float3 m_PlacementOffset;
```

- `public System.UInt32 m_ConstructionCost`  

```csharp
public System.UInt32 m_ConstructionCost;
```

- `public System.Int32 m_XPReward`  

```csharp
public System.Int32 m_XPReward;
```

- `public System.Byte m_DefaultProbability`  

```csharp
public System.Byte m_DefaultProbability;
```

- `public Game.Objects.RotationSymmetry m_RotationSymmetry`  

```csharp
public Game.Objects.RotationSymmetry m_RotationSymmetry;
```

- `public Game.Net.SubReplacementType m_SubReplacementType`  

```csharp
public Game.Net.SubReplacementType m_SubReplacementType;
```

- `public Game.Objects.PlacementFlags m_Flags`  

```csharp
public Game.Objects.PlacementFlags m_Flags;
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


