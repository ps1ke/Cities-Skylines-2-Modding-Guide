# Game.UI.InGame.MapTilesUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapTilesUISystem : Game.UI.UISystemBase
{
    private Game.Simulation.MapTilePurchaseSystem m_MapTileSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesPanelVisibleBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesViewActiveBinding;
    private Colossal.UI.Binding.RawValueBinding m_ResourcesBinding;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_BuildableLandBinding;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_WaterBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchasePriceBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseUpkeepBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseFlagsBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitsBinding;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitCostBinding;
    private System.Int32 m_LastSelected;
    private System.Boolean m_IsLastTimeZoomOut;
    private static System.Boolean <mapTileViewActive>k__BackingField;
    private static const System.String kGroup;

    public static System.Boolean mapTileViewActive { get; private set; }

    public MapTilesUISystem();

    private System.Boolean <OnCreate>b__22_0();
    private System.Int32 <OnCreate>b__22_2();
    private System.Int32 <OnCreate>b__22_3();
    private System.Int32 <OnCreate>b__22_4();
    private System.Int32 <OnCreate>b__22_5();
    private System.Int32 <OnCreate>b__22_6();
    private System.Void BindResources(Colossal.UI.Binding.IJsonWriter binder);
    private Game.UI.InGame.MapTilesUISystem+UIMapTileResource GetResource(Game.Areas.MapFeature feature);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    private System.Void PurchaseMapTiles();
    private System.Void SetMapTileViewActive(System.Boolean enabled);
}
```


## Fields

- `private Game.Simulation.MapTilePurchaseSystem m_MapTileSystem`  

```csharp
private Game.Simulation.MapTilePurchaseSystem m_MapTileSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  

```csharp
private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesPanelVisibleBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesPanelVisibleBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesViewActiveBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Boolean> m_MapTilesViewActiveBinding;
```

- `private Colossal.UI.Binding.RawValueBinding m_ResourcesBinding`  

```csharp
private Colossal.UI.Binding.RawValueBinding m_ResourcesBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_BuildableLandBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_BuildableLandBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_WaterBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.MapTilesUISystem+UIMapTileResource> m_WaterBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchasePriceBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchasePriceBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseUpkeepBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseUpkeepBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseFlagsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_PurchaseFlagsBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitsBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitCostBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_ExpansionPermitCostBinding;
```

- `private System.Int32 m_LastSelected`  

```csharp
private System.Int32 m_LastSelected;
```

- `private System.Boolean m_IsLastTimeZoomOut`  

```csharp
private System.Boolean m_IsLastTimeZoomOut;
```

- `private static System.Boolean <mapTileViewActive>k__BackingField`  

```csharp
private static System.Boolean <mapTileViewActive>k__BackingField;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public static System.Boolean mapTileViewActive { get; private set }`  

```csharp
public static System.Boolean mapTileViewActive { get; private set; }
```


## Constructors

- `public MapTilesUISystem()`  

```csharp
public MapTilesUISystem();
```


## Methods

- `private <OnCreate>b__22_0() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__22_0();
```

- `private <OnCreate>b__22_2() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__22_2();
```

- `private <OnCreate>b__22_3() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__22_3();
```

- `private <OnCreate>b__22_4() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__22_4();
```

- `private <OnCreate>b__22_5() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__22_5();
```

- `private <OnCreate>b__22_6() : System.Int32`  

```csharp
private System.Int32 <OnCreate>b__22_6();
```

- `private BindResources(Colossal.UI.Binding.IJsonWriter binder) : System.Void`  

```csharp
private System.Void BindResources(Colossal.UI.Binding.IJsonWriter binder);
```

- `private GetResource(Game.Areas.MapFeature feature) : Game.UI.InGame.MapTilesUISystem+UIMapTileResource`  

```csharp
private Game.UI.InGame.MapTilesUISystem+UIMapTileResource GetResource(Game.Areas.MapFeature feature);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private PurchaseMapTiles() : System.Void`  

```csharp
private System.Void PurchaseMapTiles();
```

- `private SetMapTileViewActive(System.Boolean enabled) : System.Void`  

```csharp
private System.Void SetMapTileViewActive(System.Boolean enabled);
```


## Nested types

- `Game.UI.InGame.MapTilesUISystem+UIMapTileResource`  
- `Game.UI.InGame.MapTilesUISystem+<>c`  

