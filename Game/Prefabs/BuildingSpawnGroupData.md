# Game.Prefabs.BuildingSpawnGroupData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.ISharedComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct BuildingSpawnGroupData : Unity.Entities.ISharedComponentData, Unity.Entities.IQueryTypeParameter
{
    public Game.Zones.ZoneType m_ZoneType;

    public BuildingSpawnGroupData(Game.Zones.ZoneType type);

}
```


## Fields

- `public Game.Zones.ZoneType m_ZoneType`  

```csharp
public Game.Zones.ZoneType m_ZoneType;
```


## Constructors

- `public BuildingSpawnGroupData(Game.Zones.ZoneType type)`  

```csharp
public BuildingSpawnGroupData(Game.Zones.ZoneType type);
```


