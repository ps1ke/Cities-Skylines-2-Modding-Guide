# Game.UI.InGame.ActionsSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ActionsSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
    private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem;
    private Game.Tools.TrafficRoutesSystem m_TrafficRoutesSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_RouteConfigQuery;
    private Game.Prefabs.PolicyPrefab m_RouteOutOfServicePolicy;
    private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
    private Game.Prefabs.PolicyPrefab m_EmptyingPolicy;
    private Game.Prefabs.AreaPrefab m_LotPrefab;
    private System.Boolean m_EditingLot;
    private UnityEngine.Color32[] m_TrafficRouteColors;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MovingBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EditingLotBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_TrafficRoutesVisibleBinding;
    private Colossal.UI.Binding.ValueBinding<UnityEngine.Color32[]> m_TrafficRouteColorsBinding;
    private Colossal.UI.Binding.RawValueBinding m_MoveableObjectName;
    private System.Boolean <focusable>k__BackingField;
    private System.Boolean <focusing>k__BackingField;
    private System.Boolean <following>k__BackingField;
    private System.Boolean <followable>k__BackingField;
    private System.Boolean <moveable>k__BackingField;
    private System.Boolean <deletable>k__BackingField;
    private System.Boolean <disabled>k__BackingField;
    private System.Boolean <disableable>k__BackingField;
    private System.Boolean <hasTutorial>k__BackingField;
    private System.Boolean <emptying>k__BackingField;
    private System.Boolean <emptiable>k__BackingField;
    private System.Boolean <hasLotTool>k__BackingField;
    private System.Boolean <hasTrafficRoutes>k__BackingField;

    protected System.String group { protected get; }
    public System.Boolean editingLot { get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForOutsideConnections { protected get; }
    protected System.Boolean displayForUnderConstruction { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private System.Boolean focusable { private get; private set; }
    private System.Boolean focusing { private get; private set; }
    private System.Boolean following { private get; private set; }
    private System.Boolean followable { private get; private set; }
    private System.Boolean moveable { private get; private set; }
    private System.Boolean deletable { private get; private set; }
    private System.Boolean disabled { private get; private set; }
    private System.Boolean disableable { private get; private set; }
    private System.Boolean hasTutorial { private get; private set; }
    private System.Boolean emptying { private get; private set; }
    private System.Boolean emptiable { private get; private set; }
    private System.Boolean hasLotTool { private get; private set; }
    private System.Boolean hasTrafficRoutes { private get; private set; }

    public ActionsSection();

    private System.Void BindObjectName(Colossal.UI.Binding.IJsonWriter binder);
    protected virtual System.Void OnCreate();
    private System.Void OnDelete();
    private System.Void OnFocus();
    private System.Void OnFollow();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnToggle();
    private System.Void OnToggleEmptying();
    private System.Void OnToggleLotTool();
    private System.Void OnToggleMove();
    private System.Void OnToggleTrafficRoutes();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem`  

```csharp
private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
```

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Game.Triggers.LifePathEventSystem m_LifePathEventSystem`  

```csharp
private Game.Triggers.LifePathEventSystem m_LifePathEventSystem;
```

- `private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem`  

```csharp
private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem;
```

- `private Game.Tools.TrafficRoutesSystem m_TrafficRoutesSystem`  

```csharp
private Game.Tools.TrafficRoutesSystem m_TrafficRoutesSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_RouteConfigQuery;
```

- `private Game.Prefabs.PolicyPrefab m_RouteOutOfServicePolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_RouteOutOfServicePolicy;
```

- `private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
```

- `private Game.Prefabs.PolicyPrefab m_EmptyingPolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_EmptyingPolicy;
```

- `private Game.Prefabs.AreaPrefab m_LotPrefab`  

```csharp
private Game.Prefabs.AreaPrefab m_LotPrefab;
```

- `private System.Boolean m_EditingLot`  

```csharp
private System.Boolean m_EditingLot;
```

- `private UnityEngine.Color32[] m_TrafficRouteColors`  

```csharp
private UnityEngine.Color32[] m_TrafficRouteColors;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MovingBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MovingBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EditingLotBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_EditingLotBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_TrafficRoutesVisibleBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_TrafficRoutesVisibleBinding;
```

- `private Colossal.UI.Binding.ValueBinding<UnityEngine.Color32[]> m_TrafficRouteColorsBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<UnityEngine.Color32[]> m_TrafficRouteColorsBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_MoveableObjectName`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_MoveableObjectName;
```

- `private System.Boolean <focusable>k__BackingField`  

```csharp
private System.Boolean <focusable>k__BackingField;
```

- `private System.Boolean <focusing>k__BackingField`  

```csharp
private System.Boolean <focusing>k__BackingField;
```

- `private System.Boolean <following>k__BackingField`  

```csharp
private System.Boolean <following>k__BackingField;
```

- `private System.Boolean <followable>k__BackingField`  

```csharp
private System.Boolean <followable>k__BackingField;
```

- `private System.Boolean <moveable>k__BackingField`  

```csharp
private System.Boolean <moveable>k__BackingField;
```

- `private System.Boolean <deletable>k__BackingField`  

```csharp
private System.Boolean <deletable>k__BackingField;
```

- `private System.Boolean <disabled>k__BackingField`  

```csharp
private System.Boolean <disabled>k__BackingField;
```

- `private System.Boolean <disableable>k__BackingField`  

```csharp
private System.Boolean <disableable>k__BackingField;
```

- `private System.Boolean <hasTutorial>k__BackingField`  

```csharp
private System.Boolean <hasTutorial>k__BackingField;
```

- `private System.Boolean <emptying>k__BackingField`  

```csharp
private System.Boolean <emptying>k__BackingField;
```

- `private System.Boolean <emptiable>k__BackingField`  

```csharp
private System.Boolean <emptiable>k__BackingField;
```

- `private System.Boolean <hasLotTool>k__BackingField`  

```csharp
private System.Boolean <hasLotTool>k__BackingField;
```

- `private System.Boolean <hasTrafficRoutes>k__BackingField`  

```csharp
private System.Boolean <hasTrafficRoutes>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `public System.Boolean editingLot { get }`  

```csharp
public System.Boolean editingLot { get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForOutsideConnections { protected get }`  

```csharp
protected System.Boolean displayForOutsideConnections { protected get; }
```

- `protected System.Boolean displayForUnderConstruction { protected get }`  

```csharp
protected System.Boolean displayForUnderConstruction { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private System.Boolean focusable { private get; private set }`  

```csharp
private System.Boolean focusable { private get; private set; }
```

- `private System.Boolean focusing { private get; private set }`  

```csharp
private System.Boolean focusing { private get; private set; }
```

- `private System.Boolean following { private get; private set }`  

```csharp
private System.Boolean following { private get; private set; }
```

- `private System.Boolean followable { private get; private set }`  

```csharp
private System.Boolean followable { private get; private set; }
```

- `private System.Boolean moveable { private get; private set }`  

```csharp
private System.Boolean moveable { private get; private set; }
```

- `private System.Boolean deletable { private get; private set }`  

```csharp
private System.Boolean deletable { private get; private set; }
```

- `private System.Boolean disabled { private get; private set }`  

```csharp
private System.Boolean disabled { private get; private set; }
```

- `private System.Boolean disableable { private get; private set }`  

```csharp
private System.Boolean disableable { private get; private set; }
```

- `private System.Boolean hasTutorial { private get; private set }`  

```csharp
private System.Boolean hasTutorial { private get; private set; }
```

- `private System.Boolean emptying { private get; private set }`  

```csharp
private System.Boolean emptying { private get; private set; }
```

- `private System.Boolean emptiable { private get; private set }`  

```csharp
private System.Boolean emptiable { private get; private set; }
```

- `private System.Boolean hasLotTool { private get; private set }`  

```csharp
private System.Boolean hasLotTool { private get; private set; }
```

- `private System.Boolean hasTrafficRoutes { private get; private set }`  

```csharp
private System.Boolean hasTrafficRoutes { private get; private set; }
```


## Constructors

- `public ActionsSection()`  

```csharp
public ActionsSection();
```


## Methods

- `private BindObjectName(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindObjectName(Colossal.UI.Binding.IJsonWriter binder);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `private OnDelete() : System.Void`  

```csharp
private System.Void OnDelete();
```

- `private OnFocus() : System.Void`  

```csharp
private System.Void OnFocus();
```

- `private OnFollow() : System.Void`  

```csharp
private System.Void OnFollow();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected virtual System.Void OnProcess();
```

- `private OnToggle() : System.Void`  

```csharp
private System.Void OnToggle();
```

- `private OnToggleEmptying() : System.Void`  

```csharp
private System.Void OnToggleEmptying();
```

- `private OnToggleLotTool() : System.Void`  

```csharp
private System.Void OnToggleLotTool();
```

- `private OnToggleMove() : System.Void`  

```csharp
private System.Void OnToggleMove();
```

- `private OnToggleTrafficRoutes() : System.Void`  

```csharp
private System.Void OnToggleTrafficRoutes();
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
```

- `protected virtual Reset() : System.Void`  

```csharp
protected virtual System.Void Reset();
```


