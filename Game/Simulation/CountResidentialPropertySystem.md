# Game.Simulation.CountResidentialPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountResidentialPropertySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Colossal.Collections.NativeAccumulator<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData> m_ResidentialPropertyData;
    private Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData m_LastResidentialPropertyData;
    private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
    private Game.Simulation.CountResidentialPropertySystem+TypeHandle __TypeHandle;

    public Unity.Mathematics.int3 FreeProperties { get; }
    public Unity.Mathematics.int3 TotalProperties { get; }
    public System.Int32 FreeShelterCapacity { get; }
    public System.Int32 TotalShelterCapacity { get; }

    public CountResidentialPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData GetResidentialPropertyData();
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData> m_ResidentialPropertyData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData> m_ResidentialPropertyData;
```

- `private Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData m_LastResidentialPropertyData`  

```csharp
private Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData m_LastResidentialPropertyData;
```

- `private Unity.Entities.EntityQuery m_ResidentialPropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentialPropertyQuery;
```

- `private Game.Simulation.CountResidentialPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountResidentialPropertySystem+TypeHandle __TypeHandle;
```


## Properties

- `public Unity.Mathematics.int3 FreeProperties { get }`  

```csharp
public Unity.Mathematics.int3 FreeProperties { get; }
```

- `public Unity.Mathematics.int3 TotalProperties { get }`  

```csharp
public Unity.Mathematics.int3 TotalProperties { get; }
```

- `public System.Int32 FreeShelterCapacity { get }`  

```csharp
public System.Int32 FreeShelterCapacity { get; }
```

- `public System.Int32 TotalShelterCapacity { get }`  

```csharp
public System.Int32 TotalShelterCapacity { get; }
```


## Constructors

- `public CountResidentialPropertySystem()`  

```csharp
[Preserve]
	public CountResidentialPropertySystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetResidentialPropertyData() : Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData`  

```csharp
public ResidentialPropertyData GetResidentialPropertyData()
	{
		return m_LastResidentialPropertyData;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResidentialPropertyQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Building>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Abandoned>(),
				ComponentType.ReadOnly<Game.Buildings.Park>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Condemned>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<ResidentialProperty>() },
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Condemned>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ResidentialPropertyData = new NativeAccumulator<ResidentialPropertyData>(Allocator.Persistent);
		RequireForUpdate(m_ResidentialPropertyQuery);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_ResidentialPropertyData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LastResidentialPropertyData = m_ResidentialPropertyData.GetResult();
		m_ResidentialPropertyData.Clear();
		CountResidentialPropertyJob jobData = new CountResidentialPropertyJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZonePropertiesDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZonePropertiesData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResidentialPropertyData = m_ResidentialPropertyData.AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ResidentialPropertyQuery, base.Dependency);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LastResidentialPropertyData = default(ResidentialPropertyData);
		m_ResidentialPropertyData.Clear();
	}
```


## Nested types

- `Game.Simulation.CountResidentialPropertySystem+ResidentialPropertyData`  
- `Game.Simulation.CountResidentialPropertySystem+CountResidentialPropertyJob`  
- `Game.Simulation.CountResidentialPropertySystem+TypeHandle`  

