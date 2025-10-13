# Game.Simulation.GameModeNaturalResourcesAdjustSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GameModeNaturalResourcesAdjustSystem : Game.GameSystemBase
{
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    public static readonly System.Int32 kUpdatesPerDay;

    public GameModeNaturalResourcesAdjustSystem();

    private System.Void BoostStartGameNaturalResources(System.Single boostMultiplier);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public GameModeNaturalResourcesAdjustSystem()`  

```csharp
[Preserve]
	public GameModeNaturalResourcesAdjustSystem()
	{
	}
```


## Methods

- `private BoostStartGameNaturalResources(System.Single boostMultiplier) : System.Void`  

```csharp
private void BoostStartGameNaturalResources(float boostMultiplier)
	{
		JobHandle dependencies;
		CellMapData<NaturalResourceCell> data = m_NaturalResourceSystem.GetData(readOnly: false, out dependencies);
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(new BoostInitialNaturalResourcesJob
		{
			m_CellData = data,
			m_BoostMultiplier = boostMultiplier
		}, data.m_TextureSize.x * data.m_TextureSize.y, 64, dependencies);
		m_NaturalResourceSystem.AddWriter(jobHandle);
		JobHandle dependencies2;
		CellMapData<GroundWater> data2 = m_GroundWaterSystem.GetData(readOnly: false, out dependencies2);
		JobHandle jobHandle2 = IJobParallelForExtensions.Schedule(new BoostInitialGroundWaterJob
		{
			m_CellData = data2,
			m_BoostMultiplier = boostMultiplier
		}, data2.m_TextureSize.x * data2.m_TextureSize.y, 64, dependencies2);
		m_GroundWaterSystem.AddWriter(jobHandle2);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_GameModeSettingQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		RequireForUpdate(m_GameModeSettingQuery);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		if (m_GameModeSettingQuery.IsEmptyIgnoreFilter)
		{
			base.Enabled = false;
			return;
		}
		ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
		if (singleton.m_Enable && singleton.m_EnableAdjustNaturalResources)
		{
			if (serializationContext.purpose == Purpose.NewGame)
			{
				BoostStartGameNaturalResources(singleton.m_InitialNaturalResourceBoostMultiplier);
			}
			base.Enabled = true;
		}
		else
		{
			base.Enabled = false;
		}
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_GameModeSettingQuery.IsEmptyIgnoreFilter)
		{
			ModeSettingData singleton = m_GameModeSettingQuery.GetSingleton<ModeSettingData>();
			if (singleton.m_Enable && singleton.m_EnableAdjustNaturalResources)
			{
				JobHandle dependencies;
				CellMapData<NaturalResourceCell> data = m_NaturalResourceSystem.GetData(readOnly: false, out dependencies);
				JobHandle jobHandle = IJobParallelForExtensions.Schedule(new RefillNaturalResourcesJob
				{
					m_CellData = data,
					m_GlobalData = singleton
				}, data.m_TextureSize.x * data.m_TextureSize.y, 64, dependencies);
				m_NaturalResourceSystem.AddWriter(jobHandle);
			}
		}
	}
```


## Nested types

- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+BoostInitialNaturalResourcesJob`  
- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+BoostInitialGroundWaterJob`  
- `Game.Simulation.GameModeNaturalResourcesAdjustSystem+RefillNaturalResourcesJob`  

