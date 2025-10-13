# Game.Prefabs.ObjectInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ObjectInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_PlaceholderQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.ObjectInitializeSystem+TypeHandle __TypeHandle;

    public ObjectInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Game.Prefabs.MeshGroupFlags GetMeshGroupFlag(Game.Objects.ObjectState state, System.Boolean inverse);
    private System.UInt16 GetRandomSeed(System.String name);
    private System.Void InitializePrefab(Game.Prefabs.AssetStampPrefab stampPrefab, Game.Prefabs.AssetStampData& assetStampData, Game.Prefabs.PlaceableObjectData& placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData);
    private System.Void InitializePrefab(Game.Prefabs.ObjectGeometryPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.GrowthScaleData& growthScaleData, Game.Prefabs.StackData& stackData, Game.Prefabs.QuantityObjectData& quantityObjectData, Game.Prefabs.CreatureData& creatureData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMeshGroup> meshGroups, Unity.Entities.DynamicBuffer<Game.Prefabs.CharacterElement> characterElements, System.Boolean isPlantObject, System.Boolean isHumanObject, System.Boolean isBuildingObject, System.Boolean isVehicleObject, System.Boolean isCreatureObject);
    private System.Void InitializePrefab(Game.Prefabs.MarkerObjectPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void UpdateStackBounds(Colossal.Mathematics.Bounds1& stackBounds, Colossal.Mathematics.Bounds3& meshBounds, Game.Prefabs.StackProperties properties);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.ObjectInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.ObjectInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ObjectInitializeSystem()`  

```csharp
[Preserve]
	public ObjectInitializeSystem()
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

- `private static GetMeshGroupFlag(Game.Objects.ObjectState state, System.Boolean inverse) : Game.Prefabs.MeshGroupFlags`  

```csharp
private static MeshGroupFlags GetMeshGroupFlag(ObjectState state, bool inverse)
	{
		if (inverse)
		{
			switch (state)
			{
			case ObjectState.Cold:
				return MeshGroupFlags.RequireWarm;
			case ObjectState.Warm:
				return MeshGroupFlags.RequireCold;
			case ObjectState.Home:
				return MeshGroupFlags.RequireHomeless;
			case ObjectState.Homeless:
				return MeshGroupFlags.RequireHome;
			case ObjectState.Motorcycle:
				return MeshGroupFlags.ForbidMotorcycle;
			}
		}
		else
		{
			switch (state)
			{
			case ObjectState.Cold:
				return MeshGroupFlags.RequireCold;
			case ObjectState.Warm:
				return MeshGroupFlags.RequireWarm;
			case ObjectState.Home:
				return MeshGroupFlags.RequireHome;
			case ObjectState.Homeless:
				return MeshGroupFlags.RequireHomeless;
			case ObjectState.Motorcycle:
				return MeshGroupFlags.RequireMotorcycle;
			}
		}
		return (MeshGroupFlags)0u;
	}
```

- `private GetRandomSeed(System.String name) : System.UInt16`  

```csharp
private ushort GetRandomSeed(string name)
	{
		uint num = 0u;
		for (int i = 0; i < name.Length; i++)
		{
			num = (num << 1) ^ name[i];
		}
		return (ushort)num;
	}
```

- `private InitializePrefab(Game.Prefabs.AssetStampPrefab stampPrefab, Game.Prefabs.AssetStampData& assetStampData, Game.Prefabs.PlaceableObjectData& placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData) : System.Void`  

```csharp
private void InitializePrefab(MarkerObjectPrefab objectPrefab, PlaceableObjectData placeableObjectData, ref ObjectGeometryData objectGeometryData, DynamicBuffer<SubMesh> meshes)
	{
		Bounds3 bounds = default(Bounds3);
		if (objectPrefab.m_Mesh != null)
		{
			Entity entity = m_PrefabSystem.GetEntity(objectPrefab.m_Mesh);
			MeshData componentData = base.EntityManager.GetComponentData<MeshData>(entity);
			Bounds3 bounds2 = objectPrefab.m_Mesh.bounds;
			float renderingSize = RenderingUtils.GetRenderingSize(MathUtils.Size(bounds2));
			componentData.m_MinLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, componentData.m_LodBias);
			componentData.m_ShadowLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, componentData.m_ShadowBias);
			objectGeometryData.m_MinLod = math.min(objectGeometryData.m_MinLod, componentData.m_MinLod);
			objectGeometryData.m_Layers = ((componentData.m_DefaultLayers == (MeshLayer)0) ? MeshLayer.Default : componentData.m_DefaultLayers);
			bounds |= bounds2;
			base.EntityManager.SetComponentData(entity, componentData);
			meshes.Add(new SubMesh(entity, (SubMeshFlags)0u, 0));
		}
		objectGeometryData.m_Bounds = bounds;
		objectGeometryData.m_Size = ObjectUtils.GetSize(bounds);
		if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.Wall) != Game.Objects.PlacementFlags.None)
		{
			objectGeometryData.m_Pivot = default(float3);
		}
		else if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.Hanging) != Game.Objects.PlacementFlags.None)
		{
			objectGeometryData.m_Pivot = new float3(0f, math.lerp(bounds.min.y, bounds.max.y, 0.9f), 0f);
		}
		else
		{
			objectGeometryData.m_Pivot = new float3(0f, math.lerp(bounds.min.y, bounds.max.y, 0.25f), 0f);
		}
		if (objectPrefab.m_Circular)
		{
			objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.Circular;
			objectGeometryData.m_Size.xz = math.max(objectGeometryData.m_Size.x, objectGeometryData.m_Size.z);
		}
		objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.Marker;
	}
```

- `private InitializePrefab(Game.Prefabs.ObjectGeometryPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.GrowthScaleData& growthScaleData, Game.Prefabs.StackData& stackData, Game.Prefabs.QuantityObjectData& quantityObjectData, Game.Prefabs.CreatureData& creatureData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMeshGroup> meshGroups, Unity.Entities.DynamicBuffer<Game.Prefabs.CharacterElement> characterElements, System.Boolean isPlantObject, System.Boolean isHumanObject, System.Boolean isBuildingObject, System.Boolean isVehicleObject, System.Boolean isCreatureObject) : System.Void`  

```csharp
private void InitializePrefab(MarkerObjectPrefab objectPrefab, PlaceableObjectData placeableObjectData, ref ObjectGeometryData objectGeometryData, DynamicBuffer<SubMesh> meshes)
	{
		Bounds3 bounds = default(Bounds3);
		if (objectPrefab.m_Mesh != null)
		{
			Entity entity = m_PrefabSystem.GetEntity(objectPrefab.m_Mesh);
			MeshData componentData = base.EntityManager.GetComponentData<MeshData>(entity);
			Bounds3 bounds2 = objectPrefab.m_Mesh.bounds;
			float renderingSize = RenderingUtils.GetRenderingSize(MathUtils.Size(bounds2));
			componentData.m_MinLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, componentData.m_LodBias);
			componentData.m_ShadowLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, componentData.m_ShadowBias);
			objectGeometryData.m_MinLod = math.min(objectGeometryData.m_MinLod, componentData.m_MinLod);
			objectGeometryData.m_Layers = ((componentData.m_DefaultLayers == (MeshLayer)0) ? MeshLayer.Default : componentData.m_DefaultLayers);
			bounds |= bounds2;
			base.EntityManager.SetComponentData(entity, componentData);
			meshes.Add(new SubMesh(entity, (SubMeshFlags)0u, 0));
		}
		objectGeometryData.m_Bounds = bounds;
		objectGeometryData.m_Size = ObjectUtils.GetSize(bounds);
		if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.Wall) != Game.Objects.PlacementFlags.None)
		{
			objectGeometryData.m_Pivot = default(float3);
		}
		else if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.Hanging) != Game.Objects.PlacementFlags.None)
		{
			objectGeometryData.m_Pivot = new float3(0f, math.lerp(bounds.min.y, bounds.max.y, 0.9f), 0f);
		}
		else
		{
			objectGeometryData.m_Pivot = new float3(0f, math.lerp(bounds.min.y, bounds.max.y, 0.25f), 0f);
		}
		if (objectPrefab.m_Circular)
		{
			objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.Circular;
			objectGeometryData.m_Size.xz = math.max(objectGeometryData.m_Size.x, objectGeometryData.m_Size.z);
		}
		objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.Marker;
	}
```

- `private InitializePrefab(Game.Prefabs.MarkerObjectPrefab objectPrefab, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Prefabs.ObjectGeometryData& objectGeometryData, Unity.Entities.DynamicBuffer<Game.Prefabs.SubMesh> meshes) : System.Void`  

```csharp
private void InitializePrefab(MarkerObjectPrefab objectPrefab, PlaceableObjectData placeableObjectData, ref ObjectGeometryData objectGeometryData, DynamicBuffer<SubMesh> meshes)
	{
		Bounds3 bounds = default(Bounds3);
		if (objectPrefab.m_Mesh != null)
		{
			Entity entity = m_PrefabSystem.GetEntity(objectPrefab.m_Mesh);
			MeshData componentData = base.EntityManager.GetComponentData<MeshData>(entity);
			Bounds3 bounds2 = objectPrefab.m_Mesh.bounds;
			float renderingSize = RenderingUtils.GetRenderingSize(MathUtils.Size(bounds2));
			componentData.m_MinLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, componentData.m_LodBias);
			componentData.m_ShadowLod = (byte)RenderingUtils.CalculateLodLimit(renderingSize, componentData.m_ShadowBias);
			objectGeometryData.m_MinLod = math.min(objectGeometryData.m_MinLod, componentData.m_MinLod);
			objectGeometryData.m_Layers = ((componentData.m_DefaultLayers == (MeshLayer)0) ? MeshLayer.Default : componentData.m_DefaultLayers);
			bounds |= bounds2;
			base.EntityManager.SetComponentData(entity, componentData);
			meshes.Add(new SubMesh(entity, (SubMeshFlags)0u, 0));
		}
		objectGeometryData.m_Bounds = bounds;
		objectGeometryData.m_Size = ObjectUtils.GetSize(bounds);
		if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.Wall) != Game.Objects.PlacementFlags.None)
		{
			objectGeometryData.m_Pivot = default(float3);
		}
		else if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.Hanging) != Game.Objects.PlacementFlags.None)
		{
			objectGeometryData.m_Pivot = new float3(0f, math.lerp(bounds.min.y, bounds.max.y, 0.9f), 0f);
		}
		else
		{
			objectGeometryData.m_Pivot = new float3(0f, math.lerp(bounds.min.y, bounds.max.y, 0.25f), 0f);
		}
		if (objectPrefab.m_Circular)
		{
			objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.Circular;
			objectGeometryData.m_Size.xz = math.max(objectGeometryData.m_Size.x, objectGeometryData.m_Size.z);
		}
		objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.Marker;
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
				ComponentType.ReadOnly<ObjectData>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_PlaceholderQuery = GetEntityQuery(ComponentType.ReadOnly<ObjectData>(), ComponentType.ReadOnly<PlaceholderObjectElement>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_PrefabQuery);
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
		NativeArray<ArchetypeChunk> chunks = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		bool flag = false;
		try
		{
			EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<UtilityObjectData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UtilityObjectData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PillarData> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PillarData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<MoveableBridgeData> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MoveableBridgeData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetObjectData> typeHandle6 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetObjectData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PlantData> typeHandle7 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlantData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<HumanData> typeHandle8 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_HumanData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<BuildingData> typeHandle9 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<VehicleData> typeHandle10 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_VehicleData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<BuildingExtensionData> typeHandle11 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<ObjectGeometryData> typeHandle12 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PlaceableObjectData> typeHandle13 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<SpawnableObjectData> typeHandle14 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<AssetStampData> typeHandle15 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_AssetStampData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<GrowthScaleData> typeHandle16 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_GrowthScaleData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<StackData> typeHandle17 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_StackData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<QuantityObjectData> typeHandle18 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_QuantityObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<CreatureData> typeHandle19 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CreatureData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<BuildingTerraformData> typeHandle20 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingTerraformData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubMesh> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubMesh_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubMeshGroup> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubMeshGroup_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<CharacterElement> bufferTypeHandle3 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_CharacterElement_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubObject> bufferTypeHandle4 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubObject_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubNet> bufferTypeHandle5 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubNet_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubLane> bufferTypeHandle6 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubLane_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubArea> bufferTypeHandle7 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubArea_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubAreaNode> bufferTypeHandle8 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubAreaNode_RW_BufferTypeHandle, ref base.CheckedStateRef);
			CompleteDependency();
			SubArea elem3 = default(SubArea);
			for (int i = 0; i < chunks.Length; i++)
			{
				ArchetypeChunk archetypeChunk = chunks[i];
				if (archetypeChunk.Has(ref typeHandle))
				{
					flag |= archetypeChunk.Has(ref typeHandle14);
					continue;
				}
				NativeArray<PrefabData> nativeArray = archetypeChunk.GetNativeArray(ref typeHandle2);
				NativeArray<ObjectGeometryData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle12);
				NativeArray<PlaceableObjectData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle13);
				NativeArray<SpawnableObjectData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle14);
				NativeArray<AssetStampData> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle15);
				NativeArray<GrowthScaleData> nativeArray6 = archetypeChunk.GetNativeArray(ref typeHandle16);
				NativeArray<StackData> nativeArray7 = archetypeChunk.GetNativeArray(ref typeHandle17);
				NativeArray<QuantityObjectData> nativeArray8 = archetypeChunk.GetNativeArray(ref typeHandle18);
				NativeArray<CreatureData> nativeArray9 = archetypeChunk.GetNativeArray(ref typeHandle19);
				NativeArray<PillarData> nativeArray10 = archetypeChunk.GetNativeArray(ref typeHandle4);
				NativeArray<BuildingTerraformData> nativeArray11 = archetypeChunk.GetNativeArray(ref typeHandle20);
				NativeArray<BuildingExtensionData> nativeArray12 = archetypeChunk.GetNativeArray(ref typeHandle11);
				BufferAccessor<SubObject> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle4);
				BufferAccessor<SubArea> bufferAccessor2 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle7);
				BufferAccessor<SubMesh> bufferAccessor3 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
				BufferAccessor<SubMeshGroup> bufferAccessor4 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle2);
				BufferAccessor<CharacterElement> bufferAccessor5 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle3);
				BufferAccessor<SubNet> bufferAccessor6 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle5);
				BufferAccessor<SubLane> bufferAccessor7 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle6);
				bool flag2 = archetypeChunk.Has(ref typeHandle3);
				bool flag3 = archetypeChunk.Has(ref typeHandle5);
				bool flag4 = archetypeChunk.Has(ref typeHandle6);
				bool isPlantObject = archetypeChunk.Has(ref typeHandle7);
				bool flag5 = archetypeChunk.Has(ref typeHandle8);
				bool flag6 = archetypeChunk.Has(ref typeHandle9) || nativeArray12.Length != 0;
				bool isVehicleObject = archetypeChunk.Has(ref typeHandle10);
				bool isCreatureObject = nativeArray9.Length != 0;
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					ObjectPrefab prefab = m_PrefabSystem.GetPrefab<ObjectPrefab>(nativeArray[j]);
					ObjectGeometryData objectGeometryData = nativeArray2[j];
					objectGeometryData.m_MinLod = 255;
					objectGeometryData.m_Layers = (MeshLayer)0;
					PlaceableObjectData placeableObjectData = default(PlaceableObjectData);
					if (nativeArray3.Length != 0)
					{
						placeableObjectData = nativeArray3[j];
					}
					GrowthScaleData growthScaleData = default(GrowthScaleData);
					if (nativeArray6.Length != 0)
					{
						growthScaleData = nativeArray6[j];
					}
					StackData stackData = default(StackData);
					if (nativeArray7.Length != 0)
					{
						stackData = nativeArray7[j];
						stackData.m_FirstBounds = new Bounds1(float.MaxValue, float.MinValue);
						stackData.m_MiddleBounds = new Bounds1(float.MaxValue, float.MinValue);
						stackData.m_LastBounds = new Bounds1(float.MaxValue, float.MinValue);
					}
					QuantityObjectData quantityObjectData = default(QuantityObjectData);
					if (nativeArray8.Length != 0)
					{
						quantityObjectData = nativeArray8[j];
					}
					CreatureData creatureData = default(CreatureData);
					if (nativeArray9.Length != 0)
					{
						creatureData = nativeArray9[j];
						CreaturePrefab creaturePrefab = prefab as CreaturePrefab;
						creatureData.m_Gender = creaturePrefab.m_Gender;
						if (!flag5)
						{
							objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.LowCollisionPriority;
						}
					}
					if (prefab is AssetStampPrefab)
					{
						AssetStampData assetStampData = nativeArray5[j];
						InitializePrefab(prefab as AssetStampPrefab, ref assetStampData, ref placeableObjectData, ref objectGeometryData);
						nativeArray5[j] = assetStampData;
						objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.ExclusiveGround | Game.Objects.GeometryFlags.WalkThrough | Game.Objects.GeometryFlags.OccupyZone | Game.Objects.GeometryFlags.Stampable | Game.Objects.GeometryFlags.HasLot;
					}
					else if (prefab is ObjectGeometryPrefab)
					{
						CollectionUtils.TryGet(bufferAccessor4, j, out var value);
						CollectionUtils.TryGet(bufferAccessor5, j, out var value2);
						InitializePrefab(prefab as ObjectGeometryPrefab, placeableObjectData, ref objectGeometryData, ref growthScaleData, ref stackData, ref quantityObjectData, ref creatureData, bufferAccessor3[j], value, value2, isPlantObject, flag5, flag6, isVehicleObject, isCreatureObject);
						if (nativeArray10.Length != 0)
						{
							if (nativeArray10[j].m_Type == PillarType.Horizontal)
							{
								objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.IgnoreBottomCollision;
							}
							else
							{
								objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.BaseCollision;
							}
							if (flag3)
							{
								objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.WalkThrough;
							}
							objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.OccupyZone | Game.Objects.GeometryFlags.CanSubmerge | Game.Objects.GeometryFlags.OptionalAttach;
						}
						else if (flag2)
						{
							objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.IgnoreSecondaryCollision;
						}
						else if (flag4)
						{
							objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.OccupyZone;
						}
						else
						{
							objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.Overridable | Game.Objects.GeometryFlags.Brushable;
						}
					}
					else if (prefab is MarkerObjectPrefab)
					{
						InitializePrefab(prefab as MarkerObjectPrefab, placeableObjectData, ref objectGeometryData, bufferAccessor3[j]);
						placeableObjectData.m_Flags |= Game.Objects.PlacementFlags.CanOverlap;
						objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.WalkThrough;
					}
					if (!flag6 && nativeArray11.Length != 0)
					{
						BuildingTerraformOverride component = prefab.GetComponent<BuildingTerraformOverride>();
						Bounds2 bounds;
						if ((objectGeometryData.m_Flags & Game.Objects.GeometryFlags.Standing) != Game.Objects.GeometryFlags.None)
						{
							float2 xz = objectGeometryData.m_Pivot.xz;
							float2 @float = objectGeometryData.m_LegSize.xz * 0.5f + objectGeometryData.m_LegOffset;
							bounds = new Bounds2(xz - @float, xz + @float);
						}
						else
						{
							bounds = objectGeometryData.m_Bounds.xz;
						}
						BuildingTerraformData buildingTerraformData = nativeArray11[j];
						BuildingInitializeSystem.InitializeTerraformData(component, ref buildingTerraformData, bounds, bounds);
						nativeArray11[j] = buildingTerraformData;
					}
					nativeArray2[j] = objectGeometryData;
					if (nativeArray3.Length != 0)
					{
						nativeArray3[j] = placeableObjectData;
					}
					if (nativeArray6.Length != 0)
					{
						nativeArray6[j] = growthScaleData;
					}
					if (nativeArray7.Length != 0)
					{
						if (stackData.m_FirstBounds.min > stackData.m_FirstBounds.max)
						{
							stackData.m_FirstBounds = default(Bounds1);
						}
						if (stackData.m_MiddleBounds.min > stackData.m_MiddleBounds.max)
						{
							stackData.m_MiddleBounds = default(Bounds1);
						}
						if (stackData.m_LastBounds.min > stackData.m_LastBounds.max)
						{
							stackData.m_LastBounds = default(Bounds1);
						}
						nativeArray7[j] = stackData;
					}
					if (nativeArray8.Length != 0)
					{
						nativeArray8[j] = quantityObjectData;
					}
					if (nativeArray9.Length != 0)
					{
						nativeArray9[j] = creatureData;
					}
				}
				for (int k = 0; k < bufferAccessor.Length; k++)
				{
					ObjectSubObjects component2 = m_PrefabSystem.GetPrefab<ObjectPrefab>(nativeArray[k]).GetComponent<ObjectSubObjects>();
					if (component2.m_SubObjects == null)
					{
						continue;
					}
					DynamicBuffer<SubObject> dynamicBuffer = bufferAccessor[k];
					for (int l = 0; l < component2.m_SubObjects.Length; l++)
					{
						ObjectSubObjectInfo objectSubObjectInfo = component2.m_SubObjects[l];
						ObjectPrefab objectPrefab = objectSubObjectInfo.m_Object;
						if (!(objectPrefab == null) && m_PrefabSystem.TryGetEntity(objectPrefab, out var entity))
						{
							SubObject elem = new SubObject
							{
								m_Prefab = entity,
								m_Position = objectSubObjectInfo.m_Position,
								m_Rotation = objectSubObjectInfo.m_Rotation,
								m_ParentIndex = objectSubObjectInfo.m_ParentMesh,
								m_GroupIndex = objectSubObjectInfo.m_GroupIndex,
								m_Probability = math.select(objectSubObjectInfo.m_Probability, 100, objectSubObjectInfo.m_Probability == 0)
							};
							if (objectSubObjectInfo.m_ParentMesh == -1)
							{
								elem.m_Flags |= SubObjectFlags.OnGround;
							}
							dynamicBuffer.Add(elem);
						}
					}
				}
				for (int m = 0; m < bufferAccessor6.Length; m++)
				{
					ObjectPrefab prefab2 = m_PrefabSystem.GetPrefab<ObjectPrefab>(nativeArray[m]);
					ObjectSubNets component3 = prefab2.GetComponent<ObjectSubNets>();
					if (component3.m_SubNets == null)
					{
						continue;
					}
					bool flag7 = false;
					DynamicBuffer<SubNet> dynamicBuffer2 = bufferAccessor6[m];
					for (int n = 0; n < component3.m_SubNets.Length; n++)
					{
						ObjectSubNetInfo objectSubNetInfo = component3.m_SubNets[n];
						NetPrefab netPrefab = objectSubNetInfo.m_NetPrefab;
						if (!(netPrefab == null) && m_PrefabSystem.TryGetEntity(netPrefab, out var entity2))
						{
							SubNet elem2 = new SubNet
							{
								m_Prefab = entity2,
								m_Curve = objectSubNetInfo.m_BezierCurve,
								m_NodeIndex = objectSubNetInfo.m_NodeIndex,
								m_InvertMode = component3.m_InvertWhen,
								m_ParentMesh = objectSubNetInfo.m_ParentMesh
							};
							if (MathUtils.Min(objectSubNetInfo.m_BezierCurve).y <= -2f)
							{
								flag7 = true;
							}
							NetCompositionHelpers.GetRequirementFlags(objectSubNetInfo.m_Upgrades, out elem2.m_Upgrades, out var sectionFlags);
							if (sectionFlags != 0)
							{
								COSystemBase.baseLog.ErrorFormat(prefab2, "ObjectSubNets ({0}[{1}]) cannot upgrade section flags: {2}", prefab2.name, n, sectionFlags);
							}
							dynamicBuffer2.Add(elem2);
						}
					}
					if (flag7)
					{
						if (nativeArray3.Length != 0)
						{
							PlaceableObjectData value3 = nativeArray3[m];
							value3.m_Flags |= Game.Objects.PlacementFlags.HasUndergroundElements;
							nativeArray3[m] = value3;
						}
						if (nativeArray12.Length != 0)
						{
							BuildingExtensionData value4 = nativeArray12[m];
							value4.m_HasUndergroundElements = true;
							nativeArray12[m] = value4;
						}
					}
				}
				for (int num = 0; num < bufferAccessor7.Length; num++)
				{
					ObjectSubLanes component4 = m_PrefabSystem.GetPrefab<ObjectPrefab>(nativeArray[num]).GetComponent<ObjectSubLanes>();
					if (component4.m_SubLanes == null)
					{
						continue;
					}
					DynamicBuffer<SubLane> dynamicBuffer3 = bufferAccessor7[num];
					for (int num2 = 0; num2 < component4.m_SubLanes.Length; num2++)
					{
						ObjectSubLaneInfo objectSubLaneInfo = component4.m_SubLanes[num2];
						NetLanePrefab lanePrefab = objectSubLaneInfo.m_LanePrefab;
						if (!(lanePrefab == null) && m_PrefabSystem.TryGetEntity(lanePrefab, out var entity3))
						{
							dynamicBuffer3.Add(new SubLane
							{
								m_Prefab = entity3,
								m_Curve = objectSubLaneInfo.m_BezierCurve,
								m_NodeIndex = objectSubLaneInfo.m_NodeIndex,
								m_ParentMesh = objectSubLaneInfo.m_ParentMesh
							});
						}
					}
				}
				if (bufferAccessor2.Length != 0)
				{
					BufferAccessor<SubAreaNode> bufferAccessor8 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle8);
					for (int num3 = 0; num3 < bufferAccessor2.Length; num3++)
					{
						ObjectSubAreas component5 = m_PrefabSystem.GetPrefab<ObjectPrefab>(nativeArray[num3]).GetComponent<ObjectSubAreas>();
						if (component5.m_SubAreas == null)
						{
							continue;
						}
						int num4 = 0;
						for (int num5 = 0; num5 < component5.m_SubAreas.Length; num5++)
						{
							ObjectSubAreaInfo objectSubAreaInfo = component5.m_SubAreas[num5];
							if (!(objectSubAreaInfo.m_AreaPrefab == null) && m_PrefabSystem.TryGetEntity(objectSubAreaInfo.m_AreaPrefab, out var _))
							{
								num4 += objectSubAreaInfo.m_NodePositions.Length;
							}
						}
						DynamicBuffer<SubArea> dynamicBuffer4 = bufferAccessor2[num3];
						DynamicBuffer<SubAreaNode> dynamicBuffer5 = bufferAccessor8[num3];
						dynamicBuffer4.EnsureCapacity(component5.m_SubAreas.Length);
						dynamicBuffer5.ResizeUninitialized(num4);
						num4 = 0;
						for (int num6 = 0; num6 < component5.m_SubAreas.Length; num6++)
						{
							ObjectSubAreaInfo objectSubAreaInfo2 = component5.m_SubAreas[num6];
							if (objectSubAreaInfo2.m_AreaPrefab == null || !m_PrefabSystem.TryGetEntity(objectSubAreaInfo2.m_AreaPrefab, out var entity5))
							{
								continue;
							}
							elem3.m_Prefab = entity5;
							elem3.m_NodeRange.x = num4;
							if (objectSubAreaInfo2.m_ParentMeshes != null && objectSubAreaInfo2.m_ParentMeshes.Length != 0)
							{
								for (int num7 = 0; num7 < objectSubAreaInfo2.m_NodePositions.Length; num7++)
								{
									float3 position = objectSubAreaInfo2.m_NodePositions[num7];
									int parentMesh = objectSubAreaInfo2.m_ParentMeshes[num7];
									dynamicBuffer5[num4++] = new SubAreaNode(position, parentMesh);
								}
							}
							else
							{
								for (int num8 = 0; num8 < objectSubAreaInfo2.m_NodePositions.Length; num8++)
								{
									float3 position2 = objectSubAreaInfo2.m_NodePositions[num8];
									int parentMesh2 = -1;
									dynamicBuffer5[num4++] = new SubAreaNode(position2, parentMesh2);
								}
							}
							elem3.m_NodeRange.y = num4;
							dynamicBuffer4.Add(elem3);
						}
					}
				}
				if (nativeArray4.Length == 0)
				{
					continue;
				}
				NativeArray<Entity> nativeArray13 = archetypeChunk.GetNativeArray(entityTypeHandle);
				for (int num9 = 0; num9 < nativeArray4.Length; num9++)
				{
					Entity obj = nativeArray13[num9];
					SpawnableObjectData value5 = nativeArray4[num9];
					SpawnableObject component6 = m_PrefabSystem.GetPrefab<ObjectPrefab>(nativeArray[num9]).GetComponent<SpawnableObject>();
					if (component6.m_Placeholders != null)
					{
						for (int num10 = 0; num10 < component6.m_Placeholders.Length; num10++)
						{
							ObjectPrefab objectPrefab2 = component6.m_Placeholders[num10];
							if (!(objectPrefab2 == null) && m_PrefabSystem.TryGetEntity(objectPrefab2, out var entity6))
							{
								base.EntityManager.GetBuffer<PlaceholderObjectElement>(entity6).Add(new PlaceholderObjectElement(obj));
							}
						}
					}
					if (component6.m_RandomizationGroup != null)
					{
						value5.m_RandomizationGroup = m_PrefabSystem.GetEntity(component6.m_RandomizationGroup);
					}
					value5.m_Probability = component6.m_Probability;
					nativeArray4[num9] = value5;
				}
			}
			JobHandle dependsOn = default(JobHandle);
			if (flag)
			{
				dependsOn = JobChunkExtensions.ScheduleParallel(new FixPlaceholdersJob
				{
					m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PlaceholderObjectElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RW_BufferTypeHandle, ref base.CheckedStateRef)
				}, m_PlaceholderQuery, base.Dependency);
			}
			FindPlaceholderRequirementsJob jobData = new FindPlaceholderRequirementsJob
			{
				m_Chunks = chunks,
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PlaceholderObjectElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PlaceholderObjectDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ObjectRequirementElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ObjectRequirementElement_RO_BufferLookup, ref base.CheckedStateRef)
			};
			FindSubObjectRequirementsJob jobData2 = new FindSubObjectRequirementsJob
			{
				m_Chunks = chunks,
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ObjectGeometryDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PlaceholderObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef)
			};
			InitializeSubNetsJob jobData3 = new InitializeSubNetsJob
			{
				m_Chunks = chunks,
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PlaceableObjectDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubNetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubNet_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef)
			};
			JobHandle job = IJobParallelForExtensions.Schedule(dependsOn: IJobParallelForExtensions.Schedule(jobData, chunks.Length, 1, dependsOn), jobData: jobData2, arrayLength: chunks.Length, innerloopBatchCount: 1);
			JobHandle job2 = IJobParallelForExtensions.Schedule(jobData3, chunks.Length, 1);
			base.Dependency = JobHandle.CombineDependencies(job, job2);
		}
		finally
		{
			chunks.Dispose(base.Dependency);
		}
	}
```

- `private UpdateStackBounds(Colossal.Mathematics.Bounds1& stackBounds, Colossal.Mathematics.Bounds3& meshBounds, Game.Prefabs.StackProperties properties) : System.Void`  

```csharp
private void UpdateStackBounds(ref Bounds1 stackBounds, ref Bounds3 meshBounds, StackProperties properties)
	{
		switch (properties.m_Direction)
		{
		case StackDirection.Right:
			stackBounds |= new Bounds1(meshBounds.min.x + properties.m_StartOverlap, meshBounds.max.x - properties.m_EndOverlap);
			meshBounds.min.x = ((properties.m_Order == StackOrder.First) ? math.min(meshBounds.min.x, 0f) : 0f);
			meshBounds.max.x = ((properties.m_Order == StackOrder.Last) ? math.max(meshBounds.max.x, 0f) : 0f);
			break;
		case StackDirection.Up:
			stackBounds |= new Bounds1(meshBounds.min.y + properties.m_StartOverlap, meshBounds.max.y - properties.m_EndOverlap);
			meshBounds.min.y = ((properties.m_Order == StackOrder.First) ? math.min(meshBounds.min.y, 0f) : 0f);
			meshBounds.max.y = ((properties.m_Order == StackOrder.Last) ? math.max(meshBounds.max.y, 0f) : 0f);
			break;
		case StackDirection.Forward:
			stackBounds |= new Bounds1(meshBounds.min.z + properties.m_StartOverlap, meshBounds.max.z - properties.m_EndOverlap);
			meshBounds.min.z = ((properties.m_Order == StackOrder.First) ? math.min(meshBounds.min.z, 0f) : 0f);
			meshBounds.max.z = ((properties.m_Order == StackOrder.Last) ? math.max(meshBounds.max.z, 0f) : 0f);
			break;
		}
	}
```


## Nested types

- `Game.Prefabs.ObjectInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.ObjectInitializeSystem+InitializeSubNetsJob`  
- `Game.Prefabs.ObjectInitializeSystem+FindPlaceholderRequirementsJob`  
- `Game.Prefabs.ObjectInitializeSystem+FindSubObjectRequirementsJob`  
- `Game.Prefabs.ObjectInitializeSystem+TypeHandle`  

