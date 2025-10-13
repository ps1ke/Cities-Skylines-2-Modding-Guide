# Game.Debug.TreeSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class TreeSpawnSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Unity.Entities.EntityQuery m_Prefabs;
    private Unity.Entities.EntityQuery m_TreeQuery;

    public TreeSpawnSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Unity.Entities.EntityQuery m_Prefabs`  

```csharp
private Unity.Entities.EntityQuery m_Prefabs;
```

- `private Unity.Entities.EntityQuery m_TreeQuery`  

```csharp
private Unity.Entities.EntityQuery m_TreeQuery;
```


## Constructors

- `public TreeSpawnSystem()`  

```csharp
public TreeSpawnSystem();
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


