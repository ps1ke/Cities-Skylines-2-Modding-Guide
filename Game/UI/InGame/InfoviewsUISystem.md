# Game.UI.InGame.InfoviewsUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InfoviewsUISystem : Game.UI.UISystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.UnlockSystem m_UnlockSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.Prefabs.InfoviewInitializeSystem m_InfoviewInitializeSystem;
    private Colossal.UI.Binding.RawValueBinding m_ActiveView;
    private System.Collections.Generic.List<Game.UI.InGame.InfoviewsUISystem+Infoview> m_InfoviewsCache;
    private Colossal.UI.Binding.RawValueBinding m_Infoviews;
    private Unity.Entities.EntityQuery m_UnlockedInfoviewQuery;
    private System.Boolean m_InfoviewChanged;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }

    public InfoviewsUISystem();

    private System.Void BindActiveInfoview(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindColorLegend(Colossal.UI.Binding.IJsonWriter writer, UnityEngine.Color color, Game.UI.Localization.LocalizedString label);
    private System.Void BindColorLegends(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode);
    private System.Void BindGradientStop(Colossal.UI.Binding.IJsonWriter writer, System.Single offset, UnityEngine.Color color);
    private System.Void BindInfomode(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.InfomodeInfo info);
    private System.Void BindInfomodeGradientLegend(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode);
    private System.Void BindInfoviews(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void OnChanged();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    private System.Void OnInfoviewChanged(Game.Prefabs.InfoviewPrefab prefab);
    protected virtual System.Void OnUpdate();
    public System.Void SetActiveInfoview(Unity.Entities.Entity entity);
    private System.Void SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority);
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  

```csharp
private Game.Prefabs.UnlockSystem m_UnlockSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.Prefabs.InfoviewInitializeSystem m_InfoviewInitializeSystem`  

```csharp
private Game.Prefabs.InfoviewInitializeSystem m_InfoviewInitializeSystem;
```

- `private Colossal.UI.Binding.RawValueBinding m_ActiveView`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ActiveView;
```

- `private System.Collections.Generic.List<Game.UI.InGame.InfoviewsUISystem+Infoview> m_InfoviewsCache`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.InfoviewsUISystem+Infoview> m_InfoviewsCache;
```

- `private Colossal.UI.Binding.RawValueBinding m_Infoviews`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_Infoviews;
```

- `private Unity.Entities.EntityQuery m_UnlockedInfoviewQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedInfoviewQuery;
```

- `private System.Boolean m_InfoviewChanged`  

```csharp
private System.Boolean m_InfoviewChanged;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```


## Constructors

- `public InfoviewsUISystem()`  

```csharp
public InfoviewsUISystem();
```


## Methods

- `private BindActiveInfoview(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindActiveInfoview(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindColorLegend(Colossal.UI.Binding.IJsonWriter writer, UnityEngine.Color color, Game.UI.Localization.LocalizedString label) : System.Void`  

```csharp
private System.Void BindColorLegend(Colossal.UI.Binding.IJsonWriter writer, UnityEngine.Color color, Game.UI.Localization.LocalizedString label);
```

- `private BindColorLegends(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode) : System.Void`  

```csharp
private System.Void BindColorLegends(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode);
```

- `private BindGradientStop(Colossal.UI.Binding.IJsonWriter writer, System.Single offset, UnityEngine.Color color) : System.Void`  

```csharp
private System.Void BindGradientStop(Colossal.UI.Binding.IJsonWriter writer, System.Single offset, UnityEngine.Color color);
```

- `private BindInfomode(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.InfomodeInfo info) : System.Void`  

```csharp
private System.Void BindInfomode(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.InfomodeInfo info);
```

- `private BindInfomodeGradientLegend(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode) : System.Void`  

```csharp
private System.Void BindInfomodeGradientLegend(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.IGradientInfomode gradientInfomode);
```

- `private BindInfoviews(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindInfoviews(Colossal.UI.Binding.IJsonWriter writer);
```

- `private OnChanged() : System.Void`  

```csharp
private System.Void OnChanged();
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

- `private OnInfoviewChanged(Game.Prefabs.InfoviewPrefab prefab) : System.Void`  

```csharp
private System.Void OnInfoviewChanged(Game.Prefabs.InfoviewPrefab prefab);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public SetActiveInfoview(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void SetActiveInfoview(Unity.Entities.Entity entity);
```

- `private SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority) : System.Void`  

```csharp
private System.Void SetInfomodeActive(Unity.Entities.Entity entity, System.Boolean active, System.Int32 priority);
```


## Nested types

- `Game.UI.InGame.InfoviewsUISystem+Infoview`  

