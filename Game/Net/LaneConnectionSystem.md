# Game.Net.LaneConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.Net.LaneConnectionSystem+TypeHandle __TypeHandle;

    public LaneConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.Net.LaneConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneConnectionSystem()`  

```csharp
public LaneConnectionSystem();
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

- `Game.Net.LaneConnectionSystem+FindUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+CheckUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+ListUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+FindLaneConnectionJob`  
- `Game.Net.LaneConnectionSystem+TypeHandle`  

