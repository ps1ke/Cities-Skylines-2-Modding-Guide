# Game.Prefabs.AreaInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AreaInitializeSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_SubAreaQuery;
    private Unity.Entities.EntityQuery m_PlaceholderQuery;
    private Game.Prefabs.AreaInitializeSystem+TypeHandle __TypeHandle;

    public AreaInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void InitializeAreaPrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void ValidateSubAreas();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_SubAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_SubAreaQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderQuery;
```

- `private Game.Prefabs.AreaInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.AreaInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AreaInitializeSystem()`  

```csharp
[Preserve]
	public AreaInitializeSystem()
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

- `private InitializeAreaPrefabs() : System.Void`  

```csharp
private void InitializeAreaPrefabs()
	{
		NativeArray<ArchetypeChunk> nativeArray = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		bool flag = false;
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<AreaColorData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AreaColorData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<AreaGeometryData> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<LotData> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_LotData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<DistrictData> typeHandle6 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_DistrictData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<MapTileData> typeHandle7 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MapTileData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<SpaceData> typeHandle8 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpaceData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<SurfaceData> typeHandle9 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SurfaceData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<StorageAreaData> typeHandle10 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_StorageAreaData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<ExtractorAreaData> typeHandle11 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ExtractorAreaData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<TerrainAreaData> typeHandle12 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TerrainAreaData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<SpawnableObjectData> typeHandle13 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubObject> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubObject_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubArea> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubArea_RW_BufferTypeHandle, ref base.CheckedStateRef);
			for (int i = 0; i < nativeArray.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray[i];
				if (archetypeChunk.Has(ref typeHandle))
				{
					flag = archetypeChunk.Has(ref typeHandle13);
					continue;
				}
				NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle2);
				NativeArray<AreaColorData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle3);
				NativeArray<AreaGeometryData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle4);
				NativeArray<SpawnableObjectData> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle13);
				NativeArray<LotData> nativeArray6 = archetypeChunk.GetNativeArray(ref typeHandle5);
				AreaType areaType = AreaType.None;
				GeometryFlags geometryFlags = (GeometryFlags)0;
				NativeArray<ExtractorAreaData> nativeArray7 = default(NativeArray<ExtractorAreaData>);
				if (nativeArray6.Length != 0)
				{
					areaType = AreaType.Lot;
					geometryFlags = GeometryFlags.PhysicalGeometry | GeometryFlags.PseudoRandom;
					if (archetypeChunk.Has(ref typeHandle10))
					{
						geometryFlags |= GeometryFlags.CanOverrideObjects;
					}
					nativeArray7 = archetypeChunk.GetNativeArray(ref typeHandle11);
				}
				else if (archetypeChunk.Has(ref typeHandle6))
				{
					areaType = AreaType.District;
					geometryFlags = GeometryFlags.OnWaterSurface;
				}
				else if (archetypeChunk.Has(ref typeHandle7))
				{
					areaType = AreaType.MapTile;
					geometryFlags = GeometryFlags.ProtectedArea | GeometryFlags.OnWaterSurface;
				}
				else if (archetypeChunk.Has(ref typeHandle8))
				{
					areaType = AreaType.Space;
				}
				else if (archetypeChunk.Has(ref typeHandle9))
				{
					areaType = AreaType.Surface;
				}
				if (archetypeChunk.Has(ref typeHandle12))
				{
					geometryFlags |= GeometryFlags.ShiftTerrain;
				}
				float minNodeDistance = AreaUtils.GetMinNodeDistance(areaType);
				for (int j = 0; j < nativeArray4.Length; j++)
				{
					AreaPrefab prefab = m_PrefabSystem.GetPrefab<AreaPrefab>(nativeArray2[j]);
					AreaColorData value = nativeArray3[j];
					AreaGeometryData value2 = nativeArray4[j];
					value2.m_Type = areaType;
					value2.m_Flags = geometryFlags;
					value2.m_SnapDistance = minNodeDistance;
					if (prefab.Has<ClearArea>())
					{
						value2.m_Flags |= GeometryFlags.ClearArea;
					}
					if (prefab.Has<ClipArea>())
					{
						value2.m_Flags |= GeometryFlags.ClipTerrain;
					}
					if (nativeArray7.IsCreated && nativeArray7[j].m_MapFeature != MapFeature.Forest)
					{
						value2.m_Flags |= GeometryFlags.CanOverrideObjects;
					}
					if (areaType == AreaType.Lot)
					{
						LotData lotData = nativeArray6[j];
						if (lotData.m_OnWater)
						{
							value2.m_Flags |= GeometryFlags.OnWaterSurface | GeometryFlags.RequireWater;
						}
						if (lotData.m_AllowOverlap)
						{
							value2.m_Flags &= ~GeometryFlags.PhysicalGeometry;
							value2.m_Flags |= GeometryFlags.HiddenIngame;
						}
					}
					value.m_FillColor = prefab.m_Color;
					value.m_EdgeColor = prefab.m_EdgeColor;
					value.m_SelectionFillColor = prefab.m_SelectionColor;
					value.m_SelectionEdgeColor = prefab.m_SelectionEdgeColor;
					if (prefab.TryGet<RenderedArea>(out var component))
					{
						value2.m_LodBias = component.m_LodBias;
					}
					nativeArray3[j] = value;
					nativeArray4[j] = value2;
				}
				BufferAccessor<SubObject> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
				for (int k = 0; k < bufferAccessor.Length; k++)
				{
					AreaSubObjects component2 = m_PrefabSystem.GetPrefab<AreaPrefab>(nativeArray2[k]).GetComponent<AreaSubObjects>();
					DynamicBuffer<SubObject> dynamicBuffer = bufferAccessor[k];
					for (int l = 0; l < component2.m_SubObjects.Length; l++)
					{
						AreaSubObjectInfo obj = component2.m_SubObjects[l];
						ObjectPrefab prefab2 = obj.m_Object;
						SubObject elem = new SubObject
						{
							m_Prefab = m_PrefabSystem.GetEntity(prefab2),
							m_Position = default(float3),
							m_Rotation = quaternion.identity,
							m_Probability = 100
						};
						if (obj.m_BorderPlacement)
						{
							elem.m_Flags |= SubObjectFlags.EdgePlacement;
						}
						dynamicBuffer.Add(elem);
					}
				}
				if (nativeArray5.Length != 0)
				{
					NativeArray<Entity> nativeArray8 = archetypeChunk.GetNativeArray(entityTypeHandle);
					for (int m = 0; m < nativeArray5.Length; m++)
					{
						Entity obj2 = nativeArray8[m];
						SpawnableObjectData value3 = nativeArray5[m];
						SpawnableArea component3 = m_PrefabSystem.GetPrefab<AreaPrefab>(nativeArray2[m]).GetComponent<SpawnableArea>();
						for (int n = 0; n < component3.m_Placeholders.Length; n++)
						{
							AreaPrefab prefab3 = component3.m_Placeholders[n];
							Entity entity = m_PrefabSystem.GetEntity(prefab3);
							base.EntityManager.GetBuffer<PlaceholderObjectElement>(entity).Add(new PlaceholderObjectElement(obj2));
						}
						value3.m_Probability = component3.m_Probability;
						nativeArray5[m] = value3;
					}
				}
				BufferAccessor<SubArea> bufferAccessor2 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle2);
				for (int num = 0; num < bufferAccessor2.Length; num++)
				{
					MasterArea component4 = m_PrefabSystem.GetPrefab<AreaPrefab>(nativeArray2[num]).GetComponent<MasterArea>();
					DynamicBuffer<SubArea> dynamicBuffer2 = bufferAccessor2[num];
					for (int num2 = 0; num2 < component4.m_SlaveAreas.Length; num2++)
					{
						AreaPrefab area = component4.m_SlaveAreas[num2].m_Area;
						dynamicBuffer2.Add(new SubArea
						{
							m_Prefab = m_PrefabSystem.GetEntity(area),
							m_NodeRange = -1
						});
					}
				}
			}
			if (flag)
			{
				JobHandle dependency = JobChunkExtensions.ScheduleParallel(new FixPlaceholdersJob
				{
					m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PlaceholderObjectElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RW_BufferTypeHandle, ref base.CheckedStateRef)
				}, m_PlaceholderQuery, base.Dependency);
				base.Dependency = dependency;
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<AreaData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_SubAreaQuery = GetEntityQuery(ComponentType.ReadOnly<Updated>(), ComponentType.ReadWrite<SubArea>(), ComponentType.ReadWrite<SubAreaNode>());
		m_PlaceholderQuery = GetEntityQuery(ComponentType.ReadOnly<AreaData>(), ComponentType.ReadOnly<PlaceholderObjectElement>(), ComponentType.Exclude<Deleted>());
		RequireAnyForUpdate(m_PrefabQuery, m_SubAreaQuery);
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
		if (!m_PrefabQuery.IsEmptyIgnoreFilter)
		{
			InitializeAreaPrefabs();
		}
		if (!m_SubAreaQuery.IsEmptyIgnoreFilter)
		{
			ValidateSubAreas();
		}
	}
```

- `private ValidateSubAreas() : System.Void`  

```csharp
private void ValidateSubAreas()
	{
		JobHandle dependency = JobChunkExtensions.ScheduleParallel(new ValidateSubAreasJob
		{
			m_AreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreaType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubArea_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubAreaNodeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RW_BufferTypeHandle, ref base.CheckedStateRef)
		}, m_SubAreaQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Prefabs.AreaInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.AreaInitializeSystem+ValidateSubAreasJob`  
- `Game.Prefabs.AreaInitializeSystem+TypeHandle`  

