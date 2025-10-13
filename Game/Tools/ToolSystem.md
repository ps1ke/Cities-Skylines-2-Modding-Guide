# Game.Tools.ToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    public System.Action<Game.Tools.ToolBaseSystem> EventToolChanged;
    public System.Action<Game.Prefabs.PrefabBase> EventPrefabChanged;
    public System.Action<Game.Prefabs.InfoviewPrefab> EventInfoviewChanged;
    public System.Action EventInfomodesChanged;
    private Game.Tools.ToolBaseSystem m_ActiveTool;
    private Unity.Entities.Entity m_Selected;
    private System.Int32 <selectedIndex>k__BackingField;
    private Game.GameMode <actionMode>k__BackingField;
    private System.Boolean <ignoreErrors>k__BackingField;
    private System.Boolean <fullUpdateRequired>k__BackingField;
    private Game.Tools.ToolBaseSystem m_LastTool;
    private Game.Prefabs.InfoviewPrefab m_CurrentInfoview;
    private Game.Prefabs.InfoviewPrefab m_LastToolInfoview;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UpdateSystem m_UpdateSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private System.Collections.Generic.List<Game.Tools.ToolBaseSystem> m_Tools;
    private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> m_LastToolInfomodes;
    private System.Collections.Generic.Dictionary<Game.Prefabs.InfoviewPrefab, System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>> m_InfomodeMap;
    private UnityEngine.Vector4[] m_InfomodeColors;
    private UnityEngine.Vector4[] m_InfomodeParams;
    private System.Int32[] m_InfomodeCounts;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_Infomodes;
    private System.Single m_InfoviewTimer;
    private System.Boolean m_FullUpdateRequired;
    private System.Boolean m_InfoviewUpdateRequired;
    private System.Boolean m_IsUpdating;
    private Game.Input.InputBarrier m_ToolActionBarrier;
    private System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.Input.InputBarrier> m_MouseToolBarriers;
    protected static const System.String kToolKeyGroup;
    protected static const System.String kToolCancelKeyGroup;
    protected static const System.String kToolApplyKeyAction;
    protected static const System.String kToolCancelKeyAction;

    public Game.Tools.ToolBaseSystem activeTool { get; set; }
    public Unity.Entities.Entity selected { get; set; }
    public System.Int32 selectedIndex { get; set; }
    public Game.Prefabs.PrefabBase activePrefab { get; }
    public Game.Prefabs.InfoviewPrefab infoview { get; set; }
    public Game.Prefabs.InfoviewPrefab activeInfoview { get; }
    public Game.GameMode actionMode { get; private set; }
    public Game.Tools.ApplyMode applyMode { get; }
    public System.Boolean ignoreErrors { get; set; }
    public System.Boolean fullUpdateRequired { get; private set; }
    public System.Collections.Generic.List<Game.Tools.ToolBaseSystem> tools { get; }

    public ToolSystem();

    private System.Void <OnCreate>b__64_3(Game.Input.InputManager+ControlScheme activeControlScheme);
    private System.Void <OnCreate>b__64_4(System.Boolean mouseOverUI);
    private System.Void Activate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, System.Int32 priority);
    public System.Boolean ActivatePrefabTool(Game.Prefabs.PrefabBase prefab);
    private System.Void ClearInfomodes();
    private System.Void Deactivate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, Game.Prefabs.InfomodeActive infomodeActive);
    private System.Void Deactivate(System.Int32 colorGroup, System.Int32 activeIndex);
    public System.Collections.Generic.List<Game.Prefabs.InfomodeInfo> GetInfomodes(Game.Prefabs.InfoviewPrefab infoview);
    public System.Collections.Generic.List<Game.Prefabs.InfomodeInfo> GetInfoviewInfomodes();
    public System.Boolean IsInfomodeActive(Game.Prefabs.InfomodePrefab prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void RefreshInputBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI);
    public System.Void RequireFullUpdate();
    public System.Void SetInfomodeActive(Game.Prefabs.InfomodePrefab prefab, System.Boolean active, System.Int32 priority);
    public System.Void SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority);
    private System.Void SetInfoview(Game.Prefabs.InfoviewPrefab value, System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes);
    private System.Boolean ShouldBlockBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI);
    private System.Void ToolUpdate();
    private System.Void UpdateInfoviewColors();
}
```


## Fields

- `public System.Action<Game.Tools.ToolBaseSystem> EventToolChanged`  

```csharp
public System.Action<Game.Tools.ToolBaseSystem> EventToolChanged;
```

- `public System.Action<Game.Prefabs.PrefabBase> EventPrefabChanged`  

```csharp
public System.Action<Game.Prefabs.PrefabBase> EventPrefabChanged;
```

- `public System.Action<Game.Prefabs.InfoviewPrefab> EventInfoviewChanged`  

```csharp
public System.Action<Game.Prefabs.InfoviewPrefab> EventInfoviewChanged;
```

- `public System.Action EventInfomodesChanged`  

```csharp
public System.Action EventInfomodesChanged;
```

- `private Game.Tools.ToolBaseSystem m_ActiveTool`  

```csharp
private Game.Tools.ToolBaseSystem m_ActiveTool;
```

- `private Unity.Entities.Entity m_Selected`  

```csharp
private Unity.Entities.Entity m_Selected;
```

- `private System.Int32 <selectedIndex>k__BackingField`  

```csharp
private System.Int32 <selectedIndex>k__BackingField;
```

- `private Game.GameMode <actionMode>k__BackingField`  

```csharp
private Game.GameMode <actionMode>k__BackingField;
```

- `private System.Boolean <ignoreErrors>k__BackingField`  

```csharp
private System.Boolean <ignoreErrors>k__BackingField;
```

- `private System.Boolean <fullUpdateRequired>k__BackingField`  

```csharp
private System.Boolean <fullUpdateRequired>k__BackingField;
```

- `private Game.Tools.ToolBaseSystem m_LastTool`  

```csharp
private Game.Tools.ToolBaseSystem m_LastTool;
```

- `private Game.Prefabs.InfoviewPrefab m_CurrentInfoview`  

```csharp
private Game.Prefabs.InfoviewPrefab m_CurrentInfoview;
```

- `private Game.Prefabs.InfoviewPrefab m_LastToolInfoview`  

```csharp
private Game.Prefabs.InfoviewPrefab m_LastToolInfoview;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UpdateSystem m_UpdateSystem`  

```csharp
private Game.UpdateSystem m_UpdateSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private System.Collections.Generic.List<Game.Tools.ToolBaseSystem> m_Tools`  

```csharp
private System.Collections.Generic.List<Game.Tools.ToolBaseSystem> m_Tools;
```

- `private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> m_LastToolInfomodes`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> m_LastToolInfomodes;
```

- `private System.Collections.Generic.Dictionary<Game.Prefabs.InfoviewPrefab, System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>> m_InfomodeMap`  

```csharp
private System.Collections.Generic.Dictionary<Game.Prefabs.InfoviewPrefab, System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>> m_InfomodeMap;
```

- `private UnityEngine.Vector4[] m_InfomodeColors`  

```csharp
private UnityEngine.Vector4[] m_InfomodeColors;
```

- `private UnityEngine.Vector4[] m_InfomodeParams`  

```csharp
private UnityEngine.Vector4[] m_InfomodeParams;
```

- `private System.Int32[] m_InfomodeCounts`  

```csharp
private System.Int32[] m_InfomodeCounts;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_Infomodes`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_Infomodes;
```

- `private System.Single m_InfoviewTimer`  

```csharp
private System.Single m_InfoviewTimer;
```

- `private System.Boolean m_FullUpdateRequired`  

```csharp
private System.Boolean m_FullUpdateRequired;
```

- `private System.Boolean m_InfoviewUpdateRequired`  

```csharp
private System.Boolean m_InfoviewUpdateRequired;
```

- `private System.Boolean m_IsUpdating`  

```csharp
private System.Boolean m_IsUpdating;
```

- `private Game.Input.InputBarrier m_ToolActionBarrier`  

```csharp
private Game.Input.InputBarrier m_ToolActionBarrier;
```

- `private System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.Input.InputBarrier> m_MouseToolBarriers`  

```csharp
private System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.Input.InputBarrier> m_MouseToolBarriers;
```

- `protected static const System.String kToolKeyGroup`  

```csharp
protected static const System.String kToolKeyGroup;
```

- `protected static const System.String kToolCancelKeyGroup`  

```csharp
protected static const System.String kToolCancelKeyGroup;
```

- `protected static const System.String kToolApplyKeyAction`  

```csharp
protected static const System.String kToolApplyKeyAction;
```

- `protected static const System.String kToolCancelKeyAction`  

```csharp
protected static const System.String kToolCancelKeyAction;
```


## Properties

- `public Game.Tools.ToolBaseSystem activeTool { get; set }`  

```csharp
public Game.Tools.ToolBaseSystem activeTool { get; set; }
```

- `public Unity.Entities.Entity selected { get; set }`  

```csharp
public Unity.Entities.Entity selected { get; set; }
```

- `public System.Int32 selectedIndex { get; set }`  

```csharp
public System.Int32 selectedIndex { get; set; }
```

- `public Game.Prefabs.PrefabBase activePrefab { get }`  

```csharp
public Game.Prefabs.PrefabBase activePrefab { get; }
```

- `public Game.Prefabs.InfoviewPrefab infoview { get; set }`  

```csharp
public Game.Prefabs.InfoviewPrefab infoview { get; set; }
```

- `public Game.Prefabs.InfoviewPrefab activeInfoview { get }`  

```csharp
public Game.Prefabs.InfoviewPrefab activeInfoview { get; }
```

- `public Game.GameMode actionMode { get; private set }`  

```csharp
public Game.GameMode actionMode { get; private set; }
```

- `public Game.Tools.ApplyMode applyMode { get }`  

```csharp
public Game.Tools.ApplyMode applyMode { get; }
```

- `public System.Boolean ignoreErrors { get; set }`  

```csharp
public System.Boolean ignoreErrors { get; set; }
```

- `public System.Boolean fullUpdateRequired { get; private set }`  

```csharp
public System.Boolean fullUpdateRequired { get; private set; }
```

- `public System.Collections.Generic.List<Game.Tools.ToolBaseSystem> tools { get }`  

```csharp
public System.Collections.Generic.List<Game.Tools.ToolBaseSystem> tools { get; }
```


## Constructors

- `public ToolSystem()`  

```csharp
public ToolSystem();
```


## Methods

- `private <OnCreate>b__64_3(Game.Input.InputManager+ControlScheme activeControlScheme) : System.Void`  

```csharp
private System.Void <OnCreate>b__64_3(Game.Input.InputManager+ControlScheme activeControlScheme);
```

- `private <OnCreate>b__64_4(System.Boolean mouseOverUI) : System.Void`  

```csharp
private System.Void <OnCreate>b__64_4(System.Boolean mouseOverUI);
```

- `private Activate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, System.Int32 priority) : System.Void`  

```csharp
private System.Void Activate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, System.Int32 priority);
```

- `public ActivatePrefabTool(Game.Prefabs.PrefabBase prefab) : System.Boolean`  

```csharp
public System.Boolean ActivatePrefabTool(Game.Prefabs.PrefabBase prefab);
```

- `private ClearInfomodes() : System.Void`  

```csharp
private System.Void ClearInfomodes();
```

- `private Deactivate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, Game.Prefabs.InfomodeActive infomodeActive) : System.Void`  

```csharp
private System.Void Deactivate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, Game.Prefabs.InfomodeActive infomodeActive);
```

- `private Deactivate(System.Int32 colorGroup, System.Int32 activeIndex) : System.Void`  

```csharp
private System.Void Deactivate(System.Int32 colorGroup, System.Int32 activeIndex);
```

- `public GetInfomodes(Game.Prefabs.InfoviewPrefab infoview) : System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.InfomodeInfo> GetInfomodes(Game.Prefabs.InfoviewPrefab infoview);
```

- `public GetInfoviewInfomodes() : System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>`  

```csharp
public System.Collections.Generic.List<Game.Prefabs.InfomodeInfo> GetInfoviewInfomodes();
```

- `public IsInfomodeActive(Game.Prefabs.InfomodePrefab prefab) : System.Boolean`  

```csharp
public System.Boolean IsInfomodeActive(Game.Prefabs.InfomodePrefab prefab);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private RefreshInputBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI) : System.Void`  

```csharp
private System.Void RefreshInputBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI);
```

- `public RequireFullUpdate() : System.Void`  

```csharp
public System.Void RequireFullUpdate();
```

- `public SetInfomodeActive(Game.Prefabs.InfomodePrefab prefab, System.Boolean active, System.Int32 priority) : System.Void`  

```csharp
public System.Void SetInfomodeActive(Game.Prefabs.InfomodePrefab prefab, System.Boolean active, System.Int32 priority);
```

- `public SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority) : System.Void`  

```csharp
public System.Void SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority);
```

- `private SetInfoview(Game.Prefabs.InfoviewPrefab value, System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes) : System.Void`  

```csharp
private System.Void SetInfoview(Game.Prefabs.InfoviewPrefab value, System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes);
```

- `private ShouldBlockBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI) : System.Boolean`  

```csharp
private System.Boolean ShouldBlockBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI);
```

- `private ToolUpdate() : System.Void`  

```csharp
private System.Void ToolUpdate();
```

- `private UpdateInfoviewColors() : System.Void`  

```csharp
private System.Void UpdateInfoviewColors();
```


## Nested types

- `Game.Tools.ToolSystem+<>c`  
- `Game.Tools.ToolSystem+<>c__DisplayClass64_0`  

