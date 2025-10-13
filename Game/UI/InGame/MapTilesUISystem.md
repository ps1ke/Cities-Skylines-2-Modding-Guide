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
[Preserve]
	public MapTilesUISystem()
	{
	}
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
private void BindResources(IJsonWriter binder)
	{
		binder.ArrayBegin(5u);
		binder.Write(GetResource(MapFeature.FertileLand));
		binder.Write(GetResource(MapFeature.Forest));
		binder.Write(GetResource(MapFeature.Oil));
		binder.Write(GetResource(MapFeature.Ore));
		binder.Write(GetResource(MapFeature.Fish));
		binder.ArrayEnd();
	}
```

- `private GetResource(Game.Areas.MapFeature feature) : Game.UI.InGame.MapTilesUISystem+UIMapTileResource`  

```csharp
private UIMapTileResource GetResource(MapFeature feature)
	{
		return feature switch
		{
			MapFeature.BuildableLand => new UIMapTileResource("BuildableLand", "Media/Game/Icons/MapTile.svg", m_MapTileSystem.GetFeatureAmount(MapFeature.BuildableLand), "area"), 
			MapFeature.FertileLand => new UIMapTileResource("FertileLand", "Media/Game/Icons/Fertility.svg", m_MapTileSystem.GetFeatureAmount(MapFeature.FertileLand), "area"), 
			MapFeature.Forest => new UIMapTileResource("Forest", "Media/Game/Icons/Forest.svg", m_MapTileSystem.GetFeatureAmount(MapFeature.Forest), "weight"), 
			MapFeature.Oil => new UIMapTileResource("Oil", "Media/Game/Icons/Oil.svg", m_MapTileSystem.GetFeatureAmount(MapFeature.Oil), "weight"), 
			MapFeature.Ore => new UIMapTileResource("Ore", "Media/Game/Icons/Coal.svg", m_MapTileSystem.GetFeatureAmount(MapFeature.Ore), "weight"), 
			MapFeature.Fish => new UIMapTileResource("Fish", "Media/Game/Resources/Fish.svg", m_MapTileSystem.GetFeatureAmount(MapFeature.Fish), "weight"), 
			_ => new UIMapTileResource("Water", "Media/Game/Icons/Water.svg", m_MapTileSystem.GetFeatureAmount(MapFeature.GroundWater), "volume"), 
		};
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_MapTileSystem = base.World.GetOrCreateSystemManaged<MapTilePurchaseSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_GameScreenUISystem = base.World.GetOrCreateSystemManaged<GameScreenUISystem>();
		AddBinding(m_MapTilesPanelVisibleBinding = new GetterValueBinding<bool>("mapTiles", "mapTilePanelVisible", () => mapTileViewActive && !m_CityConfigurationSystem.unlockMapTiles));
		AddBinding(m_MapTilesViewActiveBinding = new GetterValueBinding<bool>("mapTiles", "mapTileViewActive", () => mapTileViewActive));
		AddBinding(m_BuildableLandBinding = new ValueBinding<UIMapTileResource>("mapTiles", "buildableLand", GetResource(MapFeature.BuildableLand), new ValueWriter<UIMapTileResource>()));
		AddBinding(m_WaterBinding = new ValueBinding<UIMapTileResource>("mapTiles", "water", GetResource(MapFeature.GroundWater), new ValueWriter<UIMapTileResource>()));
		AddBinding(m_PurchasePriceBinding = new GetterValueBinding<int>("mapTiles", "purchasePrice", () => m_MapTileSystem.cost));
		AddBinding(m_PurchaseUpkeepBinding = new GetterValueBinding<int>("mapTiles", "purchaseUpkeep", () => m_MapTileSystem.upkeep));
		AddBinding(m_PurchaseFlagsBinding = new GetterValueBinding<int>("mapTiles", "purchaseFlags", () => (int)m_MapTileSystem.status));
		AddBinding(m_ExpansionPermitsBinding = new GetterValueBinding<int>("mapTiles", "expansionPermits", () => m_MapTileSystem.GetAvailableTiles()));
		AddBinding(m_ExpansionPermitCostBinding = new GetterValueBinding<int>("mapTiles", "expansionPermitCost", () => m_MapTileSystem.GetSelectedTileCount()));
		AddBinding(m_ResourcesBinding = new RawValueBinding("mapTiles", "resources", BindResources));
		AddBinding(new TriggerBinding<bool>("mapTiles", "setMapTileViewActive", SetMapTileViewActive));
		AddBinding(new TriggerBinding("mapTiles", "purchaseMapTiles", PurchaseMapTiles));
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_IsLastTimeZoomOut = false;
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		mapTileViewActive = false;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_MapTilesViewActiveBinding.Update();
		m_MapTilesPanelVisibleBinding.Update();
		m_ExpansionPermitsBinding.Update();
		if (!mapTileViewActive)
		{
			return;
		}
		m_MapTileSystem.Update();
		if (m_MapTileSystem.selecting)
		{
			m_PurchaseFlagsBinding.Update();
			int selectedTileCount = m_MapTileSystem.GetSelectedTileCount();
			if (m_LastSelected != selectedTileCount)
			{
				m_LastSelected = selectedTileCount;
				m_PurchasePriceBinding.Update();
				m_PurchaseUpkeepBinding.Update();
				m_ExpansionPermitCostBinding.Update();
				m_ResourcesBinding.Update();
				m_BuildableLandBinding.Update(GetResource(MapFeature.BuildableLand));
				m_WaterBinding.Update(GetResource(MapFeature.GroundWater));
			}
		}
	}
```

- `private PurchaseMapTiles() : System.Void`  

```csharp
private void PurchaseMapTiles()
	{
		m_MapTileSystem.PurchaseSelection();
	}
```

- `private SetMapTileViewActive(System.Boolean enabled) : System.Void`  

```csharp
private void SetMapTileViewActive(bool enabled)
	{
		if (enabled && m_GameScreenUISystem.activeScreen != GameScreenUISystem.GameScreen.Main)
		{
			m_GameScreenUISystem.SetScreen(GameScreenUISystem.GameScreen.Main);
		}
		mapTileViewActive = enabled;
		m_MapTileSystem.selecting = enabled && !m_CityConfigurationSystem.unlockMapTiles;
		if (m_IsLastTimeZoomOut != enabled && !GameManager.instance.isGameLoading)
		{
			Entity clipEntity = (enabled ? m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_CameraZoomInSound : m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_CameraZoomOutSound);
			m_AudioManager.PlayUISound(clipEntity);
		}
		m_IsLastTimeZoomOut = enabled;
	}
```


## Nested types

- `Game.UI.InGame.MapTilesUISystem+UIMapTileResource`  
- `Game.UI.InGame.MapTilesUISystem+<>c`  

