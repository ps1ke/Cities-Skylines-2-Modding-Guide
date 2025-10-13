# Game.Tools.SelectionToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SelectionToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Tools.SelectionType <selectionType>k__BackingField;
    private Unity.Entities.Entity <selectionOwner>k__BackingField;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_DefinitionGroup;
    private Unity.Entities.EntityQuery m_TempGroup;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.Entity m_SelectionEntity;
    private Unity.Entities.Entity m_LastOwner;
    private Game.Tools.SelectionType m_LastType;
    private Unity.Entities.EntityArchetype m_SelectionArchetype;
    private Game.Tools.SelectionToolSystem+State m_State;
    private Game.Tools.ControlPoint m_StartPoint;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Input.IProxyAction m_SelectArea;
    private Game.Input.IProxyAction m_DeselectArea;
    private Game.Input.IProxyAction m_DiscardSelect;
    private Game.Input.IProxyAction m_DiscardDeselect;
    private System.Boolean m_ApplyBlocked;
    private Game.Tools.SelectionToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public Game.Tools.SelectionType selectionType { get; set; }
    public Unity.Entities.Entity selectionOwner { get; set; }
    public Game.Tools.SelectionToolSystem+State state { get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public SelectionToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CopySelection(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CopyServiceDistricts(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle CopyStartTiles(Unity.Jobs.JobHandle inputDeps);
    private Game.Areas.AreaType GetAreaType(Game.Tools.SelectionType selectionType);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
    protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
    public System.Boolean GetSelectionQuad(Colossal.Mathematics.Quad3& quad);
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle ToggleTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean select);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateSelection(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateServiceDistricts(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle UpdateStartTiles(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Tools.SelectionType <selectionType>k__BackingField`  

```csharp
private Game.Tools.SelectionType <selectionType>k__BackingField;
```

- `private Unity.Entities.Entity <selectionOwner>k__BackingField`  

```csharp
private Unity.Entities.Entity <selectionOwner>k__BackingField;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTilePurchaseSystem;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionGroup`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionGroup;
```

- `private Unity.Entities.EntityQuery m_TempGroup`  

```csharp
private Unity.Entities.EntityQuery m_TempGroup;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.Entity m_SelectionEntity`  

```csharp
private Unity.Entities.Entity m_SelectionEntity;
```

- `private Unity.Entities.Entity m_LastOwner`  

```csharp
private Unity.Entities.Entity m_LastOwner;
```

- `private Game.Tools.SelectionType m_LastType`  

```csharp
private Game.Tools.SelectionType m_LastType;
```

- `private Unity.Entities.EntityArchetype m_SelectionArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_SelectionArchetype;
```

- `private Game.Tools.SelectionToolSystem+State m_State`  

```csharp
private Game.Tools.SelectionToolSystem+State m_State;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Input.IProxyAction m_SelectArea`  

```csharp
private Game.Input.IProxyAction m_SelectArea;
```

- `private Game.Input.IProxyAction m_DeselectArea`  

```csharp
private Game.Input.IProxyAction m_DeselectArea;
```

- `private Game.Input.IProxyAction m_DiscardSelect`  

```csharp
private Game.Input.IProxyAction m_DiscardSelect;
```

- `private Game.Input.IProxyAction m_DiscardDeselect`  

```csharp
private Game.Input.IProxyAction m_DiscardDeselect;
```

- `private System.Boolean m_ApplyBlocked`  

```csharp
private System.Boolean m_ApplyBlocked;
```

- `private Game.Tools.SelectionToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.SelectionToolSystem+TypeHandle __TypeHandle;
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

- `public Game.Tools.SelectionType selectionType { get; set }`  

```csharp
public Game.Tools.SelectionType selectionType { get; set; }
```

- `public Unity.Entities.Entity selectionOwner { get; set }`  

```csharp
public Unity.Entities.Entity selectionOwner { get; set; }
```

- `public Game.Tools.SelectionToolSystem+State state { get }`  

```csharp
public Game.Tools.SelectionToolSystem+State state { get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public SelectionToolSystem()`  

```csharp
public SelectionToolSystem();
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

- `private CopySelection(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle CopySelection(Unity.Jobs.JobHandle inputDeps);
```

- `private CopyServiceDistricts(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle CopyServiceDistricts(Unity.Jobs.JobHandle inputDeps);
```

- `private CopyStartTiles(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle CopyStartTiles(Unity.Jobs.JobHandle inputDeps);
```

- `private GetAreaType(Game.Tools.SelectionType selectionType) : Game.Areas.AreaType`  

```csharp
private Game.Areas.AreaType GetAreaType(Game.Tools.SelectionType selectionType);
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint) : System.Boolean`  

```csharp
protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint);
```

- `protected virtual GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate) : System.Boolean`  

```csharp
protected virtual System.Boolean GetRaycastResult(Game.Tools.ControlPoint& controlPoint, System.Boolean& forceUpdate);
```

- `public GetSelectionQuad(Colossal.Mathematics.Quad3& quad) : System.Boolean`  

```csharp
public System.Boolean GetSelectionQuad(Colossal.Mathematics.Quad3& quad);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `private ToggleTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean select) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle ToggleTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean select);
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

- `private UpdateSelection(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateSelection(Unity.Jobs.JobHandle inputDeps);
```

- `private UpdateServiceDistricts(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateServiceDistricts(Unity.Jobs.JobHandle inputDeps);
```

- `private UpdateStartTiles(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateStartTiles(Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Tools.SelectionToolSystem+State`  
- `Game.Tools.SelectionToolSystem+FindEntitiesJob`  
- `Game.Tools.SelectionToolSystem+CreateDefinitionsJob`  
- `Game.Tools.SelectionToolSystem+ToggleEntityJob`  
- `Game.Tools.SelectionToolSystem+CopyStartTilesJob`  
- `Game.Tools.SelectionToolSystem+UpdateStartTilesJob`  
- `Game.Tools.SelectionToolSystem+CopyServiceDistrictsJob`  
- `Game.Tools.SelectionToolSystem+UpdateServiceDistrictsJob`  
- `Game.Tools.SelectionToolSystem+TypeHandle`  
- `Game.Tools.SelectionToolSystem+<get_toolActions>d__37`  

