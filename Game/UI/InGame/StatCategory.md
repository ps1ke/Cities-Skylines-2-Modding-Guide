# Game.UI.InGame.StatisticsUISystem+StatCategory

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.UI.InGame.StatisticsUISystem+StatCategory>`  

## Code

```csharp
public sealed struct StatCategory : System.IComparable<Game.UI.InGame.StatisticsUISystem+StatCategory>
{
    public Unity.Entities.Entity m_Entity;
    public Game.Prefabs.PrefabData m_PrefabData;
    public Game.Prefabs.UIObjectData m_ObjectData;

    public StatCategory(Unity.Entities.Entity entity, Game.Prefabs.UIObjectData objectData, Game.Prefabs.PrefabData prefabData);

    public System.Int32 CompareTo(Game.UI.InGame.StatisticsUISystem+StatCategory other);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Game.Prefabs.PrefabData m_PrefabData`  

```csharp
public Game.Prefabs.PrefabData m_PrefabData;
```

- `public Game.Prefabs.UIObjectData m_ObjectData`  

```csharp
public Game.Prefabs.UIObjectData m_ObjectData;
```


## Constructors

- `public StatCategory(Unity.Entities.Entity entity, Game.Prefabs.UIObjectData objectData, Game.Prefabs.PrefabData prefabData)`  

```csharp
public StatCategory(Unity.Entities.Entity entity, Game.Prefabs.UIObjectData objectData, Game.Prefabs.PrefabData prefabData);
```


## Methods

- `public CompareTo(Game.UI.InGame.StatisticsUISystem+StatCategory other) : System.Int32`  

```csharp
public System.Int32 CompareTo(Game.UI.InGame.StatisticsUISystem+StatCategory other);
```


