# Game.Objects.SpawnLocationConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SpawnLocationConnectionSystem : Game.GameSystemBase
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.Objects.SpawnLocationConnectionSystem+TypeHandle __TypeHandle;

    public SpawnLocationConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.Objects.SpawnLocationConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SpawnLocationConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SpawnLocationConnectionSystem()`  

```csharp
public SpawnLocationConnectionSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Objects.SpawnLocationConnectionSystem+FindUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+CheckUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+ListUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+FindSpawnLocationConnectionJob`  
- `Game.Objects.SpawnLocationConnectionSystem+TypeHandle`  

