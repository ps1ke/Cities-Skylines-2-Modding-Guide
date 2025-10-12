# Game.UI.Menu.WhatsNewPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Colossal.UI.Binding.RawValueBinding m_PanelBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibilityBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InitialTabBinding`  
- `private Unity.Entities.EntityQuery m_Query`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private static const System.String kGroup`  

## Constructors

- `public WhatsNewPanelUISystem()`  

## Methods

- `private BindPanel(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `private GetSortedWhatsNewTabs(Unity.Entities.EntityQuery query) : System.Collections.Generic.List<Game.Prefabs.UIWhatsNewPanelPrefab>`  
- `private OnClose(System.Boolean dismiss) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

## Nested types

- `Game.UI.Menu.WhatsNewPanelUISystem+DlcComparer`  
- `Game.UI.Menu.WhatsNewPanelUISystem+<>c__DisplayClass8_0`  

