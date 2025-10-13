# Game.Simulation.CountWorkplacesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountWorkplacesSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Unity.Entities.EntityQuery m_WorkplaceQuery;
    private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_FreeWorkplaces;
    private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_TotalWorkplaces;
    public Game.Companies.Workplaces m_LastFreeWorkplaces;
    public Game.Companies.Workplaces m_LastTotalWorkplaces;
    private Game.Simulation.CountWorkplacesSystem+TypeHandle __TypeHandle;

    public CountWorkplacesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    public Game.Companies.Workplaces GetFreeWorkplaces();
    public Game.Companies.Workplaces GetTotalWorkplaces();
    public Game.Companies.Workplaces GetUnemployedWorkspaceByLevel();
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

- `private Unity.Entities.EntityQuery m_WorkplaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkplaceQuery;
```

- `private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_FreeWorkplaces`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_FreeWorkplaces;
```

- `private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_TotalWorkplaces`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Companies.Workplaces> m_TotalWorkplaces;
```

- `public Game.Companies.Workplaces m_LastFreeWorkplaces`  

```csharp
public Game.Companies.Workplaces m_LastFreeWorkplaces;
```

- `public Game.Companies.Workplaces m_LastTotalWorkplaces`  

```csharp
public Game.Companies.Workplaces m_LastTotalWorkplaces;
```

- `private Game.Simulation.CountWorkplacesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountWorkplacesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CountWorkplacesSystem()`  

```csharp
[Preserve]
	public CountWorkplacesSystem()
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

- `public GetFreeWorkplaces() : Game.Companies.Workplaces`  

```csharp
public Workplaces GetFreeWorkplaces()
	{
		return m_LastFreeWorkplaces;
	}
```

- `public GetTotalWorkplaces() : Game.Companies.Workplaces`  

```csharp
public Workplaces GetTotalWorkplaces()
	{
		return m_LastTotalWorkplaces;
	}
```

- `public GetUnemployedWorkspaceByLevel() : Game.Companies.Workplaces`  

```csharp
public Workplaces GetUnemployedWorkspaceByLevel()
	{
		Workplaces result = default(Workplaces);
		int num = 0;
		for (int i = 0; i < 5; i++)
		{
			num = (result[i] = num + m_LastFreeWorkplaces[i]);
		}
		return result;
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
		m_WorkplaceQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<WorkProvider>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<PropertyRenter>(),
				ComponentType.ReadOnly<Building>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_FreeWorkplaces = new NativeAccumulator<Workplaces>(Allocator.Persistent);
		m_TotalWorkplaces = new NativeAccumulator<Workplaces>(Allocator.Persistent);
		RequireForUpdate(m_WorkplaceQuery);
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
		m_FreeWorkplaces.Dispose();
		m_TotalWorkplaces.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LastFreeWorkplaces = m_FreeWorkplaces.GetResult();
		m_LastTotalWorkplaces = m_TotalWorkplaces.GetResult();
		m_FreeWorkplaces.Clear();
		m_TotalWorkplaces.Clear();
		CountWorkplacesJob jobData = new CountWorkplacesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_FreeWorkplacesType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_FreeWorkplaces_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkProviderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkplaceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FreeWorkplaces = m_FreeWorkplaces.AsParallelWriter(),
			m_TotalWorkplaces = m_TotalWorkplaces.AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_WorkplaceQuery, base.Dependency);
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
		m_LastFreeWorkplaces = default(Workplaces);
		m_LastTotalWorkplaces = default(Workplaces);
		m_FreeWorkplaces.Clear();
		m_TotalWorkplaces.Clear();
	}
```


## Nested types

- `Game.Simulation.CountWorkplacesSystem+CountWorkplacesJob`  
- `Game.Simulation.CountWorkplacesSystem+TypeHandle`  

