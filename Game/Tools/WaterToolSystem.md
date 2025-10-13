# Game.Tools.WaterToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaterToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.WaterToolSystem+Attribute <attribute>k__BackingField;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Game.Tools.WaterToolSystem+State m_State;
    private Game.Tools.WaterToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Tools.WaterToolSystem+Attribute attribute { get; private set; }

    public WaterToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    private Game.Tools.WaterToolSystem+Attribute GetAttribute(Game.Tools.ControlPoint controlPoint);
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.WaterToolSystem+Attribute <attribute>k__BackingField`  

```csharp
private Game.Tools.WaterToolSystem+Attribute <attribute>k__BackingField;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Game.Tools.WaterToolSystem+State m_State`  

```csharp
private Game.Tools.WaterToolSystem+State m_State;
```

- `private Game.Tools.WaterToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.WaterToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public Game.Tools.WaterToolSystem+Attribute attribute { get; private set }`  

```csharp
public Game.Tools.WaterToolSystem+Attribute attribute { get; private set; }
```


## Constructors

- `public WaterToolSystem()`  

```csharp
public WaterToolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
```

- `private GetAttribute(Game.Tools.ControlPoint controlPoint) : Game.Tools.WaterToolSystem+Attribute`  

```csharp
private Game.Tools.WaterToolSystem+Attribute GetAttribute(Game.Tools.ControlPoint controlPoint);
```

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
```

- `public virtual InitializeRaycast() : System.Void`  

```csharp
public virtual System.Void InitializeRaycast();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual TrySetPrefab(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
```

- `private Update(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
```

- `private virtual UpdateActions() : System.Void`  

```csharp
private virtual System.Void UpdateActions();
```

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Tools.WaterToolSystem+Attribute`  
- `Game.Tools.WaterToolSystem+State`  
- `Game.Tools.WaterToolSystem+CreateDefinitionsJob`  
- `Game.Tools.WaterToolSystem+TypeHandle`  

