# Game.UI.InGame.FireAndRescueInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireAndRescueInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.FireHazardSystem m_FireHazardSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_FlammableQuery;
    private Unity.Entities.EntityQuery m_FireStationsModifiedQuery;
    private Unity.Entities.EntityQuery m_FireConfigQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageFireHazard;
    private Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle __TypeHandle;
    private static const System.String kGroup;

    protected System.Boolean Active { protected get; }
    protected System.Boolean Modified { protected get; }

    public FireAndRescueInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  

```csharp
private Game.Buildings.LocalEffectSystem m_LocalEffectSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  

```csharp
private Game.Simulation.FireHazardSystem m_FireHazardSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_FlammableQuery`  

```csharp
private Unity.Entities.EntityQuery m_FlammableQuery;
```

- `private Unity.Entities.EntityQuery m_FireStationsModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireStationsModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_FireConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireConfigQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  

```csharp
private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageFireHazard`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageFireHazard;
```

- `private Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle __TypeHandle;
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

- `public FireAndRescueInfoviewUISystem()`  

```csharp
[Preserve]
	public FireAndRescueInfoviewUISystem()
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
		m_LocalEffectSystem = base.World.GetOrCreateSystemManaged<LocalEffectSystem>();
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_FireHazardSystem = base.World.GetOrCreateSystemManaged<FireHazardSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_FlammableQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Tree>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Buildings.FireStation>(),
				ComponentType.ReadOnly<OnFire>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_FireStationsModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.FireStation>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Updated>()
			}
		});
		m_FireConfigQuery = GetEntityQuery(ComponentType.ReadOnly<FireConfigurationData>());
		AddBinding(m_AverageFireHazard = new ValueBinding<IndicatorValue>("fireAndRescueInfo", "averageFireHazard", default(IndicatorValue), new ValueWriter<IndicatorValue>()));
		m_Results = new NativeArray<float>(2, Allocator.Persistent);
		m_FireHazardData = new EventHelpers.FireHazardData(this);
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
		base.OnDestroy();
		m_Results.Dispose();
	}
```

- `protected virtual PerformUpdate() : System.Void`  

```csharp
protected override void PerformUpdate()
	{
		JobHandle dependencies;
		LocalEffectSystem.ReadData readData = m_LocalEffectSystem.GetReadData(out dependencies);
		FireConfigurationPrefab prefab = m_PrefabSystem.GetPrefab<FireConfigurationPrefab>(m_FireConfigQuery.GetSingletonEntity());
		if (m_Results.IsCreated)
		{
			base.Dependency.Complete();
			float num = m_Results[0];
			float num2 = m_Results[1];
			float current = ((num2 > 0f) ? (num / num2) : 0f);
			m_AverageFireHazard.Update(new IndicatorValue(0f, 100f, current));
			m_Results[0] = 0f;
			m_Results[1] = 0f;
		}
		m_FireHazardData.Update(this, readData, prefab, m_ClimateSystem.temperature, m_FireHazardSystem.noRainDays);
		JobHandle jobHandle = JobChunkExtensions.Schedule(new FireHazardJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DamagedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnderConstructionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_FireHazardData = m_FireHazardData,
			m_Result = m_Results
		}, m_FlammableQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		m_LocalEffectSystem.AddLocalEffectReader(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.UI.InGame.FireAndRescueInfoviewUISystem+FireHazardJob`  
- `Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle`  

