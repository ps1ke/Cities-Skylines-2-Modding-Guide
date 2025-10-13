# Game.Routes.WaypointConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaypointConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Routes.SearchSystem m_RouteSearchSystem;
    private Unity.Entities.EntityQuery m_WaypointQuery;
    private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
    private Game.Routes.WaypointConnectionSystem+TypeHandle __TypeHandle;

    public WaypointConnectionSystem();

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

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Routes.SearchSystem m_RouteSearchSystem`  

```csharp
private Game.Routes.SearchSystem m_RouteSearchSystem;
```

- `private Unity.Entities.EntityQuery m_WaypointQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaypointQuery;
```

- `private Unity.Entities.EntityArchetype m_PathTargetEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
```

- `private Game.Routes.WaypointConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.WaypointConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaypointConnectionSystem()`  

```csharp
public WaypointConnectionSystem();
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

- `Game.Routes.WaypointConnectionSystem+UpdateWaypointReferencesJob`  
- `Game.Routes.WaypointConnectionSystem+FindUpdatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+DequeUpdatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+RemoveDuplicatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+FindWaypointConnectionsJob`  
- `Game.Routes.WaypointConnectionSystem+PathTargetInfo`  
- `Game.Routes.WaypointConnectionSystem+ClearPathTargetsJob`  
- `Game.Routes.WaypointConnectionSystem+TypeHandle`  

