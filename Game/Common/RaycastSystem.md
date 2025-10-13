# Game.Common.RaycastSystem

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TerrainQuery;
    private Unity.Entities.EntityQuery m_LabelQuery;
    private Unity.Entities.EntityQuery m_IconQuery;
    private Unity.Entities.EntityQuery m_WaterSourceQuery;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Objects.SearchSystem m_ObjectsSearchSystem;
    private Game.Routes.SearchSystem m_RouteSearchSystem;
    private Game.Notifications.IconClusterSystem m_IconClusterSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private System.Collections.Generic.List<System.Object> m_InputContext;
    private System.Collections.Generic.List<System.Object> m_ResultContext;
    private Unity.Collections.NativeList<Game.Common.RaycastInput> m_Input;
    private Unity.Collections.NativeList<Game.Common.RaycastResult> m_Result;
    private Unity.Jobs.JobHandle m_Dependencies;
    private System.Boolean m_Updating;
    private Game.Common.RaycastSystem+TypeHandle __TypeHandle;

    public RaycastSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddInput(System.Object context, Game.Common.RaycastInput input);
    private System.Void CompleteRaycast();
    public Unity.Collections.NativeArray<Game.Common.RaycastResult> GetResult(System.Object context);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private Unity.Jobs.JobHandle PerformRaycast(Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> accumulator);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TerrainQuery`  

```csharp
private Unity.Entities.EntityQuery m_TerrainQuery;
```

- `private Unity.Entities.EntityQuery m_LabelQuery`  

```csharp
private Unity.Entities.EntityQuery m_LabelQuery;
```

- `private Unity.Entities.EntityQuery m_IconQuery`  

```csharp
private Unity.Entities.EntityQuery m_IconQuery;
```

- `private Unity.Entities.EntityQuery m_WaterSourceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaterSourceQuery;
```

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Objects.SearchSystem m_ObjectsSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectsSearchSystem;
```

- `private Game.Routes.SearchSystem m_RouteSearchSystem`  

```csharp
private Game.Routes.SearchSystem m_RouteSearchSystem;
```

- `private Game.Notifications.IconClusterSystem m_IconClusterSystem`  

```csharp
private Game.Notifications.IconClusterSystem m_IconClusterSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private System.Collections.Generic.List<System.Object> m_InputContext`  

```csharp
private System.Collections.Generic.List<System.Object> m_InputContext;
```

- `private System.Collections.Generic.List<System.Object> m_ResultContext`  

```csharp
private System.Collections.Generic.List<System.Object> m_ResultContext;
```

- `private Unity.Collections.NativeList<Game.Common.RaycastInput> m_Input`  

```csharp
private Unity.Collections.NativeList<Game.Common.RaycastInput> m_Input;
```

- `private Unity.Collections.NativeList<Game.Common.RaycastResult> m_Result`  

```csharp
private Unity.Collections.NativeList<Game.Common.RaycastResult> m_Result;
```

- `private Unity.Jobs.JobHandle m_Dependencies`  

```csharp
private Unity.Jobs.JobHandle m_Dependencies;
```

- `private System.Boolean m_Updating`  

```csharp
private System.Boolean m_Updating;
```

- `private Game.Common.RaycastSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Common.RaycastSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RaycastSystem()`  

```csharp
public RaycastSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddInput(System.Object context, Game.Common.RaycastInput input) : System.Void`  

```csharp
public System.Void AddInput(System.Object context, Game.Common.RaycastInput input);
```

- `private CompleteRaycast() : System.Void`  

```csharp
private System.Void CompleteRaycast();
```

- `public GetResult(System.Object context) : Unity.Collections.NativeArray<Game.Common.RaycastResult>`  

```csharp
public Unity.Collections.NativeArray<Game.Common.RaycastResult> GetResult(System.Object context);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PerformRaycast(Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> accumulator) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle PerformRaycast(Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> accumulator);
```


## Nested types

- `Game.Common.RaycastSystem+EntityResult`  
- `Game.Common.RaycastSystem+FindEntitiesFromTreeJob`  
- `Game.Common.RaycastSystem+DequeEntitiesJob`  
- `Game.Common.RaycastSystem+RaycastTerrainJob`  
- `Game.Common.RaycastSystem+RaycastWaterSourcesJob`  
- `Game.Common.RaycastSystem+RaycastResultJob`  
- `Game.Common.RaycastSystem+TypeHandle`  

