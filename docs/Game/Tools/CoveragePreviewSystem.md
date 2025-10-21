# Game.Tools.CoveragePreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CoveragePreviewSystem : Game.GameSystemBase
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
    private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Game.Net.CoverageService m_LastService;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private System.Collections.Generic.HashSet<Unity.Entities.Entity> m_PendingCoverages;
    private Game.Tools.CoveragePreviewSystem+TypeHandle __TypeHandle;

    public CoveragePreviewSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetInfoviewCoverageData(Game.Prefabs.InfoviewCoverageData& coverageData);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Game.Net.CoverageService m_LastService`  

```csharp
private Game.Net.CoverageService m_LastService;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private System.Collections.Generic.HashSet<Unity.Entities.Entity> m_PendingCoverages`  

```csharp
private System.Collections.Generic.HashSet<Unity.Entities.Entity> m_PendingCoverages;
```

- `private Game.Tools.CoveragePreviewSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.CoveragePreviewSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CoveragePreviewSystem()`  

```csharp
public CoveragePreviewSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private GetInfoviewCoverageData(Game.Prefabs.InfoviewCoverageData& coverageData) : System.Boolean`  

```csharp
private System.Boolean GetInfoviewCoverageData(Game.Prefabs.InfoviewCoverageData& coverageData);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Tools.CoveragePreviewSystem+InitializeCoverageJob`  
- `Game.Tools.CoveragePreviewSystem+CopyServiceCoverageJob`  
- `Game.Tools.CoveragePreviewSystem+SetupCoverageSearchJob`  
- `Game.Tools.CoveragePreviewSystem+TypeHandle`  

