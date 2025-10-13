# Game.UI.InGame.GarbageInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Simulation.GarbageAccumulationSystem m_GarbageAccumulationSystem;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Capacity;
    private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_StoredGarbage;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_ProcessingRate;
    private Colossal.UI.Binding.GetterValueBinding<System.Single> m_GarbageRate;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ProcessingAvailability;
    private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_LandfillAvailability;
    private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
    private Unity.Entities.EntityQuery m_GarbageFacilityModifiedQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public GarbageInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Single <OnCreate>b__11_0();
    private System.Int32 GetGarbageCapacity();
    private Game.UI.InGame.IndicatorValue GetLandfillAvailability();
    private Game.UI.InGame.IndicatorValue GetProcessingAvailability();
    private System.Single GetProcessingRate();
    private System.Int32 GetStoredGarbage();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
    private System.Void ResetResults();
}
```


## Fields

- `private Game.Simulation.GarbageAccumulationSystem m_GarbageAccumulationSystem`  

```csharp
private Game.Simulation.GarbageAccumulationSystem m_GarbageAccumulationSystem;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Capacity`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_Capacity;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_StoredGarbage`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Int32> m_StoredGarbage;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_ProcessingRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_ProcessingRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_GarbageRate`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<System.Single> m_GarbageRate;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ProcessingAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_ProcessingAvailability;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_LandfillAvailability`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.IndicatorValue> m_LandfillAvailability;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageFacilityModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageFacilityModifiedQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```

- `protected System.Boolean Modified { protected get }`  

```csharp
protected System.Boolean Modified { protected get; }
```


## Constructors

- `public GarbageInfoviewUISystem()`  

```csharp
[Preserve]
	public GarbageInfoviewUISystem()
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

- `private <OnCreate>b__11_0() : System.Single`  

```csharp
private System.Single <OnCreate>b__11_0();
```

- `private GetGarbageCapacity() : System.Int32`  

```csharp
private int GetGarbageCapacity()
	{
		return (int)m_Results[1];
	}
```

- `private GetLandfillAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetLandfillAvailability()
	{
		return IndicatorValue.Calculate(m_Results[1], m_Results[2], 0f);
	}
```

- `private GetProcessingAvailability() : Game.UI.InGame.IndicatorValue`  

```csharp
private IndicatorValue GetProcessingAvailability()
	{
		return IndicatorValue.Calculate(m_Results[0], math.max(m_GarbageAccumulationSystem.garbageAccumulation, 0L));
	}
```

- `private GetProcessingRate() : System.Single`  

```csharp
private float GetProcessingRate()
	{
		return m_Results[0];
	}
```

- `private GetStoredGarbage() : System.Int32`  

```csharp
private int GetStoredGarbage()
	{
		return (int)m_Results[2];
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_GarbageAccumulationSystem = base.World.GetOrCreateSystemManaged<GarbageAccumulationSystem>();
		m_GarbageFacilityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(), ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_GarbageFacilityModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(),
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<ServiceDispatch>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		AddBinding(m_Capacity = new GetterValueBinding<int>("garbageInfo", "capacity", GetGarbageCapacity));
		AddBinding(m_StoredGarbage = new GetterValueBinding<int>("garbageInfo", "storedGarbage", GetStoredGarbage));
		AddBinding(m_ProcessingRate = new GetterValueBinding<float>("garbageInfo", "processingRate", GetProcessingRate));
		AddBinding(m_GarbageRate = new GetterValueBinding<float>("garbageInfo", "productionRate", () => m_GarbageAccumulationSystem.garbageAccumulation));
		AddBinding(m_ProcessingAvailability = new GetterValueBinding<IndicatorValue>("garbageInfo", "processingAvailability", GetProcessingAvailability, new ValueWriter<IndicatorValue>()));
		AddBinding(m_LandfillAvailability = new GetterValueBinding<IndicatorValue>("garbageInfo", "landfillAvailability", GetLandfillAvailability, new ValueWriter<IndicatorValue>()));
		m_Results = new NativeArray<float>(3, Allocator.Persistent);
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
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		ResetResults();
		JobChunkExtensions.Schedule(new UpdateGarbageJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingEfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Storages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Storage_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Geometries = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageFacilities = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbageFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageAreaDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_GarbageFacilityQuery, base.Dependency).Complete();
		m_Capacity.Update();
		m_StoredGarbage.Update();
		m_ProcessingRate.Update();
		m_GarbageRate.Update();
		m_ProcessingAvailability.Update();
		m_LandfillAvailability.Update();
	}
```

- `private ResetResults() : System.Void`  

```csharp
private void ResetResults()
	{
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0f;
		}
	}
```


## Nested types

- `Game.UI.InGame.GarbageInfoviewUISystem+Result`  
- `Game.UI.InGame.GarbageInfoviewUISystem+UpdateGarbageJob`  
- `Game.UI.InGame.GarbageInfoviewUISystem+TypeHandle`  

