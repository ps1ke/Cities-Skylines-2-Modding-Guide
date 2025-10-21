# Game.Prefabs.ServiceUpgradeData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ServiceUpgradeData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.UInt32 m_UpgradeCost;
    public System.Int32 m_XPReward;
    public System.Int32 m_MaxPlacementOffset;
    public System.Single m_MaxPlacementDistance;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.UInt32 m_UpgradeCost`  

```csharp
public System.UInt32 m_UpgradeCost;
```

- `public System.Int32 m_XPReward`  

```csharp
public System.Int32 m_XPReward;
```

- `public System.Int32 m_MaxPlacementOffset`  

```csharp
public System.Int32 m_MaxPlacementOffset;
```

- `public System.Single m_MaxPlacementDistance`  

```csharp
public System.Single m_MaxPlacementDistance;
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


