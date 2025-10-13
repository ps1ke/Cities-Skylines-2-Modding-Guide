# Game.UI.Editor.DiversityPanelSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Editor.EditorPanelSystemBase`  
**Implements:** `Game.UI.Editor.IEditorPanel`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DiversityPanelSystem : Game.UI.Editor.EditorPanelSystemBase, Game.UI.Editor.IEditorPanel
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.DiversitySystem m_DiversitySystem;
    private Unity.Entities.EntityQuery m_AtmosphereQuery;
    private Unity.Entities.EntityQuery m_BiomeQuery;
    private Game.Prefabs.AtmospherePrefab m_Atmosphere;
    private Game.Prefabs.BiomePrefab m_Biome;

    public DiversityPanelSystem();

    private Game.Prefabs.PrefabBase <OnCreate>b__6_0();
    private Game.Prefabs.PrefabBase <OnCreate>b__6_1();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnStartRunning();
    private System.Void SetAtmosphere(Game.Prefabs.PrefabBase prefab);
    private System.Void SetBiome(Game.Prefabs.PrefabBase prefab);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.DiversitySystem m_DiversitySystem`  

```csharp
private Game.Simulation.DiversitySystem m_DiversitySystem;
```

- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  

```csharp
private Unity.Entities.EntityQuery m_AtmosphereQuery;
```

- `private Unity.Entities.EntityQuery m_BiomeQuery`  

```csharp
private Unity.Entities.EntityQuery m_BiomeQuery;
```

- `private Game.Prefabs.AtmospherePrefab m_Atmosphere`  

```csharp
private Game.Prefabs.AtmospherePrefab m_Atmosphere;
```

- `private Game.Prefabs.BiomePrefab m_Biome`  

```csharp
private Game.Prefabs.BiomePrefab m_Biome;
```


## Constructors

- `public DiversityPanelSystem()`  

```csharp
[Preserve]
	public DiversityPanelSystem()
	{
	}
```


## Methods

- `private <OnCreate>b__6_0() : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase <OnCreate>b__6_0();
```

- `private <OnCreate>b__6_1() : Game.Prefabs.PrefabBase`  

```csharp
private Game.Prefabs.PrefabBase <OnCreate>b__6_1();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_DiversitySystem = base.World.GetOrCreateSystemManaged<DiversitySystem>();
		m_AtmosphereQuery = GetEntityQuery(ComponentType.ReadOnly<AtmosphereData>());
		m_BiomeQuery = GetEntityQuery(ComponentType.ReadOnly<BiomeData>());
		title = LocalizedString.Value("Diversity");
		children = new IWidget[1] { Scrollable.WithChildren(new IWidget[1]
		{
			new EditorSection
			{
				displayName = "Diversity Settings",
				expanded = true,
				children = new IWidget[2]
				{
					new PopupValueField<PrefabBase>
					{
						displayName = "Atmosphere",
						accessor = new DelegateAccessor<PrefabBase>(() => m_Atmosphere, SetAtmosphere),
						popup = new PrefabPickerPopup(typeof(AtmospherePrefab))
					},
					new PopupValueField<PrefabBase>
					{
						displayName = "Biome",
						accessor = new DelegateAccessor<PrefabBase>(() => m_Biome, SetBiome),
						popup = new PrefabPickerPopup(typeof(BiomePrefab))
					}
				}
			}
		}) };
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		AtmosphereData singleton = m_AtmosphereQuery.GetSingleton<AtmosphereData>();
		m_PrefabSystem.TryGetPrefab<AtmospherePrefab>(singleton.m_AtmospherePrefab, out m_Atmosphere);
		BiomeData singleton2 = m_BiomeQuery.GetSingleton<BiomeData>();
		m_PrefabSystem.TryGetPrefab<BiomePrefab>(singleton2.m_BiomePrefab, out m_Biome);
	}
```

- `private SetAtmosphere(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private void SetAtmosphere(PrefabBase prefab)
	{
		m_Atmosphere = (AtmospherePrefab)prefab;
		Entity entity = m_PrefabSystem.GetEntity(m_Atmosphere);
		m_DiversitySystem.ApplyAtmospherePreset(entity);
	}
```

- `private SetBiome(Game.Prefabs.PrefabBase prefab) : System.Void`  

```csharp
private void SetBiome(PrefabBase prefab)
	{
		m_Biome = (BiomePrefab)prefab;
		Entity entity = m_PrefabSystem.GetEntity(m_Biome);
		m_DiversitySystem.ApplyBiomePreset(entity);
	}
```


