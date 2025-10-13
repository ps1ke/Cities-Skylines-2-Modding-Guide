# Game.Prefabs.PlaceableNetData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PlaceableNetData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Colossal.Mathematics.Bounds1 m_ElevationRange;
    public Unity.Entities.Entity m_UndergroundPrefab;
    public Game.Net.PlacementFlags m_PlacementFlags;
    public Game.Prefabs.CompositionFlags m_SetUpgradeFlags;
    public Game.Prefabs.CompositionFlags m_UnsetUpgradeFlags;
    public System.UInt32 m_DefaultConstructionCost;
    public System.Single m_DefaultUpkeepCost;
    public System.Single m_SnapDistance;
    public System.Single m_MinWaterElevation;
    public System.Int32 m_XPReward;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Colossal.Mathematics.Bounds1 m_ElevationRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_ElevationRange;
```

- `public Unity.Entities.Entity m_UndergroundPrefab`  

```csharp
public Unity.Entities.Entity m_UndergroundPrefab;
```

- `public Game.Net.PlacementFlags m_PlacementFlags`  

```csharp
public Game.Net.PlacementFlags m_PlacementFlags;
```

- `public Game.Prefabs.CompositionFlags m_SetUpgradeFlags`  

```csharp
public Game.Prefabs.CompositionFlags m_SetUpgradeFlags;
```

- `public Game.Prefabs.CompositionFlags m_UnsetUpgradeFlags`  

```csharp
public Game.Prefabs.CompositionFlags m_UnsetUpgradeFlags;
```

- `public System.UInt32 m_DefaultConstructionCost`  

```csharp
public System.UInt32 m_DefaultConstructionCost;
```

- `public System.Single m_DefaultUpkeepCost`  

```csharp
public System.Single m_DefaultUpkeepCost;
```

- `public System.Single m_SnapDistance`  

```csharp
public System.Single m_SnapDistance;
```

- `public System.Single m_MinWaterElevation`  

```csharp
public System.Single m_MinWaterElevation;
```

- `public System.Int32 m_XPReward`  

```csharp
public System.Int32 m_XPReward;
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


