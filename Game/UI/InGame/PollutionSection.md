# Game.UI.InGame.PollutionSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PollutionThreshold <groundPollutionKey>k__BackingField;
    private Game.UI.InGame.PollutionThreshold <airPollutionKey>k__BackingField;
    private Game.UI.InGame.PollutionThreshold <noisePollutionKey>k__BackingField;
    private Unity.Entities.EntityQuery m_UIConfigQuery;
    private Game.UI.InGame.PollutionSection+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1774369403_0;
    private Unity.Entities.EntityQuery __query_1774369403_1;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    private Game.UI.InGame.PollutionThreshold groundPollutionKey { private get; private set; }
    private Game.UI.InGame.PollutionThreshold airPollutionKey { private get; private set; }
    private Game.UI.InGame.PollutionThreshold noisePollutionKey { private get; private set; }

    public PollutionSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Game.Prefabs.PollutionData GetPollution();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PollutionThreshold <groundPollutionKey>k__BackingField`  

```csharp
private Game.UI.InGame.PollutionThreshold <groundPollutionKey>k__BackingField;
```

- `private Game.UI.InGame.PollutionThreshold <airPollutionKey>k__BackingField`  

```csharp
private Game.UI.InGame.PollutionThreshold <airPollutionKey>k__BackingField;
```

- `private Game.UI.InGame.PollutionThreshold <noisePollutionKey>k__BackingField`  

```csharp
private Game.UI.InGame.PollutionThreshold <noisePollutionKey>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_UIConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_UIConfigQuery;
```

- `private Game.UI.InGame.PollutionSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.PollutionSection+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1774369403_0`  

```csharp
private Unity.Entities.EntityQuery __query_1774369403_0;
```

- `private Unity.Entities.EntityQuery __query_1774369403_1`  

```csharp
private Unity.Entities.EntityQuery __query_1774369403_1;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `private Game.UI.InGame.PollutionThreshold groundPollutionKey { private get; private set }`  

```csharp
private Game.UI.InGame.PollutionThreshold groundPollutionKey { private get; private set; }
```

- `private Game.UI.InGame.PollutionThreshold airPollutionKey { private get; private set }`  

```csharp
private Game.UI.InGame.PollutionThreshold airPollutionKey { private get; private set; }
```

- `private Game.UI.InGame.PollutionThreshold noisePollutionKey { private get; private set }`  

```csharp
private Game.UI.InGame.PollutionThreshold noisePollutionKey { private get; private set; }
```


## Constructors

- `public PollutionSection()`  

```csharp
[Preserve]
	public PollutionSection()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<PollutionParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1774369403_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAllRW<CityModifier>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1774369403_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private GetPollution() : Game.Prefabs.PollutionData`  

```csharp
private PollutionData GetPollution()
	{
		CompleteDependency();
		bool destroyed = base.EntityManager.HasComponent<Destroyed>(selectedEntity);
		bool abandoned = base.EntityManager.HasComponent<Abandoned>(selectedEntity);
		bool isPark = base.EntityManager.HasComponent<Game.Buildings.Park>(selectedEntity);
		DynamicBuffer<Efficiency> buffer;
		float efficiency = (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out buffer) ? BuildingUtils.GetEfficiency(buffer) : 1f);
		base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Renter> buffer2);
		base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<InstalledUpgrade> buffer3);
		PollutionParameterData singleton = __query_1774369403_0.GetSingleton<PollutionParameterData>();
		DynamicBuffer<CityModifier> singletonBuffer = __query_1774369403_1.GetSingletonBuffer<CityModifier>(isReadOnly: true);
		ComponentLookup<PrefabRef> prefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<BuildingData> buildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<SpawnableBuildingData> spawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<PollutionData> pollutionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PollutionData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<PollutionModifierData> pollutionModifierDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PollutionModifierData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ZoneData> zoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef);
		BufferLookup<Employee> employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef);
		BufferLookup<HouseholdCitizen> householdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef);
		ComponentLookup<Citizen> citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef);
		return BuildingPollutionAddSystem.GetBuildingPollution(selectedPrefab, destroyed, abandoned, isPark, efficiency, buffer2, buffer3, singleton, singletonBuffer, ref prefabRefs, ref buildingDatas, ref spawnableDatas, ref pollutionDatas, ref pollutionModifierDatas, ref zoneDatas, ref employees, ref householdCitizens, ref citizens);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_UIConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UIPollutionConfigurationData>());
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

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		PollutionData pollution = GetPollution();
		UIPollutionConfigurationPrefab singletonPrefab = m_PrefabSystem.GetSingletonPrefab<UIPollutionConfigurationPrefab>(m_UIConfigQuery);
		groundPollutionKey = PollutionUIUtils.GetPollutionKey(singletonPrefab.m_GroundPollution, pollution.m_GroundPollution);
		airPollutionKey = PollutionUIUtils.GetPollutionKey(singletonPrefab.m_AirPollution, pollution.m_AirPollution);
		noisePollutionKey = PollutionUIUtils.GetPollutionKey(singletonPrefab.m_NoisePollution, pollution.m_NoisePollution);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("groundPollutionKey");
		writer.Write((int)groundPollutionKey);
		writer.PropertyName("airPollutionKey");
		writer.Write((int)airPollutionKey);
		writer.PropertyName("noisePollutionKey");
		writer.Write((int)noisePollutionKey);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		groundPollutionKey = PollutionThreshold.None;
		airPollutionKey = PollutionThreshold.None;
		noisePollutionKey = PollutionThreshold.None;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Building>(selectedEntity))
		{
			PollutionData pollution = GetPollution();
			if (!(pollution.m_GroundPollution > 0f) && !(pollution.m_AirPollution > 0f))
			{
				return pollution.m_NoisePollution > 0f;
			}
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.UI.InGame.PollutionSection+TypeHandle`  

