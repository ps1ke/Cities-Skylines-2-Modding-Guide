# Game.Prefabs.RoadComposition

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct RoadComposition : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_ZoneBlockPrefab;
    public System.Single m_SpeedLimit;
    public System.Single m_Priority;
    public Game.Prefabs.RoadFlags m_Flags;

}
```


## Fields

- `public Unity.Entities.Entity m_ZoneBlockPrefab`  

```csharp
public Unity.Entities.Entity m_ZoneBlockPrefab;
```

- `public System.Single m_SpeedLimit`  

```csharp
public System.Single m_SpeedLimit;
```

- `public System.Single m_Priority`  

```csharp
public System.Single m_Priority;
```

- `public Game.Prefabs.RoadFlags m_Flags`  

```csharp
public Game.Prefabs.RoadFlags m_Flags;
```


