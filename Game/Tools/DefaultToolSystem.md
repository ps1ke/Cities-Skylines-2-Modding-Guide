# Game.Tools.DefaultToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.Tools.ToolBaseSystem`  
**Implements:** `System.IEquatable<Game.Tools.ToolBaseSystem>`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DefaultToolSystem : Game.Tools.ToolBaseSystem, System.IEquatable<Game.Tools.ToolBaseSystem>
{
    private System.Boolean <underground>k__BackingField;
    private System.Boolean <ignoreErrors>k__BackingField;
    private System.Boolean <allowManipulation>k__BackingField;
    private System.Boolean <debugSelect>k__BackingField;
    private System.Boolean <debugLandValue>k__BackingField;
    private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DragQuery;
    private Unity.Entities.EntityQuery m_TempQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.Entity m_LastRaycastEntity;
    private Unity.Mathematics.float3 m_MouseDownPosition;
    private Game.Tools.DefaultToolSystem+State m_State;
    private Game.Input.IProxyAction m_DefaultToolApply;
    private System.Int32 m_LastSelectedIndex;
    private Game.Tools.DefaultToolSystem+TypeHandle __TypeHandle;
    public static const System.String kToolID;

    public System.String toolID { get; }
    public System.Boolean allowUnderground { get; }
    public System.Boolean underground { get; set; }
    public System.Boolean ignoreErrors { get; set; }
    public System.Boolean allowManipulation { get; set; }
    public System.Boolean debugSelect { get; set; }
    public System.Boolean debugLandValue { get; set; }
    private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }

    public DefaultToolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly, System.Boolean toggleSelected);
    private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void ElevationDown();
    public virtual System.Void ElevationScroll();
    public virtual System.Void ElevationUp();
    public virtual Game.Prefabs.PrefabBase GetPrefab();
    public virtual System.Void InitializeRaycast();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStartRunning();
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
    private System.Void PlaySelectedSound(Unity.Entities.Entity selected, System.Boolean forcePlay);
    private Unity.Jobs.JobHandle SelectTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean toggleSelected);
    private System.Void SetInfomodeRaycastSettings();
    private System.Void SetState(Game.Tools.DefaultToolSystem+State state);
    public virtual System.Void SetUnderground(System.Boolean underground);
    private System.Void StartDragging(Game.Common.RaycastHit raycastHit);
    private System.Void StopDragging();
    public virtual System.Boolean TrySetPrefab(Game.Prefabs.PrefabBase prefab);
    private Unity.Jobs.JobHandle Update(Unity.Jobs.JobHandle inputDeps);
    private virtual System.Void UpdateActions();
    private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity entity, System.Int32 index, Unity.Mathematics.float3 position, System.Boolean setPosition);
}
```


## Fields

- `private System.Boolean <underground>k__BackingField`  

```csharp
private System.Boolean <underground>k__BackingField;
```

- `private System.Boolean <ignoreErrors>k__BackingField`  

```csharp
private System.Boolean <ignoreErrors>k__BackingField;
```

- `private System.Boolean <allowManipulation>k__BackingField`  

```csharp
private System.Boolean <allowManipulation>k__BackingField;
```

- `private System.Boolean <debugSelect>k__BackingField`  

```csharp
private System.Boolean <debugSelect>k__BackingField;
```

- `private System.Boolean <debugLandValue>k__BackingField`  

```csharp
private System.Boolean <debugLandValue>k__BackingField;
```

- `private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier`  

```csharp
private Game.Tools.ToolOutputBarrier m_ToolOutputBarrier;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DragQuery`  

```csharp
private Unity.Entities.EntityQuery m_DragQuery;
```

- `private Unity.Entities.EntityQuery m_TempQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.Entity m_LastRaycastEntity`  

```csharp
private Unity.Entities.Entity m_LastRaycastEntity;
```

- `private Unity.Mathematics.float3 m_MouseDownPosition`  

```csharp
private Unity.Mathematics.float3 m_MouseDownPosition;
```

- `private Game.Tools.DefaultToolSystem+State m_State`  

```csharp
private Game.Tools.DefaultToolSystem+State m_State;
```

- `private Game.Input.IProxyAction m_DefaultToolApply`  

```csharp
private Game.Input.IProxyAction m_DefaultToolApply;
```

- `private System.Int32 m_LastSelectedIndex`  

```csharp
private System.Int32 m_LastSelectedIndex;
```

- `private Game.Tools.DefaultToolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.DefaultToolSystem+TypeHandle __TypeHandle;
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

- `public System.Boolean allowUnderground { get }`  

```csharp
public System.Boolean allowUnderground { get; }
```

- `public System.Boolean underground { get; set }`  

```csharp
public System.Boolean underground { get; set; }
```

- `public System.Boolean ignoreErrors { get; set }`  

```csharp
public System.Boolean ignoreErrors { get; set; }
```

- `public System.Boolean allowManipulation { get; set }`  

```csharp
public System.Boolean allowManipulation { get; set; }
```

- `public System.Boolean debugSelect { get; set }`  

```csharp
public System.Boolean debugSelect { get; set; }
```

- `public System.Boolean debugLandValue { get; set }`  

```csharp
public System.Boolean debugLandValue { get; set; }
```

- `private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get }`  

```csharp
private System.Collections.Generic.IEnumerable<Game.Input.IProxyAction> toolActions { private get; }
```


## Constructors

- `public DefaultToolSystem()`  

```csharp
public DefaultToolSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly = False, System.Boolean toggleSelected = False) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Apply(Unity.Jobs.JobHandle inputDeps, System.Boolean singleFrameOnly, System.Boolean toggleSelected);
```

- `private Cancel(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Cancel(Unity.Jobs.JobHandle inputDeps);
```

- `private Clear(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle Clear(Unity.Jobs.JobHandle inputDeps);
```

- `public virtual ElevationDown() : System.Void`  

```csharp
public virtual System.Void ElevationDown();
```

- `public virtual ElevationScroll() : System.Void`  

```csharp
public virtual System.Void ElevationScroll();
```

- `public virtual ElevationUp() : System.Void`  

```csharp
public virtual System.Void ElevationUp();
```

- `public virtual GetPrefab() : Game.Prefabs.PrefabBase`  

```csharp
public virtual Game.Prefabs.PrefabBase GetPrefab();
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

- `private PlaySelectedSound(Unity.Entities.Entity selected, System.Boolean forcePlay = False) : System.Void`  

```csharp
private System.Void PlaySelectedSound(Unity.Entities.Entity selected, System.Boolean forcePlay);
```

- `private SelectTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean toggleSelected) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle SelectTempEntity(Unity.Jobs.JobHandle inputDeps, System.Boolean toggleSelected);
```

- `private SetInfomodeRaycastSettings() : System.Void`  

```csharp
private System.Void SetInfomodeRaycastSettings();
```

- `private SetState(Game.Tools.DefaultToolSystem+State state) : System.Void`  

```csharp
private System.Void SetState(Game.Tools.DefaultToolSystem+State state);
```

- `public virtual SetUnderground(System.Boolean underground) : System.Void`  

```csharp
public virtual System.Void SetUnderground(System.Boolean underground);
```

- `private StartDragging(Game.Common.RaycastHit raycastHit) : System.Void`  

```csharp
private System.Void StartDragging(Game.Common.RaycastHit raycastHit);
```

- `private StopDragging() : System.Void`  

```csharp
private System.Void StopDragging();
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

- `private UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity entity, System.Int32 index, Unity.Mathematics.float3 position, System.Boolean setPosition) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateDefinitions(Unity.Jobs.JobHandle inputDeps, Unity.Entities.Entity entity, System.Int32 index, Unity.Mathematics.float3 position, System.Boolean setPosition);
```


## Nested types

- `Game.Tools.DefaultToolSystem+State`  
- `Game.Tools.DefaultToolSystem+CreateDefinitionsJob`  
- `Game.Tools.DefaultToolSystem+SelectEntityJob`  
- `Game.Tools.DefaultToolSystem+TypeHandle`  
- `Game.Tools.DefaultToolSystem+<get_toolActions>d__41`  

