# Game.UI.InGame.TransportationOverviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.UI.NameSystem m_NameSystem`  
- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  
- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.Entity m_OutOfServicePolicy`  
- `private Unity.Entities.Entity m_DayRoutePolicy`  
- `private Unity.Entities.Entity m_NightRoutePolicy`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Entities.EntityQuery m_LineQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedLineQuery`  
- `private Unity.Entities.EntityQuery m_UnlockQuery`  
- `private Unity.Entities.EntityArchetype m_ColorUpdateArchetype`  
- `private Colossal.UI.Binding.RawValueBinding m_TransportLines`  
- `private Colossal.UI.Binding.RawValueBinding m_PassengerTypes`  
- `private Colossal.UI.Binding.RawValueBinding m_CargoTypes`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedCargoType`  
- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedPassengerType`  
- `private Game.Prefabs.UITransportConfigurationPrefab m_Config`  
- `private Game.UI.UIUpdateState m_UpdateState`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  

## Constructors

- `public TransportationOverviewUISystem()`  

## Methods

- `private BindCargoTypes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindLine(Game.UI.InGame.UITransportLineData lineData, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindLines(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  
- `private BindPassengerTypes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindTypes(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UITransportItem[] items) : System.Void`  
- `private DeleteLine(Unity.Entities.Entity entity) : System.Void`  
- `private GetInitialSelectedType() : System.String`  
- `public HideLine(Unity.Entities.Entity entity, System.Boolean showOthers) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RequestUpdate() : System.Void`  
- `public ResetLinesVisibility() : System.Void`  
- `private SelectLine(Unity.Entities.Entity entity) : System.Void`  
- `private SetLineColor(Unity.Entities.Entity entity, UnityEngine.Color32 color) : System.Void`  
- `private SetLineName(Unity.Entities.Entity entity, System.String name) : System.Void`  
- `private SetLineSchedule(Unity.Entities.Entity entity, System.Int32 schedule) : System.Void`  
- `public SetLineState(Unity.Entities.Entity entity, System.Boolean state) : System.Void`  
- `private SetSelectedCargoType(System.String type) : System.Void`  
- `private SetSelectedPassengerType(System.String type) : System.Void`  
- `public ShowLine(Unity.Entities.Entity entity, System.Boolean hideOthers) : System.Void`  
- `public ToggleHighlight(Unity.Entities.Entity entity) : System.Void`  

