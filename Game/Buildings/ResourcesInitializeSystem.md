# Game.Buildings.ResourcesInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourcesInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_Additions;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Buildings.ResourcesInitializeSystem+TypeHandle __TypeHandle;

    public ResourcesInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_Additions`  

```csharp
private Unity.Entities.EntityQuery m_Additions;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Buildings.ResourcesInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ResourcesInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResourcesInitializeSystem()`  

```csharp
[Preserve]
	public ResourcesInitializeSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_Additions = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadWrite<Resources>(),
				ComponentType.ReadWrite<PrefabRef>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<ServiceUpgrade>()
			}
		});
		RequireForUpdate(m_Additions);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		InitializeCityServiceJob jobData = new InitializeCityServiceJob
		{
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourcesType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourceConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ResourceConsumer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InitialResourceDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_InitialResourceData_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceUpkeepDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourceConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ResourceConsumer_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CreatedDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Created_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_Additions, base.Dependency);
		m_ResourceSystem.AddPrefabsReader(base.Dependency);
	}
```


## Nested types

- `Game.Buildings.ResourcesInitializeSystem+InitializeCityServiceJob`  
- `Game.Buildings.ResourcesInitializeSystem+TypeHandle`  

