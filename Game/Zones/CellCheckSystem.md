# Game.Zones.CellCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CellCheckSystem : Game.GameSystemBase
{
    private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
    private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Prefabs.ZoneSystem m_ZonePrefabSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedBlocksQuery;
    private Game.Zones.CellCheckSystem+TypeHandle __TypeHandle;

    public CellCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle CollectUpdatedBlocks(Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> updateBlocksList);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem`  

```csharp
private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
```

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  

```csharp
private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
```

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Prefabs.ZoneSystem m_ZonePrefabSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZonePrefabSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedBlocksQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedBlocksQuery;
```

- `private Game.Zones.CellCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Zones.CellCheckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CellCheckSystem()`  

```csharp
public CellCheckSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private CollectUpdatedBlocks(Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> updateBlocksList) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle CollectUpdatedBlocks(Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> updateBlocksList);
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

- `Game.Zones.CellCheckSystem+TypeHandle`  

