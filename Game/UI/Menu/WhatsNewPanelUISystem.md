# Game.UI.Menu.WhatsNewPanelUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Menu`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WhatsNewPanelUISystem : Game.UI.UISystemBase
{
    private Colossal.UI.Binding.RawValueBinding m_PanelBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibilityBinding;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_InitialTabBinding;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private static const System.String kGroup;

    public WhatsNewPanelUISystem();

    private System.Void BindPanel(Colossal.UI.Binding.IJsonWriter writer);
    private System.Collections.Generic.List<Game.Prefabs.UIWhatsNewPanelPrefab> GetSortedWhatsNewTabs(Unity.Entities.EntityQuery query);
    private System.Void OnClose(System.Boolean dismiss);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
}
```


## Fields

- `private Colossal.UI.Binding.RawValueBinding m_PanelBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_PanelBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibilityBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_VisibilityBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_InitialTabBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_InitialTabBinding;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public WhatsNewPanelUISystem()`  

```csharp
public WhatsNewPanelUISystem();
```


## Methods

- `private BindPanel(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindPanel(Colossal.UI.Binding.IJsonWriter writer);
```

- `private GetSortedWhatsNewTabs(Unity.Entities.EntityQuery query) : System.Collections.Generic.List<Game.Prefabs.UIWhatsNewPanelPrefab>`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.UIWhatsNewPanelPrefab> GetSortedWhatsNewTabs(Unity.Entities.EntityQuery query);
```

- `private OnClose(System.Boolean dismiss) : System.Void`  

```csharp
private System.Void OnClose(System.Boolean dismiss);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```


## Nested types

- `Game.UI.Menu.WhatsNewPanelUISystem+DlcComparer`  
- `Game.UI.Menu.WhatsNewPanelUISystem+<>c__DisplayClass8_0`  

