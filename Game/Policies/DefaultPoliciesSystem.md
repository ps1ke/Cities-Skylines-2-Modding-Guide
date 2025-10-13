# Game.Policies.DefaultPoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DefaultPoliciesSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Unity.Entities.EntityQuery m_CityConfigurationQuery;
    private Game.Policies.DefaultPoliciesSystem+TypeHandle __TypeHandle;

    public DefaultPoliciesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Unity.Entities.EntityQuery m_CityConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_CityConfigurationQuery;
```

- `private Game.Policies.DefaultPoliciesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.DefaultPoliciesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DefaultPoliciesSystem()`  

```csharp
[Preserve]
	public DefaultPoliciesSystem()
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
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadWrite<Policy>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>());
		m_CityConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceFeeParameterData>());
		RequireForUpdate(m_CreatedQuery);
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
		AddDefaultPoliciesJob jobData = new AddDefaultPoliciesJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PolicyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Policies_Policy_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PolicySliderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PolicySliderData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DefaultPolicyData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_DefaultPolicyData_RO_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedQuery, base.Dependency);
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (context.purpose != Purpose.NewGame && (context.purpose != Purpose.LoadGame || !(context.version < Version.taxiFee)))
		{
			return;
		}
		Entity singletonEntity = m_CityConfigurationQuery.GetSingletonEntity();
		DynamicBuffer<Policy> buffer = base.EntityManager.GetBuffer<Policy>(m_CitySystem.City);
		if (!base.EntityManager.TryGetBuffer(singletonEntity, isReadOnly: true, out DynamicBuffer<DefaultPolicyData> buffer2))
		{
			return;
		}
		for (int i = 0; i < buffer2.Length; i++)
		{
			DefaultPolicyData defaultPolicyData = buffer2[i];
			if (base.EntityManager.HasComponent<PolicySliderData>(defaultPolicyData.m_Policy))
			{
				PolicySliderData componentData = base.EntityManager.GetComponentData<PolicySliderData>(defaultPolicyData.m_Policy);
				buffer.Add(new Policy(defaultPolicyData.m_Policy, PolicyFlags.Active, componentData.m_Default));
			}
			else
			{
				buffer.Add(new Policy(defaultPolicyData.m_Policy, PolicyFlags.Active, 0f));
			}
		}
	}
```


## Nested types

- `Game.Policies.DefaultPoliciesSystem+AddDefaultPoliciesJob`  
- `Game.Policies.DefaultPoliciesSystem+TypeHandle`  

