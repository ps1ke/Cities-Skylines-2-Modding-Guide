# Game.UI.Editor.MapRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapRequirementSystem : Game.GameSystemBase
{
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_TileQuery;
    private Unity.Entities.EntityQuery m_OutsideRoadNodeQuery;
    private Unity.Entities.EntityQuery m_OutsideTrainNodeQuery;
    private Unity.Entities.EntityQuery m_OutsideAirNodeQuery;
    private Unity.Entities.EntityQuery m_OutsideElectricityConnectionQuery;
    private Unity.Jobs.JobHandle m_ResultDependency;
    private Colossal.Collections.NativeValue<System.Boolean> m_WaterResult;
    private Unity.Collections.NativeArray<System.Boolean> m_StartingAreaResources;
    private Unity.Collections.NativeArray<System.Boolean> m_MapResources;
    private System.Boolean <hasStartingArea>k__BackingField;
    private System.Boolean <roadConnection>k__BackingField;
    private System.Boolean <trainConnection>k__BackingField;
    private System.Boolean <airConnection>k__BackingField;
    private System.Boolean <electricityConnection>k__BackingField;
    private Game.UI.Editor.MapRequirementSystem+TypeHandle __TypeHandle;

    public System.Boolean hasStartingArea { get; private set; }
    public System.Boolean roadConnection { get; private set; }
    public System.Boolean trainConnection { get; private set; }
    public System.Boolean airConnection { get; private set; }
    public System.Boolean electricityConnection { get; private set; }

    public MapRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Boolean MapHasResource(Game.Areas.MapFeature feature);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Boolean StartingAreaHasResource(Game.Areas.MapFeature feature);
}
```


## Fields

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_TileQuery`  

```csharp
private Unity.Entities.EntityQuery m_TileQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideRoadNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideRoadNodeQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideTrainNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideTrainNodeQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideAirNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideAirNodeQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideElectricityConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideElectricityConnectionQuery;
```

- `private Unity.Jobs.JobHandle m_ResultDependency`  

```csharp
private Unity.Jobs.JobHandle m_ResultDependency;
```

- `private Colossal.Collections.NativeValue<System.Boolean> m_WaterResult`  

```csharp
private Colossal.Collections.NativeValue<System.Boolean> m_WaterResult;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_StartingAreaResources`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_StartingAreaResources;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_MapResources`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_MapResources;
```

- `private System.Boolean <hasStartingArea>k__BackingField`  

```csharp
private System.Boolean <hasStartingArea>k__BackingField;
```

- `private System.Boolean <roadConnection>k__BackingField`  

```csharp
private System.Boolean <roadConnection>k__BackingField;
```

- `private System.Boolean <trainConnection>k__BackingField`  

```csharp
private System.Boolean <trainConnection>k__BackingField;
```

- `private System.Boolean <airConnection>k__BackingField`  

```csharp
private System.Boolean <airConnection>k__BackingField;
```

- `private System.Boolean <electricityConnection>k__BackingField`  

```csharp
private System.Boolean <electricityConnection>k__BackingField;
```

- `private Game.UI.Editor.MapRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.MapRequirementSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean hasStartingArea { get; private set }`  

```csharp
public System.Boolean hasStartingArea { get; private set; }
```

- `public System.Boolean roadConnection { get; private set }`  

```csharp
public System.Boolean roadConnection { get; private set; }
```

- `public System.Boolean trainConnection { get; private set }`  

```csharp
public System.Boolean trainConnection { get; private set; }
```

- `public System.Boolean airConnection { get; private set }`  

```csharp
public System.Boolean airConnection { get; private set; }
```

- `public System.Boolean electricityConnection { get; private set }`  

```csharp
public System.Boolean electricityConnection { get; private set; }
```


## Constructors

- `public MapRequirementSystem()`  

```csharp
public MapRequirementSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public MapHasResource(Game.Areas.MapFeature feature) : System.Boolean`  

```csharp
public System.Boolean MapHasResource(Game.Areas.MapFeature feature);
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

- `public StartingAreaHasResource(Game.Areas.MapFeature feature) : System.Boolean`  

```csharp
public System.Boolean StartingAreaHasResource(Game.Areas.MapFeature feature);
```


## Nested types

- `Game.UI.Editor.MapRequirementSystem+CollectResourcesJob`  
- `Game.UI.Editor.MapRequirementSystem+CollectStartingResourcesJob`  
- `Game.UI.Editor.MapRequirementSystem+CheckWaterJob`  
- `Game.UI.Editor.MapRequirementSystem+TypeHandle`  

