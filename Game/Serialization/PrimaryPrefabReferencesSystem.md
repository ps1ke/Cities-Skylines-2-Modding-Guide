# Game.Serialization.PrimaryPrefabReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrimaryPrefabReferencesSystem : Game.GameSystemBase
{
    private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
    private Unity.Entities.EntityQuery m_PrefabRefQuery;
    private Unity.Entities.EntityQuery m_SetLevelQuery;
    private Unity.Entities.EntityQuery m_CompanyDataQuery;
    private Unity.Entities.EntityQuery m_PolicyQuery;
    private Unity.Entities.EntityQuery m_ActualBudgetQuery;
    private Unity.Entities.EntityQuery m_ServiceBudgetQuery;
    private Unity.Entities.EntityQuery m_VehicleModelQuery;
    private Unity.Entities.EntityQuery m_EditorContainerQuery;
    private Unity.Entities.EntityQuery m_AtmosphereQuery;
    private Unity.Entities.EntityQuery m_BiomeQuery;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Unity.Entities.EntityQuery m_SubReplacementQuery;
    private Game.Serialization.PrimaryPrefabReferencesSystem+TypeHandle __TypeHandle;

    public PrimaryPrefabReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem`  

```csharp
private Game.Serialization.CheckPrefabReferencesSystem m_CheckPrefabReferencesSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem`  

```csharp
private Game.Rendering.TerrainMaterialSystem m_TerrainMaterialSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabRefQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabRefQuery;
```

- `private Unity.Entities.EntityQuery m_SetLevelQuery`  

```csharp
private Unity.Entities.EntityQuery m_SetLevelQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyDataQuery;
```

- `private Unity.Entities.EntityQuery m_PolicyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyQuery;
```

- `private Unity.Entities.EntityQuery m_ActualBudgetQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActualBudgetQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceBudgetQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceBudgetQuery;
```

- `private Unity.Entities.EntityQuery m_VehicleModelQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleModelQuery;
```

- `private Unity.Entities.EntityQuery m_EditorContainerQuery`  

```csharp
private Unity.Entities.EntityQuery m_EditorContainerQuery;
```

- `private Unity.Entities.EntityQuery m_AtmosphereQuery`  

```csharp
private Unity.Entities.EntityQuery m_AtmosphereQuery;
```

- `private Unity.Entities.EntityQuery m_BiomeQuery`  

```csharp
private Unity.Entities.EntityQuery m_BiomeQuery;
```

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Unity.Entities.EntityQuery m_SubReplacementQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubReplacementQuery;
```

- `private Game.Serialization.PrimaryPrefabReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.PrimaryPrefabReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PrimaryPrefabReferencesSystem()`  

```csharp
[Preserve]
	public PrimaryPrefabReferencesSystem()
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
		m_CheckPrefabReferencesSystem = base.World.GetOrCreateSystemManaged<CheckPrefabReferencesSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_TerrainMaterialSystem = base.World.GetOrCreateSystemManaged<TerrainMaterialSystem>();
		m_PrefabRefQuery = GetEntityQuery(ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<NetCompositionData>(), ComponentType.Exclude<EffectInstance>(), ComponentType.Exclude<LivePath>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_SetLevelQuery = GetEntityQuery(ComponentType.ReadOnly<UnderConstruction>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CompanyDataQuery = GetEntityQuery(ComponentType.ReadOnly<CompanyData>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_PolicyQuery = GetEntityQuery(ComponentType.ReadOnly<Policy>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ServiceBudgetQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceBudgetData>());
		m_AtmosphereQuery = GetEntityQuery(ComponentType.ReadOnly<AtmosphereData>());
		m_BiomeQuery = GetEntityQuery(ComponentType.ReadOnly<BiomeData>());
		m_VehicleModelQuery = GetEntityQuery(ComponentType.ReadOnly<VehicleModel>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_EditorContainerQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Tools.EditorContainer>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ChirpQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Triggers.Chirp>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_SubReplacementQuery = GetEntityQuery(ComponentType.ReadOnly<SubReplacement>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
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
		JobHandle dependencies;
		PrefabReferences references = m_CheckPrefabReferencesSystem.GetPrefabReferences(this, out dependencies);
		dependencies = JobHandle.CombineDependencies(base.Dependency, dependencies);
		FixPrefabRefJob jobData = new FixPrefabRefJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixUnderConstructionJob jobData2 = new FixUnderConstructionJob
		{
			m_UnderConstructionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UnderConstruction_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixCompanyDataJob jobData3 = new FixCompanyDataJob
		{
			m_CompanyDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_CompanyData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixPolicyJob jobData4 = new FixPolicyJob
		{
			m_PolicyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Policies_Policy_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixServiceBudgetJob jobData5 = new FixServiceBudgetJob
		{
			m_BudgetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceBudgetData_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixAtmosphereJob jobData6 = new FixAtmosphereJob
		{
			m_AtmosphereType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_AtmosphereData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixBiomeJob jobData7 = new FixBiomeJob
		{
			m_BiomeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_BiomeData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixVehicleModelJob jobData8 = new FixVehicleModelJob
		{
			m_VehicleModelType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_VehicleModel_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixEditorContainerJob jobData9 = new FixEditorContainerJob
		{
			m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixChirpJob jobData10 = new FixChirpJob
		{
			m_ChirpType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Triggers_Chirp_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ChirpEntityType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Triggers_ChirpEntity_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		FixSubReplacementJob jobData11 = new FixSubReplacementJob
		{
			m_SubReplacementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubReplacement_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabReferences = references
		};
		JobHandle job = JobChunkExtensions.ScheduleParallel(jobData, m_PrefabRefQuery, dependencies);
		JobHandle job2 = JobChunkExtensions.ScheduleParallel(jobData2, m_SetLevelQuery, dependencies);
		JobHandle job3 = JobChunkExtensions.ScheduleParallel(jobData3, m_CompanyDataQuery, dependencies);
		JobHandle job4 = JobChunkExtensions.ScheduleParallel(jobData4, m_PolicyQuery, dependencies);
		JobHandle job5 = JobChunkExtensions.ScheduleParallel(jobData5, m_ServiceBudgetQuery, dependencies);
		JobHandle job6 = JobChunkExtensions.ScheduleParallel(jobData6, m_AtmosphereQuery, dependencies);
		JobHandle job7 = JobChunkExtensions.ScheduleParallel(jobData7, m_BiomeQuery, dependencies);
		JobHandle job8 = JobChunkExtensions.ScheduleParallel(jobData8, m_VehicleModelQuery, dependencies);
		JobHandle job9 = JobChunkExtensions.ScheduleParallel(jobData9, m_EditorContainerQuery, dependencies);
		JobHandle job10 = JobChunkExtensions.ScheduleParallel(jobData10, m_ChirpQuery, dependencies);
		JobHandle job11 = JobChunkExtensions.ScheduleParallel(jobData11, m_SubReplacementQuery, dependencies);
		dependencies.Complete();
		m_CityConfigurationSystem.PatchReferences(ref references);
		m_ClimateSystem.PatchReferences(ref references);
		m_TerrainMaterialSystem.PatchReferences(ref references);
		dependencies = JobUtils.CombineDependencies(job9, job8, job, job3, job4, job5, job2, job6, job7, job10, job11);
		m_CheckPrefabReferencesSystem.AddPrefabReferencesUser(dependencies);
		base.Dependency = dependencies;
	}
```


## Nested types

- `Game.Serialization.PrimaryPrefabReferencesSystem+FixPrefabRefJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixUnderConstructionJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixCompanyDataJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixPolicyJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixServiceBudgetJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixAtmosphereJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixBiomeJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixVehicleModelJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixEditorContainerJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixChirpJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+FixSubReplacementJob`  
- `Game.Serialization.PrimaryPrefabReferencesSystem+TypeHandle`  

