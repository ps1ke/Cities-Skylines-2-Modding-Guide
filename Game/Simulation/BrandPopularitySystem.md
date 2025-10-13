# Game.Simulation.BrandPopularitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BrandPopularitySystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> m_BrandPopularity;
    private Unity.Jobs.JobHandle m_Readers;
    private Game.Simulation.BrandPopularitySystem+TypeHandle __TypeHandle;
    public static const System.Int32 kUpdatesPerDay;

    public BrandPopularitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> ReadBrandPopularity(Unity.Jobs.JobHandle& dependency);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> m_BrandPopularity`  

```csharp
private Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> m_BrandPopularity;
```

- `private Unity.Jobs.JobHandle m_Readers`  

```csharp
private Unity.Jobs.JobHandle m_Readers;
```

- `private Game.Simulation.BrandPopularitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BrandPopularitySystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 kUpdatesPerDay`  

```csharp
public static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public BrandPopularitySystem()`  

```csharp
[Preserve]
	public BrandPopularitySystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 2048;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<CompanyData>(),
				ComponentType.ReadOnly<PropertyRenter>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_BrandPopularity = new NativeList<BrandPopularity>(Allocator.Persistent);
		RequireForUpdate(m_ModifiedQuery);
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
		m_BrandPopularity.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> companyChunks = m_ModifiedQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = IJobExtensions.Schedule(new UpdateBrandPopularityJob
		{
			m_CompanyChunks = companyChunks,
			m_CompanyDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CompanyRentPropertyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnderConstructions = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BrandPopularity = m_BrandPopularity
		}, JobHandle.CombineDependencies(base.Dependency, outJobHandle, m_Readers));
		companyChunks.Dispose(jobHandle);
		base.Dependency = jobHandle;
		m_Readers = default(JobHandle);
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_BrandPopularity.Clear();
	}
```

- `public ReadBrandPopularity(Unity.Jobs.JobHandle& dependency) : Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity>`  

```csharp
public NativeList<BrandPopularity> ReadBrandPopularity(out JobHandle dependency)
	{
		dependency = base.Dependency;
		return m_BrandPopularity;
	}
```


## Nested types

- `Game.Simulation.BrandPopularitySystem+BrandPopularity`  
- `Game.Simulation.BrandPopularitySystem+UpdateBrandPopularityJob`  
- `Game.Simulation.BrandPopularitySystem+TypeHandle`  

