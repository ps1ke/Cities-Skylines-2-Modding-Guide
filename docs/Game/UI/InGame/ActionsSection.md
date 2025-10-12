# Game.UI.InGame.ActionsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  
- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  
- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  
- `private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem`  
- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  
- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  
- `private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem`  
- `private Game.Tools.TrafficRoutesSystem m_TrafficRoutesSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  
- `private Game.Prefabs.PolicyPrefab m_RouteOutOfServicePolicy`  
- `private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy`  
- `private Game.Prefabs.PolicyPrefab m_EmptyingPolicy`  
- `private Game.Prefabs.AreaPrefab m_LotPrefab`  
- `private System.Boolean m_EditingLot`  
- `private UnityEngine.Color32[] m_TrafficRouteColors`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MovingBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EditingLotBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_TrafficRoutesVisibleBinding`  
- `private Colossal.UI.Binding.ValueBinding<UnityEngine.Color32[]> m_TrafficRouteColorsBinding`  
- `private Colossal.UI.Binding.RawValueBinding m_MoveableObjectName`  
- `private System.Boolean <focusable>k__BackingField`  
- `private System.Boolean <focusing>k__BackingField`  
- `private System.Boolean <following>k__BackingField`  
- `private System.Boolean <followable>k__BackingField`  
- `private System.Boolean <moveable>k__BackingField`  
- `private System.Boolean <deletable>k__BackingField`  
- `private System.Boolean <disabled>k__BackingField`  
- `private System.Boolean <disableable>k__BackingField`  
- `private System.Boolean <hasTutorial>k__BackingField`  
- `private System.Boolean <emptying>k__BackingField`  
- `private System.Boolean <emptiable>k__BackingField`  
- `private System.Boolean <hasLotTool>k__BackingField`  
- `private System.Boolean <hasTrafficRoutes>k__BackingField`  

## Properties

- `protected System.String group { protected get }`  
- `public System.Boolean editingLot { get }`  
- `protected System.Boolean displayForDestroyedObjects { protected get }`  
- `protected System.Boolean displayForOutsideConnections { protected get }`  
- `protected System.Boolean displayForUnderConstruction { protected get }`  
- `protected System.Boolean displayForUpgrades { protected get }`  
- `private System.Boolean focusable { private get; private set }`  
- `private System.Boolean focusing { private get; private set }`  
- `private System.Boolean following { private get; private set }`  
- `private System.Boolean followable { private get; private set }`  
- `private System.Boolean moveable { private get; private set }`  
- `private System.Boolean deletable { private get; private set }`  
- `private System.Boolean disabled { private get; private set }`  
- `private System.Boolean disableable { private get; private set }`  
- `private System.Boolean hasTutorial { private get; private set }`  
- `private System.Boolean emptying { private get; private set }`  
- `private System.Boolean emptiable { private get; private set }`  
- `private System.Boolean hasLotTool { private get; private set }`  
- `private System.Boolean hasTrafficRoutes { private get; private set }`  

## Constructors

- `public ActionsSection()`  

## Methods

- `private BindObjectName(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `private OnDelete() : System.Void`  
- `private OnFocus() : System.Void`  
- `private OnFollow() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnProcess() : System.Void`  
- `private OnToggle() : System.Void`  
- `private OnToggleEmptying() : System.Void`  
- `private OnToggleLotTool() : System.Void`  
- `private OnToggleMove() : System.Void`  
- `private OnToggleTrafficRoutes() : System.Void`  
- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual Reset() : System.Void`  

