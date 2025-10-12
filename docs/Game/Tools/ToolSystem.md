# Game.Tools.ToolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public System.Action<Game.Tools.ToolBaseSystem> EventToolChanged`  
- `public System.Action<Game.Prefabs.PrefabBase> EventPrefabChanged`  
- `public System.Action<Game.Prefabs.InfoviewPrefab> EventInfoviewChanged`  
- `public System.Action EventInfomodesChanged`  
- `private Game.Tools.ToolBaseSystem m_ActiveTool`  
- `private Unity.Entities.Entity m_Selected`  
- `private System.Int32 <selectedIndex>k__BackingField`  
- `private Game.GameMode <actionMode>k__BackingField`  
- `private System.Boolean <ignoreErrors>k__BackingField`  
- `private System.Boolean <fullUpdateRequired>k__BackingField`  
- `private Game.Tools.ToolBaseSystem m_LastTool`  
- `private Game.Prefabs.InfoviewPrefab m_CurrentInfoview`  
- `private Game.Prefabs.InfoviewPrefab m_LastToolInfoview`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UpdateSystem m_UpdateSystem`  
- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private System.Collections.Generic.List<Game.Tools.ToolBaseSystem> m_Tools`  
- `private System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> m_LastToolInfomodes`  
- `private System.Collections.Generic.Dictionary<Game.Prefabs.InfoviewPrefab, System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>> m_InfomodeMap`  
- `private UnityEngine.Vector4[] m_InfomodeColors`  
- `private UnityEngine.Vector4[] m_InfomodeParams`  
- `private System.Int32[] m_InfomodeCounts`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_Infomodes`  
- `private System.Single m_InfoviewTimer`  
- `private System.Boolean m_FullUpdateRequired`  
- `private System.Boolean m_InfoviewUpdateRequired`  
- `private System.Boolean m_IsUpdating`  
- `private Game.Input.InputBarrier m_ToolActionBarrier`  
- `private System.Collections.Generic.Dictionary<Game.Input.ProxyAction, Game.Input.InputBarrier> m_MouseToolBarriers`  
- `protected static const System.String kToolKeyGroup`  
- `protected static const System.String kToolCancelKeyGroup`  
- `protected static const System.String kToolApplyKeyAction`  
- `protected static const System.String kToolCancelKeyAction`  

## Properties

- `public Game.Tools.ToolBaseSystem activeTool { get; set }`  
- `public Unity.Entities.Entity selected { get; set }`  
- `public System.Int32 selectedIndex { get; set }`  
- `public Game.Prefabs.PrefabBase activePrefab { get }`  
- `public Game.Prefabs.InfoviewPrefab infoview { get; set }`  
- `public Game.Prefabs.InfoviewPrefab activeInfoview { get }`  
- `public Game.GameMode actionMode { get; private set }`  
- `public Game.Tools.ApplyMode applyMode { get }`  
- `public System.Boolean ignoreErrors { get; set }`  
- `public System.Boolean fullUpdateRequired { get; private set }`  
- `public System.Collections.Generic.List<Game.Tools.ToolBaseSystem> tools { get }`  

## Constructors

- `public ToolSystem()`  

## Methods

- `private <OnCreate>b__64_3(Game.Input.InputManager+ControlScheme activeControlScheme) : System.Void`  
- `private <OnCreate>b__64_4(System.Boolean mouseOverUI) : System.Void`  
- `private Activate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, System.Int32 priority) : System.Void`  
- `public ActivatePrefabTool(Game.Prefabs.PrefabBase prefab) : System.Boolean`  
- `private ClearInfomodes() : System.Void`  
- `private Deactivate(Unity.Entities.Entity entity, Game.Prefabs.InfomodePrefab prefab, Game.Prefabs.InfomodeActive infomodeActive) : System.Void`  
- `private Deactivate(System.Int32 colorGroup, System.Int32 activeIndex) : System.Void`  
- `public GetInfomodes(Game.Prefabs.InfoviewPrefab infoview) : System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>`  
- `public GetInfoviewInfomodes() : System.Collections.Generic.List<Game.Prefabs.InfomodeInfo>`  
- `public IsInfomodeActive(Game.Prefabs.InfomodePrefab prefab) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private RefreshInputBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI) : System.Void`  
- `public RequireFullUpdate() : System.Void`  
- `public SetInfomodeActive(Game.Prefabs.InfomodePrefab prefab, System.Boolean active, System.Int32 priority) : System.Void`  
- `public SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority) : System.Void`  
- `private SetInfoview(Game.Prefabs.InfoviewPrefab value, System.Collections.Generic.List<Game.Prefabs.InfomodePrefab> infomodes) : System.Void`  
- `private ShouldBlockBarrier(Game.Input.InputManager+ControlScheme activeControlScheme, System.Boolean mouseOverUI) : System.Boolean`  
- `private ToolUpdate() : System.Void`  
- `private UpdateInfoviewColors() : System.Void`  

## Nested types

- `Game.Tools.ToolSystem+<>c`  
- `Game.Tools.ToolSystem+<>c__DisplayClass64_0`  

