# Game.UI.InGame.UpgradeMenuUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpgradeMenuUISystem : Game.UI.UISystemBase
{
    private Unity.Entities.EntityQuery m_UnlockedUpgradeQuery;
    private Unity.Entities.EntityQuery m_CreatedExtensionQuery;
    private Unity.Entities.EntityQuery m_DeletedExtensionQuery;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.RouteToolSystem m_RouteToolSystem;
    private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradeDetailsBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedUpgradeBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_UpgradingBinding;
    private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Upgrades;
    private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Modules;
    private System.Boolean m_UniqueAssetStatusChanged;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public System.Boolean upgrading { get; }

    public UpgradeMenuUISystem();

    private System.Void BindUpgradeDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgrade);
    private System.Void BindUpgrades(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgradable);
    private System.ValueTuple<System.Boolean, System.Boolean> CheckExtensionBuiltStatus(Unity.Entities.Entity upgradableEntity, Unity.Entities.Entity upgradeEntity);
    private System.Void ClearUpgradeSelection();
    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    private System.Void OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    private System.Void OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed);
    protected virtual System.Void OnUpdate();
    private System.Void SelectUpgrade(Unity.Entities.Entity upgradable, Unity.Entities.Entity upgrade);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UnlockedUpgradeQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedUpgradeQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedExtensionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedExtensionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedExtensionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedExtensionQuery;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  

```csharp
private Game.Tools.RouteToolSystem m_RouteToolSystem;
```

- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  

```csharp
private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem`  

```csharp
private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem`  

```csharp
private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradesBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradeDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradeDetailsBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedUpgradeBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedUpgradeBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_UpgradingBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_UpgradingBinding;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Upgrades`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Upgrades;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Modules`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Modules;
```

- `private System.Boolean m_UniqueAssetStatusChanged`  

```csharp
private System.Boolean m_UniqueAssetStatusChanged;
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

- `public System.Boolean upgrading { get }`  

```csharp
public System.Boolean upgrading { get; }
```


## Constructors

- `public UpgradeMenuUISystem()`  

```csharp
public UpgradeMenuUISystem();
```


## Methods

- `private BindUpgradeDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgrade) : System.Void`  

```csharp
private System.Void BindUpgradeDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgrade);
```

- `private BindUpgrades(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgradable) : System.Void`  

```csharp
private System.Void BindUpgrades(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgradable);
```

- `private CheckExtensionBuiltStatus(Unity.Entities.Entity upgradableEntity, Unity.Entities.Entity upgradeEntity) : System.ValueTuple<System.Boolean, System.Boolean>`  

```csharp
private System.ValueTuple<System.Boolean, System.Boolean> CheckExtensionBuiltStatus(Unity.Entities.Entity upgradableEntity, Unity.Entities.Entity upgradeEntity);
```

- `private ClearUpgradeSelection() : System.Void`  

```csharp
private System.Void ClearUpgradeSelection();
```

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private System.Void OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position);
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
protected virtual System.Void OnStartRunning();
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
```

- `private OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed) : System.Void`  

```csharp
private System.Void OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private SelectUpgrade(Unity.Entities.Entity upgradable, Unity.Entities.Entity upgrade) : System.Void`  

```csharp
private System.Void SelectUpgrade(Unity.Entities.Entity upgradable, Unity.Entities.Entity upgrade);
```


## Nested types

- `Game.UI.InGame.UpgradeMenuUISystem+SortableEntity`  

