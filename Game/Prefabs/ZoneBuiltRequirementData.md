# Game.Prefabs.ZoneBuiltRequirementData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`  

## Code

```csharp
public sealed struct ZoneBuiltRequirementData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter
{
    public Unity.Entities.Entity m_RequiredTheme;
    public Unity.Entities.Entity m_RequiredZone;
    public System.Int32 m_MinimumSquares;
    public System.Int32 m_MinimumCount;
    public Game.Zones.AreaType m_RequiredType;
    public System.Byte m_MinimumLevel;

}
```


## Fields

- `public Unity.Entities.Entity m_RequiredTheme`  

```csharp
public Unity.Entities.Entity m_RequiredTheme;
```

- `public Unity.Entities.Entity m_RequiredZone`  

```csharp
public Unity.Entities.Entity m_RequiredZone;
```

- `public System.Int32 m_MinimumSquares`  

```csharp
public System.Int32 m_MinimumSquares;
```

- `public System.Int32 m_MinimumCount`  

```csharp
public System.Int32 m_MinimumCount;
```

- `public Game.Zones.AreaType m_RequiredType`  

```csharp
public Game.Zones.AreaType m_RequiredType;
```

- `public System.Byte m_MinimumLevel`  

```csharp
public System.Byte m_MinimumLevel;
```


