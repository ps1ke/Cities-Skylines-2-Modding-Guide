# Game.Prefabs.ResourceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResourceSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabGroup;
    private Unity.Entities.EntityQuery m_InfoGroup;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourcePrefabs;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourceInfos;
    private Unity.Jobs.JobHandle m_PrefabsReaders;
    private System.Int32 m_BaseConsumptionSum;
    private Game.Prefabs.ResourceSystem+TypeHandle __TypeHandle;

    public System.Int32 BaseConsumptionSum { get; }

    public ResourceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddPrefabsReader(Unity.Jobs.JobHandle handle);
    public Unity.Entities.Entity GetPrefab(Game.Economy.Resource resource);
    public Game.Prefabs.ResourcePrefabs GetPrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_PrefabGroup;
```

- `private Unity.Entities.EntityQuery m_InfoGroup`  

```csharp
private Unity.Entities.EntityQuery m_InfoGroup;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourcePrefabs`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourcePrefabs;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourceInfos`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_ResourceInfos;
```

- `private Unity.Jobs.JobHandle m_PrefabsReaders`  

```csharp
private Unity.Jobs.JobHandle m_PrefabsReaders;
```

- `private System.Int32 m_BaseConsumptionSum`  

```csharp
private System.Int32 m_BaseConsumptionSum;
```

- `private Game.Prefabs.ResourceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ResourceSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 BaseConsumptionSum { get }`  

```csharp
public System.Int32 BaseConsumptionSum { get; }
```


## Constructors

- `public ResourceSystem()`  

```csharp
[Preserve]
	public ResourceSystem()
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

- `public AddPrefabsReader(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddPrefabsReader(JobHandle handle)
	{
		m_PrefabsReaders = JobHandle.CombineDependencies(m_PrefabsReaders, handle);
	}
```

- `public GetPrefab(Game.Economy.Resource resource) : Unity.Entities.Entity`  

```csharp
public Entity GetPrefab(Resource resource)
	{
		return m_ResourcePrefabs[EconomyUtils.GetResourceIndex(resource)];
	}
```

- `public GetPrefabs() : Game.Prefabs.ResourcePrefabs`  

```csharp
public ResourcePrefabs GetPrefabs()
	{
		return new ResourcePrefabs(m_ResourcePrefabs);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<ResourceData>()
			}
		});
		m_InfoGroup = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<ResourceInfo>());
		m_ResourcePrefabs = new NativeArray<Entity>(EconomyUtils.ResourceCount, Allocator.Persistent);
		m_ResourceInfos = new NativeArray<Entity>(EconomyUtils.ResourceCount, Allocator.Persistent);
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
		m_PrefabsReaders.Complete();
		m_ResourcePrefabs.Dispose();
		m_ResourceInfos.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_PrefabsReaders.Complete();
		m_PrefabsReaders = default(JobHandle);
		if (!m_PrefabGroup.IsEmptyIgnoreFilter)
		{
			EntityCommandBuffer entityCommandBuffer = new EntityCommandBuffer(Allocator.Temp);
			NativeArray<ArchetypeChunk> nativeArray = m_PrefabGroup.ToArchetypeChunkArray(Allocator.TempJob);
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<ResourceData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResourceData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			float num = 0f;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				NativeArray<Entity> nativeArray2 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<PrefabData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle);
				NativeArray<ResourceData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < nativeArray4.Length; j++)
				{
					Entity value = nativeArray2[j];
					ResourcePrefab prefab = m_PrefabSystem.GetPrefab<ResourcePrefab>(nativeArray3[j]);
					ResourceData resourceData = nativeArray4[j];
					resourceData.m_IsMaterial = prefab.m_IsMaterial;
					resourceData.m_IsProduceable = prefab.m_IsProduceable;
					resourceData.m_IsTradable = prefab.m_IsTradable;
					resourceData.m_IsLeisure = prefab.m_IsLeisure;
					resourceData.m_Weight = prefab.m_Weight;
					resourceData.m_Price = prefab.m_InitialPrice;
					resourceData.m_WealthModifier = prefab.m_WealthModifier;
					resourceData.m_BaseConsumption = prefab.m_BaseConsumption;
					resourceData.m_ChildWeight = prefab.m_ChildWeight;
					resourceData.m_TeenWeight = prefab.m_TeenWeight;
					resourceData.m_AdultWeight = prefab.m_AdultWeight;
					resourceData.m_ElderlyWeight = prefab.m_ElderlyWeight;
					resourceData.m_CarConsumption = prefab.m_CarConsumption;
					resourceData.m_RequireTemperature = prefab.m_RequireTemperature;
					resourceData.m_RequiredTemperature = prefab.m_RequiredTemperature;
					resourceData.m_RequireNaturalResource = prefab.m_RequireNaturalResource;
					resourceData.m_NeededWorkPerUnit = prefab.m_NeededWorkPerUnit;
					nativeArray4[j] = resourceData;
					num += math.lerp(HouseholdBehaviorSystem.GetWeight(200, resourceData, 1, leisureIncluded: false), HouseholdBehaviorSystem.GetWeight(200, resourceData, 0, leisureIncluded: false), 0.2f);
					int index = (int)(prefab.m_Resource - 1);
					if (m_ResourcePrefabs[index] == Entity.Null)
					{
						m_ResourcePrefabs[index] = value;
						m_ResourceInfos[index] = entityCommandBuffer.CreateEntity();
						entityCommandBuffer.AddComponent(m_ResourceInfos[index], new ResourceInfo
						{
							m_Resource = EconomyUtils.GetResource(prefab.m_Resource)
						});
						entityCommandBuffer.AddComponent(m_ResourceInfos[index], default(Created));
					}
				}
			}
			entityCommandBuffer.Playback(base.EntityManager);
			entityCommandBuffer.Dispose();
			m_BaseConsumptionSum = Mathf.RoundToInt(num);
			nativeArray.Dispose();
		}
		if (m_InfoGroup.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<ArchetypeChunk> nativeArray5 = m_InfoGroup.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle2 = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<ResourceInfo> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Economy_ResourceInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		for (int k = 0; k < nativeArray5.Length; k++)
		{
			ArchetypeChunk archetypeChunk2 = nativeArray5[k];
			NativeArray<Entity> nativeArray6 = archetypeChunk2.GetNativeArray(entityTypeHandle2);
			NativeArray<ResourceInfo> nativeArray7 = archetypeChunk2.GetNativeArray(ref typeHandle3);
			for (int l = 0; l < nativeArray6.Length; l++)
			{
				int resourceIndex = EconomyUtils.GetResourceIndex(nativeArray7[l].m_Resource);
				if (resourceIndex >= 0 && m_ResourceInfos[resourceIndex] != nativeArray6[l])
				{
					m_ResourceInfos[resourceIndex] = nativeArray6[l];
				}
			}
		}
		nativeArray5.Dispose();
	}
```


## Nested types

- `Game.Prefabs.ResourceSystem+TypeHandle`  

