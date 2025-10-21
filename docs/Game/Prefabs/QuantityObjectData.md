# Game.Prefabs.QuantityObjectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct QuantityObjectData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Economy.Resource m_Resources;
    public Game.Areas.MapFeature m_MapFeature;
    public System.UInt32 m_StepMask;

}
```


## Fields

- `public Game.Economy.Resource m_Resources`  

```csharp
public Game.Economy.Resource m_Resources;
```

- `public Game.Areas.MapFeature m_MapFeature`  

```csharp
public Game.Areas.MapFeature m_MapFeature;
```

- `public System.UInt32 m_StepMask`  

```csharp
public System.UInt32 m_StepMask;
```


