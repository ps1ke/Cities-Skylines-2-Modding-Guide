# Game.Serialization.ClearSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

## Code

```csharp
public class ClearSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_ClearQuery;

    public ClearSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ClearQuery`  

```csharp
private Unity.Entities.EntityQuery m_ClearQuery;
```


## Constructors

- `public ClearSystem()`  

```csharp
[Preserve]
	public ClearSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ClearQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[21]
			{
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<LoadedIndex>(),
				ComponentType.ReadOnly<ElectricityFlowNode>(),
				ComponentType.ReadOnly<ElectricityFlowEdge>(),
				ComponentType.ReadOnly<WaterPipeNode>(),
				ComponentType.ReadOnly<WaterPipeEdge>(),
				ComponentType.ReadOnly<ServiceRequest>(),
				ComponentType.ReadOnly<Game.Simulation.WaterSourceData>(),
				ComponentType.ReadOnly<Game.City.City>(),
				ComponentType.ReadOnly<SchoolSeeker>(),
				ComponentType.ReadOnly<JobSeeker>(),
				ComponentType.ReadOnly<CityStatistic>(),
				ComponentType.ReadOnly<ServiceBudgetData>(),
				ComponentType.ReadOnly<FloodCounterData>(),
				ComponentType.ReadOnly<CoordinatedMeeting>(),
				ComponentType.ReadOnly<LookingForPartner>(),
				ComponentType.ReadOnly<EffectInstance>(),
				ComponentType.ReadOnly<AtmosphereData>(),
				ComponentType.ReadOnly<BiomeData>(),
				ComponentType.ReadOnly<CreationDefinition>(),
				ComponentType.ReadOnly<TimeData>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<NetCompositionData>(),
				ComponentType.ReadOnly<PrefabData>()
			}
		});
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.EntityManager.DestroyEntity(m_ClearQuery);
	}
```


