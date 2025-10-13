# Game.Prefabs.BuildingInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Prefabs.BuildingInitializeSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_547773813_0;
    private static Colossal.Logging.ILog log;

    public BuildingInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void InitializeLotSize(Game.Prefabs.BuildingPrefab buildingPrefab, Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Game.Prefabs.BuildingData& buildingData);
    public static System.Void InitializeTerraformData(Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Colossal.Mathematics.Bounds2 lotBounds, Colossal.Mathematics.Bounds2 flatBounds);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Prefabs.BuildingInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.BuildingInitializeSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_547773813_0`  

```csharp
private Unity.Entities.EntityQuery __query_547773813_0;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```


## Constructors

- `public BuildingInitializeSystem()`  

```csharp
[Preserve]
	public BuildingInitializeSystem()
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
		__query_547773813_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `private InitializeLotSize(Game.Prefabs.BuildingPrefab buildingPrefab, Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.ObjectGeometryData& objectGeometryData, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Game.Prefabs.BuildingData& buildingData) : System.Void`  

```csharp
private void InitializeLotSize(BuildingPrefab buildingPrefab, BuildingTerraformOverride terraformOverride, ref ObjectGeometryData objectGeometryData, ref BuildingTerraformData buildingTerraformData, ref BuildingData buildingData)
	{
		buildingData.m_LotSize = new int2(buildingPrefab.m_LotWidth, buildingPrefab.m_LotDepth);
		float2 @float = new float2(buildingPrefab.m_LotWidth, buildingPrefab.m_LotDepth);
		@float *= 8f;
		bool flag = false;
		Bounds2 flatBounds;
		if ((objectGeometryData.m_Flags & Game.Objects.GeometryFlags.Standing) != Game.Objects.GeometryFlags.None)
		{
			int2 @int = default(int2);
			@int.x = Mathf.RoundToInt((objectGeometryData.m_LegSize.x + objectGeometryData.m_LegOffset.x * 2f) / 8f);
			@int.y = Mathf.RoundToInt((objectGeometryData.m_LegSize.z + objectGeometryData.m_LegOffset.y * 2f) / 8f);
			flag = math.all(@int == buildingData.m_LotSize);
			buildingData.m_LotSize = @int;
			float2 xz = objectGeometryData.m_Pivot.xz;
			float2 float2 = objectGeometryData.m_LegSize.xz * 0.5f + objectGeometryData.m_LegOffset;
			flatBounds = new Bounds2(xz - float2, xz + float2);
			objectGeometryData.m_LegSize.xz = (float2)@int * 8f - objectGeometryData.m_LegOffset * 2f - 0.4f;
		}
		else
		{
			flatBounds = objectGeometryData.m_Bounds.xz;
		}
		Bounds2 lotBounds = default(Bounds2);
		lotBounds.max = (float2)buildingData.m_LotSize * 4f;
		lotBounds.min = -lotBounds.max;
		InitializeTerraformData(terraformOverride, ref buildingTerraformData, lotBounds, flatBounds);
		objectGeometryData.m_Layers |= MeshLayer.Default;
		objectGeometryData.m_MinLod = math.min(objectGeometryData.m_MinLod, RenderingUtils.CalculateLodLimit(RenderingUtils.GetRenderingSize(new float3(@float.x, 0f, @float.y))));
		switch (buildingPrefab.m_AccessType)
		{
		case BuildingAccessType.LeftCorner:
			buildingData.m_Flags |= BuildingFlags.LeftAccess;
			break;
		case BuildingAccessType.RightCorner:
			buildingData.m_Flags |= BuildingFlags.RightAccess;
			break;
		case BuildingAccessType.LeftAndRightCorner:
			buildingData.m_Flags |= BuildingFlags.LeftAccess | BuildingFlags.RightAccess;
			break;
		case BuildingAccessType.LeftAndBackCorner:
			buildingData.m_Flags |= BuildingFlags.LeftAccess | BuildingFlags.BackAccess;
			break;
		case BuildingAccessType.RightAndBackCorner:
			buildingData.m_Flags |= BuildingFlags.RightAccess | BuildingFlags.BackAccess;
			break;
		case BuildingAccessType.FrontAndBack:
			buildingData.m_Flags |= BuildingFlags.BackAccess;
			break;
		case BuildingAccessType.All:
			buildingData.m_Flags |= BuildingFlags.LeftAccess | BuildingFlags.RightAccess | BuildingFlags.BackAccess;
			break;
		}
		if (!flag)
		{
			if (math.any(objectGeometryData.m_Size.xz > @float + 0.5f) && AssetDatabase.global.AreAssetsWarningsEnabled(buildingPrefab.asset))
			{
				log.WarnFormat("Building geometry doesn't fit inside the lot ({0}): {1}m x {2}m ({3}x{4})", buildingPrefab.name, objectGeometryData.m_Size.x, objectGeometryData.m_Size.z, buildingData.m_LotSize.x, buildingData.m_LotSize.y);
			}
			@float -= 0.4f;
			objectGeometryData.m_Size.xz = @float;
			objectGeometryData.m_Bounds.min.xz = @float * -0.5f;
			objectGeometryData.m_Bounds.max.xz = @float * 0.5f;
		}
		objectGeometryData.m_Size.y = math.max(objectGeometryData.m_Size.y, 5f);
		objectGeometryData.m_Bounds.min.y = math.min(objectGeometryData.m_Bounds.min.y, 0f);
		objectGeometryData.m_Bounds.max.y = math.max(objectGeometryData.m_Bounds.max.y, 5f);
	}
```

- `public static InitializeTerraformData(Game.Prefabs.BuildingTerraformOverride terraformOverride, Game.Prefabs.BuildingTerraformData& buildingTerraformData, Colossal.Mathematics.Bounds2 lotBounds, Colossal.Mathematics.Bounds2 flatBounds) : System.Void`  

```csharp
public static void InitializeTerraformData(BuildingTerraformOverride terraformOverride, ref BuildingTerraformData buildingTerraformData, Bounds2 lotBounds, Bounds2 flatBounds)
	{
		float3 @float = new float3(1f, 0f, 1f);
		float3 float2 = new float3(1f, 0f, 1f);
		float3 float3 = new float3(1f, 0f, 1f);
		float3 float4 = new float3(1f, 0f, 1f);
		buildingTerraformData.m_Smooth.xy = lotBounds.min;
		buildingTerraformData.m_Smooth.zw = lotBounds.max;
		if (terraformOverride != null)
		{
			flatBounds.min += terraformOverride.m_LevelMinOffset;
			flatBounds.max += terraformOverride.m_LevelMaxOffset;
			@float.x = terraformOverride.m_LevelBackRight.x;
			@float.z = terraformOverride.m_LevelFrontRight.x;
			float2.x = terraformOverride.m_LevelBackRight.y;
			float2.z = terraformOverride.m_LevelBackLeft.y;
			float3.x = terraformOverride.m_LevelBackLeft.x;
			float3.z = terraformOverride.m_LevelFrontLeft.x;
			float4.x = terraformOverride.m_LevelFrontRight.y;
			float4.z = terraformOverride.m_LevelFrontLeft.y;
			buildingTerraformData.m_Smooth.xy += terraformOverride.m_SmoothMinOffset;
			buildingTerraformData.m_Smooth.zw += terraformOverride.m_SmoothMaxOffset;
			buildingTerraformData.m_HeightOffset = terraformOverride.m_HeightOffset;
			buildingTerraformData.m_DontRaise = terraformOverride.m_DontRaise;
			buildingTerraformData.m_DontLower = terraformOverride.m_DontLower;
		}
		float3 float5 = flatBounds.min.x + @float;
		float3 float6 = flatBounds.min.y + float2;
		float3 float7 = flatBounds.max.x - float3;
		float3 float8 = flatBounds.max.y - float4;
		float3 x = (float5 + float7) * 0.5f;
		float3 x2 = (float6 + float8) * 0.5f;
		buildingTerraformData.m_FlatX0 = math.min(float5, math.max(x, float7));
		buildingTerraformData.m_FlatZ0 = math.min(float6, math.max(x2, float8));
		buildingTerraformData.m_FlatX1 = math.max(float7, math.min(x, float5));
		buildingTerraformData.m_FlatZ1 = math.max(float8, math.min(x2, float6));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		log = LogManager.GetLogger("Simulation");
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadWrite<BuildingData>(),
				ComponentType.ReadWrite<BuildingExtensionData>(),
				ComponentType.ReadWrite<ServiceUpgradeData>(),
				ComponentType.ReadWrite<SpawnableBuildingData>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadWrite<ServiceUpgradeData>()
			}
		});
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
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
		EntityCommandBuffer entityCommandBuffer = new EntityCommandBuffer(Allocator.TempJob, PlaybackPolicy.SinglePlayback);
		NativeArray<ArchetypeChunk> chunks = m_PrefabQuery.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Deleted> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PrefabData> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<BuildingData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<BuildingExtensionData> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<BuildingTerraformData> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingTerraformData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<ConsumptionData> typeHandle6 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<ObjectGeometryData> typeHandle7 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<SpawnableBuildingData> typeHandle8 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<SignatureBuildingData> typeHandle9 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<PlaceableObjectData> typeHandle10 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<ServiceUpgradeData> typeHandle11 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<BuildingPropertyData> typeHandle12 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<WaterPoweredData> typeHandle13 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterPoweredData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<SewageOutletData> typeHandle14 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SewageOutletData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<ServiceUpgradeBuilding> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeBuilding_RO_BufferTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<CollectedServiceBuildingBudgetData> typeHandle15 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_CollectedServiceBuildingBudgetData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<ServiceUpkeepData> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_ServiceUpkeepData_RW_BufferTypeHandle, ref base.CheckedStateRef);
		ComponentLookup<ZoneData> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RW_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<ZoneServiceConsumptionData> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneServiceConsumptionData_RO_ComponentLookup, ref base.CheckedStateRef);
		CompleteDependency();
		for (int i = 0; i < chunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = chunks[i];
			NativeArray<Entity> nativeArray = archetypeChunk.GetNativeArray(entityTypeHandle);
			BufferAccessor<ServiceUpgradeBuilding> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
			if (archetypeChunk.Has(ref typeHandle))
			{
				if (bufferAccessor.Length == 0)
				{
					continue;
				}
				for (int j = 0; j < bufferAccessor.Length; j++)
				{
					Entity upgrade = nativeArray[j];
					DynamicBuffer<ServiceUpgradeBuilding> dynamicBuffer = bufferAccessor[j];
					for (int k = 0; k < dynamicBuffer.Length; k++)
					{
						ServiceUpgradeBuilding serviceUpgradeBuilding = dynamicBuffer[k];
						CollectionUtils.RemoveValue(base.EntityManager.GetBuffer<BuildingUpgradeElement>(serviceUpgradeBuilding.m_Building), new BuildingUpgradeElement(upgrade));
					}
				}
				continue;
			}
			NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle2);
			NativeArray<ObjectGeometryData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle7);
			NativeArray<BuildingData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle3);
			NativeArray<BuildingExtensionData> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle4);
			NativeArray<ConsumptionData> nativeArray6 = archetypeChunk.GetNativeArray(ref typeHandle6);
			NativeArray<SpawnableBuildingData> nativeArray7 = archetypeChunk.GetNativeArray(ref typeHandle8);
			NativeArray<PlaceableObjectData> nativeArray8 = archetypeChunk.GetNativeArray(ref typeHandle10);
			NativeArray<ServiceUpgradeData> nativeArray9 = archetypeChunk.GetNativeArray(ref typeHandle11);
			NativeArray<BuildingPropertyData> nativeArray10 = archetypeChunk.GetNativeArray(ref typeHandle12);
			BufferAccessor<ServiceUpkeepData> bufferAccessor2 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle2);
			bool flag = archetypeChunk.Has(ref typeHandle15);
			bool flag2 = archetypeChunk.Has(ref typeHandle9);
			bool flag3 = archetypeChunk.Has(ref typeHandle13);
			bool flag4 = archetypeChunk.Has(ref typeHandle14);
			if (nativeArray4.Length != 0)
			{
				NativeArray<BuildingTerraformData> nativeArray11 = archetypeChunk.GetNativeArray(ref typeHandle5);
				for (int l = 0; l < nativeArray4.Length; l++)
				{
					BuildingPrefab prefab = m_PrefabSystem.GetPrefab<BuildingPrefab>(nativeArray2[l]);
					BuildingTerraformOverride component = prefab.GetComponent<BuildingTerraformOverride>();
					ObjectGeometryData objectGeometryData = nativeArray3[l];
					BuildingTerraformData buildingTerraformData = nativeArray11[l];
					BuildingData buildingData = nativeArray4[l];
					InitializeLotSize(prefab, component, ref objectGeometryData, ref buildingTerraformData, ref buildingData);
					if (nativeArray7.Length != 0 && !flag2)
					{
						objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.DeleteOverridden;
					}
					else
					{
						objectGeometryData.m_Flags &= ~Game.Objects.GeometryFlags.Overridable;
						objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.OverrideZone;
					}
					if (flag3)
					{
						objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.CanSubmerge;
					}
					else if (flag4 && prefab.GetComponent<SewageOutlet>().m_AllowSubmerged)
					{
						objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.CanSubmerge;
					}
					objectGeometryData.m_Flags &= ~Game.Objects.GeometryFlags.Brushable;
					objectGeometryData.m_Flags |= Game.Objects.GeometryFlags.ExclusiveGround | Game.Objects.GeometryFlags.WalkThrough | Game.Objects.GeometryFlags.OccupyZone | Game.Objects.GeometryFlags.HasLot;
					if (CollectionUtils.TryGet(nativeArray8, l, out var value) && (value.m_Flags & (Game.Objects.PlacementFlags.OnGround | Game.Objects.PlacementFlags.Floating | Game.Objects.PlacementFlags.Swaying)) == (Game.Objects.PlacementFlags.Floating | Game.Objects.PlacementFlags.Swaying))
					{
						objectGeometryData.m_Flags &= ~(Game.Objects.GeometryFlags.ExclusiveGround | Game.Objects.GeometryFlags.OccupyZone);
					}
					nativeArray3[l] = objectGeometryData;
					nativeArray11[l] = buildingTerraformData;
					nativeArray4[l] = buildingData;
				}
			}
			if (nativeArray5.Length != 0)
			{
				NativeArray<BuildingTerraformData> nativeArray12 = archetypeChunk.GetNativeArray(ref typeHandle5);
				for (int m = 0; m < nativeArray5.Length; m++)
				{
					BuildingExtensionPrefab prefab2 = m_PrefabSystem.GetPrefab<BuildingExtensionPrefab>(nativeArray2[m]);
					ObjectGeometryData value2 = nativeArray3[m];
					Bounds2 flatBounds;
					if ((value2.m_Flags & Game.Objects.GeometryFlags.Standing) != Game.Objects.GeometryFlags.None)
					{
						float2 xz = value2.m_Pivot.xz;
						float2 @float = value2.m_LegSize.xz * 0.5f + value2.m_LegOffset;
						flatBounds = new Bounds2(xz - @float, xz + @float);
					}
					else
					{
						flatBounds = value2.m_Bounds.xz;
					}
					value2.m_Bounds.min = math.min(value2.m_Bounds.min, new float3(-0.5f, 0f, -0.5f));
					value2.m_Bounds.max = math.max(value2.m_Bounds.max, new float3(0.5f, 5f, 0.5f));
					value2.m_Flags &= ~(Game.Objects.GeometryFlags.Overridable | Game.Objects.GeometryFlags.Brushable);
					value2.m_Flags |= Game.Objects.GeometryFlags.ExclusiveGround | Game.Objects.GeometryFlags.WalkThrough | Game.Objects.GeometryFlags.OccupyZone | Game.Objects.GeometryFlags.HasLot;
					BuildingExtensionData value3 = nativeArray5[m];
					value3.m_Position = prefab2.m_Position;
					value3.m_LotSize = prefab2.m_OverrideLotSize;
					value3.m_External = prefab2.m_ExternalLot;
					if (prefab2.m_OverrideHeight > 0f)
					{
						value2.m_Bounds.max.y = prefab2.m_OverrideHeight;
					}
					Bounds2 lotBounds;
					if (math.all(value3.m_LotSize > 0))
					{
						float2 float2 = value3.m_LotSize;
						float2 *= 8f;
						lotBounds = new Bounds2(float2 * -0.5f, float2 * 0.5f);
						float2 -= 0.4f;
						value2.m_Bounds.min.xz = float2 * -0.5f;
						value2.m_Bounds.max.xz = float2 * 0.5f;
						if (bufferAccessor.Length != 0)
						{
							value2.m_Flags |= Game.Objects.GeometryFlags.OverrideZone;
						}
					}
					else
					{
						Bounds3 bounds = value2.m_Bounds;
						lotBounds = value2.m_Bounds.xz;
						if (bufferAccessor.Length != 0)
						{
							DynamicBuffer<ServiceUpgradeBuilding> dynamicBuffer2 = bufferAccessor[m];
							for (int n = 0; n < dynamicBuffer2.Length; n++)
							{
								ServiceUpgradeBuilding serviceUpgradeBuilding2 = dynamicBuffer2[n];
								BuildingPrefab prefab3 = m_PrefabSystem.GetPrefab<BuildingPrefab>(serviceUpgradeBuilding2.m_Building);
								float2 float3 = new int2(prefab3.m_LotWidth, prefab3.m_LotDepth);
								float3 *= 8f;
								float2 float4 = float3;
								float3 -= 0.4f;
								if ((value2.m_Flags & Game.Objects.GeometryFlags.Standing) == 0 && prefab3.TryGet<StandingObject>(out var component2))
								{
									float3 = component2.m_LegSize.xz + math.select(default(float2), component2.m_LegSize.xz + component2.m_LegGap, component2.m_LegGap != 0f);
									float3 -= 0.4f;
									float4 = float3;
									if (component2.m_CircularLeg)
									{
										value2.m_Flags |= Game.Objects.GeometryFlags.Circular;
									}
								}
								if (n == 0)
								{
									bounds.xz = new Bounds2(float3 * -0.5f, float3 * 0.5f) - prefab2.m_Position.xz;
									lotBounds = new Bounds2(float4 * -0.5f, float4 * 0.5f) - prefab2.m_Position.xz;
								}
								else
								{
									bounds.xz &= new Bounds2(float3 * -0.5f, float3 * 0.5f) - prefab2.m_Position.xz;
									lotBounds &= new Bounds2(float4 * -0.5f, float4 * 0.5f) - prefab2.m_Position.xz;
								}
							}
							value2.m_Bounds.xz = bounds.xz;
							value2.m_Flags |= Game.Objects.GeometryFlags.OverrideZone;
						}
						float2 float5 = math.min(-bounds.min.xz, bounds.max.xz) * 0.25f - 0.01f;
						value3.m_LotSize.x = math.max(1, Mathf.CeilToInt(float5.x));
						value3.m_LotSize.y = math.max(1, Mathf.CeilToInt(float5.y));
					}
					if (value3.m_External)
					{
						float2 float6 = value3.m_LotSize;
						float6 *= 8f;
						value2.m_Layers |= MeshLayer.Default;
						value2.m_MinLod = math.min(value2.m_MinLod, RenderingUtils.CalculateLodLimit(RenderingUtils.GetRenderingSize(new float3(float6.x, 0f, float6.y))));
					}
					if (nativeArray12.Length != 0)
					{
						BuildingTerraformOverride component3 = prefab2.GetComponent<BuildingTerraformOverride>();
						BuildingTerraformData buildingTerraformData2 = nativeArray12[m];
						InitializeTerraformData(component3, ref buildingTerraformData2, lotBounds, flatBounds);
						nativeArray12[m] = buildingTerraformData2;
					}
					value2.m_Size = math.max(ObjectUtils.GetSize(value2.m_Bounds), new float3(1f, 5f, 1f));
					nativeArray3[m] = value2;
					nativeArray5[m] = value3;
				}
			}
			if (nativeArray7.Length != 0)
			{
				for (int num = 0; num < nativeArray7.Length; num++)
				{
					Entity e = nativeArray[num];
					BuildingPrefab prefab4 = m_PrefabSystem.GetPrefab<BuildingPrefab>(nativeArray2[num]);
					BuildingPropertyData buildingPropertyData = ((nativeArray10.Length != 0) ? nativeArray10[num] : default(BuildingPropertyData));
					SpawnableBuildingData spawnableBuildingData = nativeArray7[num];
					if (!(spawnableBuildingData.m_ZonePrefab != Entity.Null))
					{
						continue;
					}
					Entity zonePrefab = spawnableBuildingData.m_ZonePrefab;
					ZoneData value4 = componentLookup[zonePrefab];
					if (!flag2)
					{
						entityCommandBuffer.SetSharedComponent(e, new BuildingSpawnGroupData(value4.m_ZoneType));
						ushort num2 = (ushort)math.clamp(Mathf.CeilToInt(nativeArray3[num].m_Size.y), 0, 65535);
						if (spawnableBuildingData.m_Level == 1)
						{
							if (prefab4.m_LotWidth == 1 && (value4.m_ZoneFlags & ZoneFlags.SupportNarrow) == 0)
							{
								value4.m_ZoneFlags |= ZoneFlags.SupportNarrow;
								componentLookup[zonePrefab] = value4;
							}
							if (prefab4.m_AccessType == BuildingAccessType.LeftCorner && (value4.m_ZoneFlags & ZoneFlags.SupportLeftCorner) == 0)
							{
								value4.m_ZoneFlags |= ZoneFlags.SupportLeftCorner;
								componentLookup[zonePrefab] = value4;
							}
							if (prefab4.m_AccessType == BuildingAccessType.RightCorner && (value4.m_ZoneFlags & ZoneFlags.SupportRightCorner) == 0)
							{
								value4.m_ZoneFlags |= ZoneFlags.SupportRightCorner;
								componentLookup[zonePrefab] = value4;
							}
							if (prefab4.m_AccessType == BuildingAccessType.Front && prefab4.m_LotWidth <= 3 && prefab4.m_LotDepth <= 2)
							{
								if ((prefab4.m_LotWidth == 1 || prefab4.m_LotWidth == 3) && num2 < value4.m_MinOddHeight)
								{
									value4.m_MinOddHeight = num2;
									componentLookup[zonePrefab] = value4;
								}
								if ((prefab4.m_LotWidth == 1 || prefab4.m_LotWidth == 2) && num2 < value4.m_MinEvenHeight)
								{
									value4.m_MinEvenHeight = num2;
									componentLookup[zonePrefab] = value4;
								}
							}
						}
						if (num2 > value4.m_MaxHeight)
						{
							value4.m_MaxHeight = num2;
							componentLookup[zonePrefab] = value4;
						}
					}
					int level = spawnableBuildingData.m_Level;
					BuildingData buildingData2 = nativeArray4[num];
					int lotSize = buildingData2.m_LotSize.x * buildingData2.m_LotSize.y;
					if (nativeArray6.Length != 0 && !prefab4.Has<ServiceConsumption>() && componentLookup2.HasComponent(zonePrefab))
					{
						ZoneServiceConsumptionData zoneServiceConsumptionData = componentLookup2[zonePrefab];
						ref ConsumptionData reference = ref nativeArray6.ElementAt(num);
						if (flag2)
						{
							level = 2;
						}
						bool isStorage = buildingPropertyData.m_AllowedStored != Resource.NoResource;
						EconomyParameterData economyParameterData = __query_547773813_0.GetSingleton<EconomyParameterData>();
						reference.m_Upkeep = PropertyRenterSystem.GetUpkeep(level, zoneServiceConsumptionData.m_Upkeep, lotSize, value4.m_AreaType, ref economyParameterData, isStorage);
					}
				}
			}
			if (nativeArray8.Length != 0)
			{
				if (nativeArray9.Length != 0)
				{
					for (int num3 = 0; num3 < nativeArray8.Length; num3++)
					{
						PlaceableObjectData value5 = nativeArray8[num3];
						ObjectGeometryData value6 = nativeArray3[num3];
						ServiceUpgradeData serviceUpgradeData = nativeArray9[num3];
						if (nativeArray4.Length != 0)
						{
							value5.m_Flags |= Game.Objects.PlacementFlags.OwnerSide;
							if (serviceUpgradeData.m_MaxPlacementDistance != 0f)
							{
								value5.m_Flags |= Game.Objects.PlacementFlags.RoadSide;
							}
						}
						if ((value5.m_Flags & Game.Objects.PlacementFlags.NetObject) != Game.Objects.PlacementFlags.None)
						{
							value6.m_Flags |= Game.Objects.GeometryFlags.IgnoreLegCollision;
							if (nativeArray4.Length != 0)
							{
								BuildingData value7 = nativeArray4[num3];
								value7.m_Flags |= BuildingFlags.CanBeOnRoad;
								nativeArray4[num3] = value7;
							}
							if ((value5.m_Flags & Game.Objects.PlacementFlags.Shoreline) != Game.Objects.PlacementFlags.None)
							{
								value5.m_Flags &= ~(Game.Objects.PlacementFlags.RoadSide | Game.Objects.PlacementFlags.OwnerSide);
							}
						}
						value5.m_ConstructionCost = serviceUpgradeData.m_UpgradeCost;
						nativeArray8[num3] = value5;
						nativeArray3[num3] = value6;
					}
				}
				else
				{
					for (int num4 = 0; num4 < nativeArray8.Length; num4++)
					{
						PlaceableObjectData value8 = nativeArray8[num4];
						ObjectGeometryData value9 = nativeArray3[num4];
						if (nativeArray4.Length != 0)
						{
							value8.m_Flags |= Game.Objects.PlacementFlags.RoadSide;
						}
						if ((value8.m_Flags & Game.Objects.PlacementFlags.NetObject) != Game.Objects.PlacementFlags.None)
						{
							value9.m_Flags |= Game.Objects.GeometryFlags.IgnoreLegCollision;
							if (nativeArray4.Length != 0)
							{
								BuildingData value10 = nativeArray4[num4];
								value10.m_Flags |= BuildingFlags.CanBeOnRoad;
								nativeArray4[num4] = value10;
							}
							if ((value8.m_Flags & Game.Objects.PlacementFlags.Shoreline) != Game.Objects.PlacementFlags.None)
							{
								value8.m_Flags &= ~Game.Objects.PlacementFlags.RoadSide;
							}
						}
						nativeArray8[num4] = value8;
						nativeArray3[num4] = value9;
					}
				}
			}
			bool flag5 = false;
			if (flag)
			{
				for (int num5 = 0; num5 < nativeArray.Length; num5++)
				{
					if (nativeArray6.Length == 0 || nativeArray6[num5].m_Upkeep <= 0)
					{
						continue;
					}
					bool flag6 = false;
					DynamicBuffer<ServiceUpkeepData> dynamicBuffer3 = bufferAccessor2[num5];
					for (int num6 = 0; num6 < dynamicBuffer3.Length; num6++)
					{
						if (dynamicBuffer3[num6].m_Upkeep.m_Resource == Resource.Money)
						{
							log.WarnFormat("Warning: {0} has monetary upkeep in both ConsumptionData and CityServiceUpkeep", m_PrefabSystem.GetPrefab<PrefabBase>(nativeArray[num5]).name);
						}
					}
					if (!flag6)
					{
						dynamicBuffer3.Add(new ServiceUpkeepData
						{
							m_ScaleWithUsage = false,
							m_Upkeep = new ResourceStack
							{
								m_Amount = nativeArray6[num5].m_Upkeep,
								m_Resource = Resource.Money
							}
						});
						flag5 = true;
					}
				}
			}
			if (bufferAccessor.Length == 0)
			{
				continue;
			}
			for (int num7 = 0; num7 < bufferAccessor.Length; num7++)
			{
				Entity upgrade2 = nativeArray[num7];
				DynamicBuffer<ServiceUpgradeBuilding> dynamicBuffer4 = bufferAccessor[num7];
				for (int num8 = 0; num8 < dynamicBuffer4.Length; num8++)
				{
					ServiceUpgradeBuilding serviceUpgradeBuilding3 = dynamicBuffer4[num8];
					base.EntityManager.GetBuffer<BuildingUpgradeElement>(serviceUpgradeBuilding3.m_Building).Add(new BuildingUpgradeElement(upgrade2));
				}
				if (!flag5 && nativeArray6.Length != 0 && nativeArray6[num7].m_Upkeep > 0)
				{
					bufferAccessor2[num7].Add(new ServiceUpkeepData
					{
						m_ScaleWithUsage = false,
						m_Upkeep = new ResourceStack
						{
							m_Amount = nativeArray6[num7].m_Upkeep,
							m_Resource = Resource.Money
						}
					});
				}
			}
		}
		IJobParallelForExtensions.Schedule(new FindConnectionRequirementsJob
		{
			m_SpawnableBuildingDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceUpgradeDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ExtractorFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ExtractorFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConsumptionDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ConsumptionData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkplaceDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterPumpingStationDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterPumpingStationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterTowerDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterTowerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SewageOutletDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SewageOutletData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WastewaterTreatmentPlantDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WastewaterTreatmentPlantData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformerDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TransformerData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkingFacilityDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ParkingFacilityData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PublicTransportStationDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PublicTransportStationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CargoTransportStationDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CargoTransportStationData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ParkDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ParkData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SubNetType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubNet_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubMeshType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubMesh_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BuildingData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EffectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_Effect_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EffectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VFXData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_VFXData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AudioSourceData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AudioSourceData_RO_BufferLookup, ref base.CheckedStateRef),
			m_AudioSpotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioSpotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AudioEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioEffectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_Chunks = chunks,
			m_BuildingConfigurationData = m_ConfigurationQuery.GetSingleton<BuildingConfigurationData>()
		}, chunks.Length, 1).Complete();
		chunks.Dispose();
		entityCommandBuffer.Playback(base.EntityManager);
		entityCommandBuffer.Dispose();
	}
```


## Nested types

- `Game.Prefabs.BuildingInitializeSystem+FindConnectionRequirementsJob`  
- `Game.Prefabs.BuildingInitializeSystem+TypeHandle`  

