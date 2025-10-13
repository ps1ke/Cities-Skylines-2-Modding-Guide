# Game.Policies.ModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ModifiedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_EffectProviderQuery;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Collections.NativeQueue<Game.Policies.ModifiedSystem+PolicyEventInfo> m_PolicyEventInfos;
    private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
    private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
    private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
    private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
    private Unity.Entities.Entity m_TicketPricePolicy;
    private Game.Policies.ModifiedSystem+TypeHandle __TypeHandle;

    public ModifiedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_EffectProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_EffectProviderQuery;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Collections.NativeQueue<Game.Policies.ModifiedSystem+PolicyEventInfo> m_PolicyEventInfos`  

```csharp
private Unity.Collections.NativeQueue<Game.Policies.ModifiedSystem+PolicyEventInfo> m_PolicyEventInfos;
```

- `private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData`  

```csharp
private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
```

- `private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData`  

```csharp
private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
```

- `private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData`  

```csharp
private Game.Policies.RouteModifierInitializeSystem+RouteModifierRefreshData m_RouteModifierRefreshData;
```

- `private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData`  

```csharp
private Game.Simulation.CityModifierUpdateSystem+CityModifierRefreshData m_CityModifierRefreshData;
```

- `private Unity.Entities.Entity m_TicketPricePolicy`  

```csharp
private Unity.Entities.Entity m_TicketPricePolicy;
```

- `private Game.Policies.ModifiedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.ModifiedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ModifiedSystem()`  

```csharp
[Preserve]
	public ModifiedSystem()
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
		m_PolicyEventInfos = new NativeQueue<PolicyEventInfo>(Allocator.Persistent);
		m_DistrictModifierRefreshData = new DistrictModifierInitializeSystem.DistrictModifierRefreshData(this);
		m_BuildingModifierRefreshData = new BuildingModifierInitializeSystem.BuildingModifierRefreshData(this);
		m_RouteModifierRefreshData = new RouteModifierInitializeSystem.RouteModifierRefreshData(this);
		m_CityModifierRefreshData = new CityModifierUpdateSystem.CityModifierRefreshData(this);
		PrefabSystem orCreateSystemManaged = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		EntityQuery entityQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		UITransportConfigurationPrefab singletonPrefab = orCreateSystemManaged.GetSingletonPrefab<UITransportConfigurationPrefab>(entityQuery);
		m_TicketPricePolicy = orCreateSystemManaged.GetEntity(singletonPrefab.m_TicketPricePolicy);
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<Modify>());
		m_EffectProviderQuery = GetEntityQuery(ComponentType.ReadOnly<CityEffectProvider>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		RequireForUpdate(m_EventQuery);
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
		m_PolicyEventInfos.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> effectProviderChunks = m_EffectProviderQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		m_DistrictModifierRefreshData.Update(this);
		m_BuildingModifierRefreshData.Update(this);
		m_RouteModifierRefreshData.Update(this);
		m_CityModifierRefreshData.Update(this);
		NativeQueue<TriggerAction> nativeQueue = (m_TriggerSystem.Enabled ? m_TriggerSystem.CreateActionBuffer() : new NativeQueue<TriggerAction>(Allocator.TempJob));
		JobHandle jobHandle = JobChunkExtensions.Schedule(new ModifyPolicyJob
		{
			m_DistrictModifierRefreshData = m_DistrictModifierRefreshData,
			m_BuildingModifierRefreshData = m_BuildingModifierRefreshData,
			m_RouteModifierRefreshData = m_RouteModifierRefreshData,
			m_CityModifierRefreshData = m_CityModifierRefreshData,
			m_EffectProviderChunks = effectProviderChunks,
			m_ModifyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Policies_Modify_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TriggerBuffer = nativeQueue.AsParallelWriter(),
			m_DistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_District_RW_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Extension_RW_ComponentLookup, ref base.CheckedStateRef),
			m_RouteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Route_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_City_RW_ComponentLookup, ref base.CheckedStateRef),
			m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RW_BufferLookup, ref base.CheckedStateRef),
			m_BuildingModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_BuildingModifier_RW_BufferLookup, ref base.CheckedStateRef),
			m_RouteModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteModifier_RW_BufferLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RW_BufferLookup, ref base.CheckedStateRef),
			m_Policies = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Policies_Policy_RW_BufferLookup, ref base.CheckedStateRef),
			m_PolicyEventInfos = m_PolicyEventInfos.AsParallelWriter(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
			m_TicketPricePolicy = m_TicketPricePolicy
		}, m_EventQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		effectProviderChunks.Dispose(jobHandle);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
		if (m_TriggerSystem.Enabled)
		{
			m_TriggerSystem.AddActionBufferWriter(jobHandle);
		}
		else
		{
			nativeQueue.Dispose(jobHandle);
		}
		base.Dependency = jobHandle;
		jobHandle.Complete();
		while (m_PolicyEventInfos.Count > 0)
		{
			Telemetry.Policy(m_PolicyEventInfos.Dequeue());
		}
	}
```


## Nested types

- `Game.Policies.ModifiedSystem+PolicyRange`  
- `Game.Policies.ModifiedSystem+PolicyEventInfo`  
- `Game.Policies.ModifiedSystem+ModifyPolicyJob`  
- `Game.Policies.ModifiedSystem+TypeHandle`  

