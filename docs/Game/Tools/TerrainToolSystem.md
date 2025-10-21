# Game.Tools.TerrainToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TerrainToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private Game.Prefabs.TerraformingPrefab <prefab>k__BackingField;
    private Game.Audio.AudioManager m_AudioManager;
    private UnityEngine.AudioSource m_AudioSource;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_BrushQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_VisibleQuery;
    private Game.Input.IProxyAction m_EraseMaterial;
    private Game.Input.IProxyAction m_EraseResource;
    private Game.Input.IProxyAction m_FastSoften;
    private Game.Input.IProxyAction m_LevelTerrain;
    private Game.Input.IProxyAction m_LowerTerrain;
    private Game.Input.IProxyAction m_PaintMaterial;
    private Game.Input.IProxyAction m_PaintResource;
    private Game.Input.IProxyAction m_RaiseTerrain;
    private Game.Input.IProxyAction m_SetLevelTarget;
    private Game.Input.IProxyAction m_SetSlopeTarget;
    private Game.Input.IProxyAction m_SlopeTerrain;
    private Game.Input.IProxyAction m_SoftenTerrain;
    private Game.Tools.ControlPoint m_RaycastPoint;
    private Game.Tools.ControlPoint m_StartPoint;
    private Unity.Mathematics.float3 m_TargetPosition;
    private Unity.Mathematics.float3 m_ApplyPosition;
    private System.Boolean m_TargetSet;
    private Game.Tools.TerrainToolSystem+State m_State;
    private Game.Tools.TerrainToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;
    public static const System.String kTerrainToolKeyGroup;

    public System.String toolID { get; }
    public Game.Prefabs.TerraformingPrefab prefab { get; private set; }
    public System.Boolean brushing { get; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
    public System.Single brushHeight { get; set; }

    public TerrainToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    private System.Boolean HaveBrushSettingsChanged();
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    public System.Void SetDisableFX();
    public System.Void SetPrefab(Game.Prefabs.TerraformingPrefab value);
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Game.Prefabs.TerraformingPrefab <prefab>k__BackingField`  

```csharp
private Game.Prefabs.TerraformingPrefab <prefab>k__BackingField;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private UnityEngine.AudioSource m_AudioSource`  

```csharp
private UnityEngine.AudioSource m_AudioSource;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_BrushQuery`  

```csharp
private Unity.Entities.EntityQuery m_BrushQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_VisibleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VisibleQuery;
```

- `private Game.Input.IProxyAction m_EraseMaterial`  

```csharp
private Game.Input.IProxyAction m_EraseMaterial;
```

- `private Game.Input.IProxyAction m_EraseResource`  

```csharp
private Game.Input.IProxyAction m_EraseResource;
```

- `private Game.Input.IProxyAction m_FastSoften`  

```csharp
private Game.Input.IProxyAction m_FastSoften;
```

- `private Game.Input.IProxyAction m_LevelTerrain`  

```csharp
private Game.Input.IProxyAction m_LevelTerrain;
```

- `private Game.Input.IProxyAction m_LowerTerrain`  

```csharp
private Game.Input.IProxyAction m_LowerTerrain;
```

- `private Game.Input.IProxyAction m_PaintMaterial`  

```csharp
private Game.Input.IProxyAction m_PaintMaterial;
```

- `private Game.Input.IProxyAction m_PaintResource`  

```csharp
private Game.Input.IProxyAction m_PaintResource;
```

- `private Game.Input.IProxyAction m_RaiseTerrain`  

```csharp
private Game.Input.IProxyAction m_RaiseTerrain;
```

- `private Game.Input.IProxyAction m_SetLevelTarget`  

```csharp
private Game.Input.IProxyAction m_SetLevelTarget;
```

- `private Game.Input.IProxyAction m_SetSlopeTarget`  

```csharp
private Game.Input.IProxyAction m_SetSlopeTarget;
```

- `private Game.Input.IProxyAction m_SlopeTerrain`  

```csharp
private Game.Input.IProxyAction m_SlopeTerrain;
```

- `private Game.Input.IProxyAction m_SoftenTerrain`  

```csharp
private Game.Input.IProxyAction m_SoftenTerrain;
```

- `private Game.Tools.ControlPoint m_RaycastPoint`  

```csharp
private Game.Tools.ControlPoint m_RaycastPoint;
```

- `private Game.Tools.ControlPoint m_StartPoint`  

```csharp
private Game.Tools.ControlPoint m_StartPoint;
```

- `private Unity.Mathematics.float3 m_TargetPosition`  

```csharp
private Unity.Mathematics.float3 m_TargetPosition;
```

- `private Unity.Mathematics.float3 m_ApplyPosition`  

```csharp
private Unity.Mathematics.float3 m_ApplyPosition;
```

- `private System.Boolean m_TargetSet`  

```csharp
private System.Boolean m_TargetSet;
```

- `private Game.Tools.TerrainToolSystem+State m_State`  

```csharp
private Game.Tools.TerrainToolSystem+State m_State;
```

- `private Game.Tools.TerrainToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.TerrainToolSystem+TypeHandle __TypeHandle;
```

- `public static const System.String kToolID`  

```csharp
public static const System.String kToolID;
```

- `public static const System.String kTerrainToolKeyGroup`  

```csharp
public static const System.String kTerrainToolKeyGroup;
```


## Properties

- `public System.String toolID { get }`  

```csharp
public System.String toolID { get; }
```

- `public Game.Prefabs.TerraformingPrefab prefab { get; private set }`  

```csharp
public Game.Prefabs.TerraformingPrefab prefab { get; private set; }
```

- `public System.Boolean brushing { get }`  

```csharp
public System.Boolean brushing { get; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```

- `public System.Single brushHeight { get; set }`  

```csharp
public System.Single brushHeight { get; set; }
```


## Constructors

- `public TerrainToolSystem()`  

```csharp
public TerrainToolSystem();
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

- `public virtual GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask) : System.Void`  

```csharp
public virtual System.Void GetAvailableSnapMask(Game.Tools.Snap& onMask, Game.Tools.Snap& offMask);
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
```

- `private HaveBrushSettingsChanged() : System.Boolean`  

```csharp
private System.Boolean HaveBrushSettingsChanged();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
```

- `public SetDisableFX() : System.Void`  

```csharp
public System.Void SetDisableFX();
```

- `public SetPrefab(Game.Prefabs.TerraformingPrefab value) : System.Void`  

```csharp
public System.Void SetPrefab(Game.Prefabs.TerraformingPrefab value);
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

- `Game.Tools.TerrainToolSystem+State`  
- `Game.Tools.TerrainToolSystem+CreateDefinitionsJob`  
- `Game.Tools.TerrainToolSystem+TypeHandle`  
- `Game.Tools.TerrainToolSystem+<get_toolActions>d__32`  

