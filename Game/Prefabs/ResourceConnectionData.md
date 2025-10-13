# Game.Prefabs.ResourceConnectionData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ResourceConnectionData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Economy.Resource m_Resource;
    public Unity.Entities.Entity m_ConnectionWarningNotification;

}
```


## Fields

- `public Game.Economy.Resource m_Resource`  

```csharp
public Game.Economy.Resource m_Resource;
```

- `public Unity.Entities.Entity m_ConnectionWarningNotification`  

```csharp
public Unity.Entities.Entity m_ConnectionWarningNotification;
```


