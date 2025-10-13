# Game.Simulation.GameModeWealthSupportSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GameModeWealthSupportSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_GameModeSettingQuery;
    private Unity.Entities.EntityQuery m_HouseholdGroup;
    private System.Int32 m_MinimumWealth;
    public static readonly System.Int32 kUpdatesPerDay;

    public GameModeWealthSupportSystem();

    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_GameModeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_GameModeSettingQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdGroup;
```

- `private System.Int32 m_MinimumWealth`  

```csharp
private System.Int32 m_MinimumWealth;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public GameModeWealthSupportSystem()`  

```csharp
[Preserve]
	public GameModeWealthSupportSystem()
	{
	}
```


## Methods

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_GameModeSettingQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<ModeSettingData>());
		m_HouseholdGroup = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadOnly<Resources>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_GameModeSettingQuery);
		RequireForUpdate(m_HouseholdGroup);
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
		if (singleton.m_Enable && singleton.m_SupportPoorCitizens)
		{
			m_MinimumWealth = singleton.m_MinimumWealth;
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		SupportWageJob jobData = new SupportWageJob
		{
			m_UpdateFrameIndex = updateFrame,
			m_MinimumWealth = m_MinimumWealth,
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_HouseholdType = GetComponentTypeHandle<Household>(isReadOnly: true),
			m_ResourcesType = GetBufferTypeHandle<Resources>()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_HouseholdGroup, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.GameModeWealthSupportSystem+SupportWageJob`  

