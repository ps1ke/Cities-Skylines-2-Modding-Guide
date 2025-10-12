# Game.UI.InGame.InfoviewsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.Prefabs.InfoviewInitializeSystem m_InfoviewInitializeSystem`  
- `private Colossal.UI.Binding.RawValueBinding m_ActiveView`  
- `private System.Collections.Generic.List<Game.UI.InGame.InfoviewsUISystem+Infoview> m_InfoviewsCache`  
- `private Colossal.UI.Binding.RawValueBinding m_Infoviews`  
- `private Unity.Entities.EntityQuery m_UnlockedInfoviewQuery`  
- `private System.Boolean m_InfoviewChanged`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  

## Constructors

- `public InfoviewsUISystem()`  

## Methods

- `private BindActiveInfoview(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private BindColorLegend(Colossal.UI.Binding.IJsonWriter writer, UnityEngine.Color color, Game.UI.Localization.LocalizedString label) : System.Void`  
- `private BindColorLegends(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode) : System.Void`  
- `private BindGradientStop(Colossal.UI.Binding.IJsonWriter writer, System.Single offset, UnityEngine.Color color) : System.Void`  
- `private BindInfomode(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.InfomodeInfo info) : System.Void`  
- `private BindInfomodeGradientLegend(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode) : System.Void`  
- `private BindInfoviews(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private OnChanged() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `private OnInfoviewChanged(Game.Prefabs.InfoviewPrefab prefab) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public SetActiveInfoview(Unity.Entities.Entity entity) : System.Void`  
- `private SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority) : System.Void`  

## Nested types

- `Game.UI.InGame.InfoviewsUISystem+Infoview`  

