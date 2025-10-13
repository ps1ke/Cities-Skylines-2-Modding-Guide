# Game.UI.InGame.TransportationOverviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportationOverviewUISystem : Game.UI.UISystemBase
{
    private Game.UI.NameSystem m_NameSystem;
    private Game.Prefabs.UnlockSystem m_UnlockSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.Entity m_OutOfServicePolicy;
    private Unity.Entities.Entity m_DayRoutePolicy;
    private Unity.Entities.Entity m_NightRoutePolicy;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityQuery m_LineQuery;
    private Unity.Entities.EntityQuery m_ModifiedLineQuery;
    private Unity.Entities.EntityQuery m_UnlockQuery;
    private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;
    private Colossal.UI.Binding.RawValueBinding m_TransportLines;
    private Colossal.UI.Binding.RawValueBinding m_PassengerTypes;
    private Colossal.UI.Binding.RawValueBinding m_CargoTypes;
    private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedCargoType;
    private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedPassengerType;
    private Game.Prefabs.UITransportConfigurationPrefab m_Config;
    private Game.UI.UIUpdateState m_UpdateState;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }

    public TransportationOverviewUISystem();

    private System.Void BindCargoTypes(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindLine(Game.UI.InGame.UITransportLineData lineData, Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindLines(Colossal.UI.Binding.IJsonWriter binder);
    private System.Void BindPassengerTypes(Colossal.UI.Binding.IJsonWriter writer);
    private System.Void BindTypes(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UITransportItem[] items);
    private System.Void DeleteLine(Unity.Entities.Entity entity);
    private System.String GetInitialSelectedType();
    public System.Void HideLine(Unity.Entities.Entity entity, System.Boolean showOthers);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public System.Void RequestUpdate();
    public System.Void ResetLinesVisibility();
    private System.Void SelectLine(Unity.Entities.Entity entity);
    private System.Void SetLineColor(Unity.Entities.Entity entity, UnityEngine.Color32 color);
    private System.Void SetLineName(Unity.Entities.Entity entity, System.String name);
    private System.Void SetLineSchedule(Unity.Entities.Entity entity, System.Int32 schedule);
    public System.Void SetLineState(Unity.Entities.Entity entity, System.Boolean state);
    private System.Void SetSelectedCargoType(System.String type);
    private System.Void SetSelectedPassengerType(System.String type);
    public System.Void ShowLine(Unity.Entities.Entity entity, System.Boolean hideOthers);
    public System.Void ToggleHighlight(Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  

```csharp
private Game.Prefabs.UnlockSystem m_UnlockSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.Entity m_OutOfServicePolicy`  

```csharp
private Unity.Entities.Entity m_OutOfServicePolicy;
```

- `private Unity.Entities.Entity m_DayRoutePolicy`  

```csharp
private Unity.Entities.Entity m_DayRoutePolicy;
```

- `private Unity.Entities.Entity m_NightRoutePolicy`  

```csharp
private Unity.Entities.Entity m_NightRoutePolicy;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityQuery m_LineQuery`  

```csharp
private Unity.Entities.EntityQuery m_LineQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedLineQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedLineQuery;
```

- `private Unity.Entities.EntityQuery m_UnlockQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockQuery;
```

- `private Unity.Entities.EntityArchetype m_ColorUpdateArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ColorUpdateArchetype;
```

- `private Colossal.UI.Binding.RawValueBinding m_TransportLines`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_TransportLines;
```

- `private Colossal.UI.Binding.RawValueBinding m_PassengerTypes`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_PassengerTypes;
```

- `private Colossal.UI.Binding.RawValueBinding m_CargoTypes`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_CargoTypes;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedCargoType`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedCargoType;
```

- `private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedPassengerType`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.String> m_SelectedPassengerType;
```

- `private Game.Prefabs.UITransportConfigurationPrefab m_Config`  

```csharp
private Game.Prefabs.UITransportConfigurationPrefab m_Config;
```

- `private Game.UI.UIUpdateState m_UpdateState`  

```csharp
private Game.UI.UIUpdateState m_UpdateState;
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

- `public TransportationOverviewUISystem()`  

```csharp
public TransportationOverviewUISystem();
```


## Methods

- `private BindCargoTypes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindCargoTypes(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindLine(Game.UI.InGame.UITransportLineData lineData, Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindLine(Game.UI.InGame.UITransportLineData lineData, Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindLines(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindLines(Colossal.UI.Binding.IJsonWriter binder);
```

- `private BindPassengerTypes(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
private System.Void BindPassengerTypes(Colossal.UI.Binding.IJsonWriter writer);
```

- `private BindTypes(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UITransportItem[] items) : System.Void`  

```csharp
private System.Void BindTypes(Colossal.UI.Binding.IJsonWriter writer, Game.Prefabs.UITransportItem[] items);
```

- `private DeleteLine(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void DeleteLine(Unity.Entities.Entity entity);
```

- `private GetInitialSelectedType() : System.String`  

```csharp
private System.String GetInitialSelectedType();
```

- `public HideLine(Unity.Entities.Entity entity, System.Boolean showOthers) : System.Void`  

```csharp
public System.Void HideLine(Unity.Entities.Entity entity, System.Boolean showOthers);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public RequestUpdate() : System.Void`  

```csharp
public System.Void RequestUpdate();
```

- `public ResetLinesVisibility() : System.Void`  

```csharp
public System.Void ResetLinesVisibility();
```

- `private SelectLine(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void SelectLine(Unity.Entities.Entity entity);
```

- `private SetLineColor(Unity.Entities.Entity entity, UnityEngine.Color32 color) : System.Void`  

```csharp
private System.Void SetLineColor(Unity.Entities.Entity entity, UnityEngine.Color32 color);
```

- `private SetLineName(Unity.Entities.Entity entity, System.String name) : System.Void`  

```csharp
private System.Void SetLineName(Unity.Entities.Entity entity, System.String name);
```

- `private SetLineSchedule(Unity.Entities.Entity entity, System.Int32 schedule) : System.Void`  

```csharp
private System.Void SetLineSchedule(Unity.Entities.Entity entity, System.Int32 schedule);
```

- `public SetLineState(Unity.Entities.Entity entity, System.Boolean state) : System.Void`  

```csharp
public System.Void SetLineState(Unity.Entities.Entity entity, System.Boolean state);
```

- `private SetSelectedCargoType(System.String type) : System.Void`  

```csharp
private System.Void SetSelectedCargoType(System.String type);
```

- `private SetSelectedPassengerType(System.String type) : System.Void`  

```csharp
private System.Void SetSelectedPassengerType(System.String type);
```

- `public ShowLine(Unity.Entities.Entity entity, System.Boolean hideOthers) : System.Void`  

```csharp
public System.Void ShowLine(Unity.Entities.Entity entity, System.Boolean hideOthers);
```

- `public ToggleHighlight(Unity.Entities.Entity entity) : System.Void`  

```csharp
public System.Void ToggleHighlight(Unity.Entities.Entity entity);
```


