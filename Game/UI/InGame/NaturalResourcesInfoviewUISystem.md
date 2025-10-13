# Game.UI.InGame.NaturalResourcesInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NaturalResourcesInfoviewUISystem : Game.UI.InGame.InfoviewUISystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOil;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOre;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableForest;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFertility;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestRenewalRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityRenewalRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FishRenewalRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFish;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_OilExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_OreExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityExtractionRate;
    private Colossal.UI.Binding.ValueBinding<System.Single> m_FishExtractionRate;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_ExtractorQuery;
    private Unity.Collections.NativeArray<System.Single> m_Results;
    private Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_1701516005_0;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    protected System.Boolean Active { protected get; }

    public NaturalResourcesInfoviewUISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void PerformUpdate();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOil`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOil;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOre`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOre;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableForest`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableForest;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFertility`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFertility;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestRenewalRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestRenewalRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityRenewalRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityRenewalRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FishRenewalRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FishRenewalRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFish`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFish;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_OilExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_OilExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_OreExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_OreExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityExtractionRate;
```

- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FishExtractionRate`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Single> m_FishExtractionRate;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorQuery;
```

- `private Unity.Collections.NativeArray<System.Single> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Single> m_Results;
```

- `private Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_1701516005_0`  

```csharp
private Unity.Entities.EntityQuery __query_1701516005_0;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `protected System.Boolean Active { protected get }`  

```csharp
protected System.Boolean Active { protected get; }
```


## Constructors

- `public NaturalResourcesInfoviewUISystem()`  

```csharp
[Preserve]
	public NaturalResourcesInfoviewUISystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<EconomyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_1701516005_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		AddBinding(m_AvailableOil = new ValueBinding<float>("naturalResourceInfo", "availableOil", 0f));
		AddBinding(m_AvailableOre = new ValueBinding<float>("naturalResourceInfo", "availableOre", 0f));
		AddBinding(m_AvailableForest = new ValueBinding<float>("naturalResourceInfo", "availableForest", 0f));
		AddBinding(m_AvailableFertility = new ValueBinding<float>("naturalResourceInfo", "availableFertility", 0f));
		AddBinding(m_ForestRenewalRate = new ValueBinding<float>("naturalResourceInfo", "forestRenewalRate", 0f));
		AddBinding(m_FertilityRenewalRate = new ValueBinding<float>("naturalResourceInfo", "fertilityRenewalRate", 0f));
		AddBinding(m_FishRenewalRate = new ValueBinding<float>("naturalResourceInfo", "fishRenewalRate", 0f));
		AddBinding(m_AvailableFish = new ValueBinding<float>("naturalResourceInfo", "availableFish", 0f));
		AddBinding(m_OilExtractionRate = new ValueBinding<float>("naturalResourceInfo", "oilExtractionRate", 0f));
		AddBinding(m_OreExtractionRate = new ValueBinding<float>("naturalResourceInfo", "oreExtractionRate", 0f));
		AddBinding(m_ForestExtractionRate = new ValueBinding<float>("naturalResourceInfo", "forestExtractionRate", 0f));
		AddBinding(m_FertilityExtractionRate = new ValueBinding<float>("naturalResourceInfo", "fertilityExtractionRate", 0f));
		AddBinding(m_FishExtractionRate = new ValueBinding<float>("naturalResourceInfo", "fishExtractionRate", 0f));
		m_MapTileQuery = GetEntityQuery(ComponentType.ReadOnly<MapTile>(), ComponentType.ReadOnly<MapFeatureElement>(), ComponentType.Exclude<Native>());
		m_ExtractorQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Companies.ExtractorCompany>(), ComponentType.ReadOnly<PropertyRenter>(), ComponentType.ReadOnly<WorkProvider>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_Results = new NativeArray<float>(13, Allocator.Persistent);
		RequireForUpdate<ExtractorParameterData>();
		RequireForUpdate<EconomyParameterData>();
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
		ResetResults(m_Results);
		JobChunkExtensions.Schedule(new UpdateResourcesJob
		{
			m_MapFeatureElementHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_MapFeatureElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Results = m_Results
		}, m_MapTileQuery, base.Dependency).Complete();
		JobChunkExtensions.Schedule(new UpdateExtractionJob
		{
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PropertyRenterHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkProviderHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AttachedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorsFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Extractor_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorAreaDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkplaceDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IndustrialProcessDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingEfficiencyFromEntity = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreaBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameters = __query_1701516005_0.GetSingleton<EconomyParameterData>(),
			m_Result = m_Results
		}, m_ExtractorQuery, base.Dependency).Complete();
		m_FertilityExtractionRate.Update(m_Results[5]);
		m_ForestExtractionRate.Update(m_Results[6]);
		m_OreExtractionRate.Update(m_Results[8]);
		m_OilExtractionRate.Update(m_Results[7]);
		m_FishExtractionRate.Update(m_Results[11]);
		m_AvailableFertility.Update(m_Results[0]);
		m_AvailableForest.Update(m_Results[1]);
		m_AvailableOre.Update(m_Results[3]);
		m_AvailableOil.Update(m_Results[2]);
		m_AvailableFish.Update(m_Results[4]);
		m_ForestRenewalRate.Update(m_Results[10]);
		m_FertilityRenewalRate.Update(m_Results[9]);
		m_FishRenewalRate.Update(m_Results[12]);
	}
```


## Nested types

- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+Result`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+UpdateResourcesJob`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+UpdateExtractionJob`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle`  

