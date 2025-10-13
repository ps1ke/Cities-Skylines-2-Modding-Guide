# Game.Objects.QuantityUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class QuantityUpdateSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_QuantityQuery;
    private Unity.Entities.EntityQuery m_PostConfigurationQuery;
    private Unity.Entities.EntityQuery m_GarbageConfigurationQuery;
    private Game.Objects.QuantityUpdateSystem+TypeHandle __TypeHandle;

    public QuantityUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_QuantityQuery`  

```csharp
private Unity.Entities.EntityQuery m_QuantityQuery;
```

- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageConfigurationQuery;
```

- `private Game.Objects.QuantityUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.QuantityUpdateSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public QuantityUpdateSystem()`  

```csharp
[Preserve]
	public QuantityUpdateSystem()
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
		m_QuantityQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadWrite<Quantity>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>()
			}
		});
		m_PostConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<PostConfigurationData>());
		m_GarbageConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>());
		RequireForUpdate(m_QuantityQuery);
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
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new UpdateQuantityJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_QuantityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Quantity_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Vehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeliveryTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_WorkVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CreatureData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Creature_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailProducerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageProducerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageFacility_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IndustrialPropertyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_IndustrialProperty_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityServiceUpkeepData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_CityServiceUpkeep_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageLimitData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageLimitData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabQuantityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_QuantityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDeliveryTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DeliveryTruckData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWorkVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCargoTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CargoTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStorageCompanyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGarbageFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbageFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyResources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabServiceUpkeepDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RO_BufferLookup, ref base.CheckedStateRef),
			m_PostConfigurationData = (m_PostConfigurationQuery.IsEmptyIgnoreFilter ? default(PostConfigurationData) : m_PostConfigurationQuery.GetSingleton<PostConfigurationData>()),
			m_GarbageConfigurationData = (m_GarbageConfigurationQuery.IsEmptyIgnoreFilter ? default(GarbageParameterData) : m_GarbageConfigurationQuery.GetSingleton<GarbageParameterData>())
		}, m_QuantityQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Objects.QuantityUpdateSystem+UpdateQuantityJob`  
- `Game.Objects.QuantityUpdateSystem+TypeHandle`  

