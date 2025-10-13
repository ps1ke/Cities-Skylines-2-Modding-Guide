# Game.UI.InGame.DisasterInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DisasterInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelteredCount;
    private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelterCapacity;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ShelterAvailability;
    private Colossal.Collections.NativeAccumulator<Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob+Result> m_Result;
    private Unity.Entities.EntityQuery m_SheltersQuery;
    private Unity.Entities.EntityQuery m_SheltersModifiedQuery;
    private Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public DisasterInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelteredCount`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelteredCount;
```

- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelterCapacity`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Int32> m_ShelterCapacity;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ShelterAvailability`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_ShelterAvailability;
```

- `private Colossal.Collections.NativeAccumulator<Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob+Result> m_Result`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob+Result> m_Result;
```

- `private Unity.Entities.EntityQuery m_SheltersQuery`  

```csharp
private Unity.Entities.EntityQuery m_SheltersQuery;
```

- `private Unity.Entities.EntityQuery m_SheltersModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_SheltersModifiedQuery;
```

- `private Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public DisasterInfoviewUISystem()`  

```csharp
[Preserve]
	public DisasterInfoviewUISystem()
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
		m_SheltersQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.EmergencyShelter>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_SheltersModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Buildings.EmergencyShelter>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Updated>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		AddBinding(m_ShelteredCount = new ValueBinding<int>("disasterInfo", "shelteredCount", 0));
		AddBinding(m_ShelterCapacity = new ValueBinding<int>("disasterInfo", "shelterCapacity", 0));
		AddBinding(m_ShelterAvailability = new ValueBinding<IndicatorValue>("disasterInfo", "shelterAvailability", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		m_Result = new NativeAccumulator<UpdateDisasterResponseJob.Result>(Allocator.Persistent);
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
		m_Result.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		m_Result.Clear();
		JobChunkExtensions.Schedule(new UpdateDisasterResponseJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OccupantType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Occupant_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EmergencyShelterDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EmergencyShelterData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Result = m_Result
		}, m_SheltersQuery, base.Dependency).Complete();
		UpdateDisasterResponseJob.Result result = m_Result.GetResult();
		m_ShelteredCount.Update(result.m_Count);
		m_ShelterCapacity.Update(result.m_Capacity);
		m_ShelterAvailability.Update(new IndicatorValue(0f, result.m_Capacity, result.m_Capacity - result.m_Count));
	}
```


## Nested types

- `Game.UI.InGame.DisasterInfoviewUISystem+UpdateDisasterResponseJob`  
- `Game.UI.InGame.DisasterInfoviewUISystem+TypeHandle`  

