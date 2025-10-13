# Game.Prefabs.NetInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetInitializeSystem : Game.GameSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_PlaceholderQuery;
    private Colossal.Collections.NativeValue<Game.Pathfind.PathfindHeuristicData> m_PathfindHeuristicData;
    private Unity.Jobs.JobHandle m_PathfindHeuristicDeps;
    private Game.Net.Layer m_InGameLayersOnce;
    private Game.Net.Layer m_InGameLayersTwice;
    private Game.Prefabs.NetInitializeSystem+TypeHandle __TypeHandle;

    public NetInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddSections(Game.Prefabs.PrefabBase prefab, Game.Prefabs.NetSectionInfo[] source, Unity.Entities.DynamicBuffer<Game.Prefabs.NetGeometrySection> target, Game.Prefabs.NetSectionFlags flags);
    public System.Boolean CanReplace(Game.Prefabs.NetData netData, System.Boolean inGame);
    public Game.Pathfind.PathfindHeuristicData GetHeuristicData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
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

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_PlaceholderQuery`  

```csharp
private Unity.Entities.EntityQuery m_PlaceholderQuery;
```

- `private Colossal.Collections.NativeValue<Game.Pathfind.PathfindHeuristicData> m_PathfindHeuristicData`  

```csharp
private Colossal.Collections.NativeValue<Game.Pathfind.PathfindHeuristicData> m_PathfindHeuristicData;
```

- `private Unity.Jobs.JobHandle m_PathfindHeuristicDeps`  

```csharp
private Unity.Jobs.JobHandle m_PathfindHeuristicDeps;
```

- `private Game.Net.Layer m_InGameLayersOnce`  

```csharp
private Game.Net.Layer m_InGameLayersOnce;
```

- `private Game.Net.Layer m_InGameLayersTwice`  

```csharp
private Game.Net.Layer m_InGameLayersTwice;
```

- `private Game.Prefabs.NetInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetInitializeSystem()`  

```csharp
[Preserve]
	public NetInitializeSystem()
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

- `private AddSections(Game.Prefabs.PrefabBase prefab, Game.Prefabs.NetSectionInfo[] source, Unity.Entities.DynamicBuffer<Game.Prefabs.NetGeometrySection> target, Game.Prefabs.NetSectionFlags flags) : System.Void`  

```csharp
private void AddSections(PrefabBase prefab, NetSectionInfo[] source, DynamicBuffer<NetGeometrySection> target, NetSectionFlags flags)
	{
		int2 @int = new int2(int.MaxValue, int.MinValue);
		for (int i = 0; i < source.Length; i++)
		{
			if (source[i].m_Median)
			{
				int y = i << 1;
				@int.x = math.min(@int.x, y);
				@int.y = math.max(@int.y, y);
			}
		}
		if (@int.Equals(new int2(int.MaxValue, int.MinValue)))
		{
			@int = source.Length - 1;
			flags |= NetSectionFlags.AlignCenter;
		}
		for (int j = 0; j < source.Length; j++)
		{
			NetSectionInfo netSectionInfo = source[j];
			NetGeometrySection elem = new NetGeometrySection
			{
				m_Section = m_PrefabSystem.GetEntity(netSectionInfo.m_Section),
				m_Offset = netSectionInfo.m_Offset,
				m_Flags = flags
			};
			NetCompositionHelpers.GetRequirementFlags(netSectionInfo.m_RequireAll, out elem.m_CompositionAll, out var sectionFlags);
			NetCompositionHelpers.GetRequirementFlags(netSectionInfo.m_RequireAny, out elem.m_CompositionAny, out var sectionFlags2);
			NetCompositionHelpers.GetRequirementFlags(netSectionInfo.m_RequireNone, out elem.m_CompositionNone, out var sectionFlags3);
			NetSectionFlags netSectionFlags = sectionFlags | sectionFlags2 | sectionFlags3;
			if (netSectionFlags != 0)
			{
				COSystemBase.baseLog.ErrorFormat(prefab, "Net section ({0}: {1}) cannot require section flags: {2}", prefab.name, netSectionInfo.m_Section.name, netSectionFlags);
			}
			if (netSectionInfo.m_Invert)
			{
				elem.m_Flags |= NetSectionFlags.Invert;
			}
			if (netSectionInfo.m_Flip)
			{
				elem.m_Flags |= NetSectionFlags.FlipLanes | NetSectionFlags.FlipMesh;
			}
			if (netSectionInfo.m_HalfLength)
			{
				elem.m_Flags |= NetSectionFlags.HalfLength;
			}
			NetPieceLayerMask netPieceLayerMask = NetPieceLayerMask.Surface | NetPieceLayerMask.Bottom | NetPieceLayerMask.Top | NetPieceLayerMask.Side;
			if ((netSectionInfo.m_HiddenLayers & netPieceLayerMask) == netPieceLayerMask)
			{
				elem.m_Flags |= NetSectionFlags.Hidden;
			}
			if ((netSectionInfo.m_HiddenLayers & NetPieceLayerMask.Surface) != 0)
			{
				elem.m_Flags |= NetSectionFlags.HiddenSurface;
			}
			if ((netSectionInfo.m_HiddenLayers & NetPieceLayerMask.Bottom) != 0)
			{
				elem.m_Flags |= NetSectionFlags.HiddenBottom;
			}
			if ((netSectionInfo.m_HiddenLayers & NetPieceLayerMask.Top) != 0)
			{
				elem.m_Flags |= NetSectionFlags.HiddenTop;
			}
			if ((netSectionInfo.m_HiddenLayers & NetPieceLayerMask.Side) != 0)
			{
				elem.m_Flags |= NetSectionFlags.HiddenSide;
			}
			int num = j << 1;
			if (num >= @int.x && num <= @int.y)
			{
				elem.m_Flags |= NetSectionFlags.Median;
			}
			else if (num > @int.y)
			{
				elem.m_Flags |= NetSectionFlags.Right;
			}
			else
			{
				elem.m_Flags |= NetSectionFlags.Left;
			}
			target.Add(elem);
		}
	}
```

- `public CanReplace(Game.Prefabs.NetData netData, System.Boolean inGame) : System.Boolean`  

```csharp
public bool CanReplace(NetData netData, bool inGame)
	{
		if (!inGame)
		{
			return true;
		}
		return (netData.m_RequiredLayers & m_InGameLayersOnce & ~m_InGameLayersTwice) == 0;
	}
```

- `public GetHeuristicData() : Game.Pathfind.PathfindHeuristicData`  

```csharp
public PathfindHeuristicData GetHeuristicData()
	{
		m_PathfindHeuristicDeps.Complete();
		return m_PathfindHeuristicData.value;
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
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadWrite<NetData>(),
				ComponentType.ReadWrite<NetSectionData>(),
				ComponentType.ReadWrite<NetPieceData>(),
				ComponentType.ReadWrite<NetLaneData>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<PrefabData>()
			},
			Any = new ComponentType[1] { ComponentType.ReadWrite<NetLaneData>() }
		});
		m_LaneQuery = GetEntityQuery(ComponentType.ReadOnly<NetLaneData>(), ComponentType.Exclude<Deleted>());
		m_PlaceholderQuery = GetEntityQuery(ComponentType.ReadOnly<NetLaneData>(), ComponentType.ReadOnly<PlaceholderObjectElement>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_PrefabQuery);
		m_PathfindHeuristicData = new NativeValue<PathfindHeuristicData>(Allocator.Persistent);
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
		m_PathfindHeuristicData.Dispose();
		base.OnDestroy();
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
			ComponentTypeHandle<NetData> typeHandle3 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetPieceData> typeHandle4 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetPieceData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetGeometryData> typeHandle5 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PlaceableNetData> typeHandle6 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<MarkerNetData> typeHandle7 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_MarkerNetData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<LocalConnectData> typeHandle8 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetLaneData> typeHandle9 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetLaneGeometryData> typeHandle10 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetLaneGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<CarLaneData> typeHandle11 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CarLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<TrackLaneData> typeHandle12 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<UtilityLaneData> typeHandle13 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<ParkingLaneData> typeHandle14 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PedestrianLaneData> typeHandle15 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PedestrianLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<SecondaryLaneData> typeHandle16 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SecondaryLaneData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetCrosswalkData> typeHandle17 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCrosswalkData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<RoadData> typeHandle18 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_RoadData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<TrackData> typeHandle19 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TrackData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<WaterwayData> typeHandle20 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterwayData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PathwayData> typeHandle21 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PathwayData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<TaxiwayData> typeHandle22 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TaxiwayData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PowerLineData> typeHandle23 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PowerLineData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PipelineData> typeHandle24 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PipelineData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<FenceData> typeHandle25 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_FenceData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<EditorContainerData> typeHandle26 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_EditorContainerData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<ElectricityConnectionData> typeHandle27 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ElectricityConnectionData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<WaterPipeConnectionData> typeHandle28 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterPipeConnectionData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<ResourceConnectionData> typeHandle29 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResourceConnectionData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<BridgeData> typeHandle30 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_BridgeData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<SpawnableObjectData> typeHandle31 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_SpawnableObjectData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<NetTerrainData> typeHandle32 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetTerrainData_RW_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<UIObjectData> typeHandle33 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UIObjectData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetSubSection> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetSubSection_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetSectionPiece> bufferTypeHandle2 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetSectionPiece_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetPieceLane> bufferTypeHandle3 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetPieceLane_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetPieceArea> bufferTypeHandle4 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetPieceArea_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetPieceObject> bufferTypeHandle5 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetPieceObject_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetGeometrySection> bufferTypeHandle6 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometrySection_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetGeometryEdgeState> bufferTypeHandle7 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometryEdgeState_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<NetGeometryNodeState> bufferTypeHandle8 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometryNodeState_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubObject> bufferTypeHandle9 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubObject_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<SubMesh> bufferTypeHandle10 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_SubMesh_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<FixedNetElement> bufferTypeHandle11 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_FixedNetElement_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<AuxiliaryNetLane> bufferTypeHandle12 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_AuxiliaryNetLane_RW_BufferTypeHandle, ref base.CheckedStateRef);
			BufferTypeHandle<AuxiliaryNet> bufferTypeHandle13 = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_AuxiliaryNet_RW_BufferTypeHandle, ref base.CheckedStateRef);
			CompleteDependency();
			FixedNetElement value51 = default(FixedNetElement);
			for (int i = 0; i < chunks.Length; i++)
			{
				ArchetypeChunk archetypeChunk = chunks[i];
				if (archetypeChunk.Has(ref typeHandle))
				{
					flag = archetypeChunk.Has(ref typeHandle31);
					continue;
				}
				NativeArray<Entity> nativeArray = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<PrefabData> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle2);
				bool flag2 = archetypeChunk.Has(ref typeHandle7);
				bool flag3 = archetypeChunk.Has(ref typeHandle30);
				bool flag4 = archetypeChunk.Has(ref typeHandle33);
				NativeArray<NetData> nativeArray3 = archetypeChunk.GetNativeArray(ref typeHandle3);
				NativeArray<NetGeometryData> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle5);
				NativeArray<PlaceableNetData> nativeArray5 = archetypeChunk.GetNativeArray(ref typeHandle6);
				NativeArray<PathwayData> nativeArray6 = archetypeChunk.GetNativeArray(ref typeHandle21);
				if (nativeArray4.Length != 0)
				{
					BufferAccessor<NetGeometrySection> bufferAccessor = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle6);
					for (int j = 0; j < nativeArray4.Length; j++)
					{
						_ = nativeArray[j];
						NetGeometryPrefab prefab = m_PrefabSystem.GetPrefab<NetGeometryPrefab>(nativeArray2[j]);
						NetGeometryData value = nativeArray4[j];
						DynamicBuffer<NetGeometrySection> target = bufferAccessor[j];
						value.m_EdgeLengthRange.max = 200f;
						value.m_ElevatedLength = 80f;
						value.m_MaxSlopeSteepness = math.select(prefab.m_MaxSlopeSteepness, 0f, prefab.m_MaxSlopeSteepness < 0.001f);
						value.m_ElevationLimit = 4f;
						if (prefab.m_AggregateType != null)
						{
							value.m_AggregateType = m_PrefabSystem.GetEntity(prefab.m_AggregateType);
						}
						if (prefab.m_StyleType != null)
						{
							value.m_StyleType = m_PrefabSystem.GetEntity(prefab.m_StyleType);
						}
						if (flag2)
						{
							value.m_Flags |= GeometryFlags.Marker;
						}
						AddSections(prefab, prefab.m_Sections, target, (NetSectionFlags)0);
						UndergroundNetSections component = prefab.GetComponent<UndergroundNetSections>();
						if (component != null)
						{
							AddSections(prefab, component.m_Sections, target, NetSectionFlags.Underground);
						}
						OverheadNetSections component2 = prefab.GetComponent<OverheadNetSections>();
						if (component2 != null)
						{
							AddSections(prefab, component2.m_Sections, target, NetSectionFlags.Overhead);
						}
						switch (prefab.m_InvertMode)
						{
						case CompositionInvertMode.InvertLefthandTraffic:
							value.m_Flags |= GeometryFlags.InvertCompositionHandedness;
							break;
						case CompositionInvertMode.FlipLefthandTraffic:
							value.m_Flags |= GeometryFlags.FlipCompositionHandedness;
							break;
						case CompositionInvertMode.InvertRighthandTraffic:
							value.m_Flags |= GeometryFlags.IsLefthanded | GeometryFlags.InvertCompositionHandedness;
							break;
						case CompositionInvertMode.FlipRighthandTraffic:
							value.m_Flags |= GeometryFlags.IsLefthanded | GeometryFlags.FlipCompositionHandedness;
							break;
						}
						nativeArray4[j] = value;
					}
					BufferAccessor<NetGeometryEdgeState> bufferAccessor2 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle7);
					BufferAccessor<NetGeometryNodeState> bufferAccessor3 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle8);
					for (int k = 0; k < nativeArray4.Length; k++)
					{
						NetGeometryPrefab prefab2 = m_PrefabSystem.GetPrefab<NetGeometryPrefab>(nativeArray2[k]);
						DynamicBuffer<NetGeometryEdgeState> dynamicBuffer = bufferAccessor2[k];
						DynamicBuffer<NetGeometryNodeState> dynamicBuffer2 = bufferAccessor3[k];
						if (prefab2.m_EdgeStates != null)
						{
							for (int l = 0; l < prefab2.m_EdgeStates.Length; l++)
							{
								NetEdgeStateInfo obj = prefab2.m_EdgeStates[l];
								NetGeometryEdgeState elem = default(NetGeometryEdgeState);
								NetCompositionHelpers.GetRequirementFlags(obj.m_RequireAll, out elem.m_CompositionAll, out var sectionFlags);
								NetCompositionHelpers.GetRequirementFlags(obj.m_RequireAny, out elem.m_CompositionAny, out var sectionFlags2);
								NetCompositionHelpers.GetRequirementFlags(obj.m_RequireNone, out elem.m_CompositionNone, out var sectionFlags3);
								NetCompositionHelpers.GetRequirementFlags(obj.m_SetState, out elem.m_State, out var sectionFlags4);
								NetSectionFlags netSectionFlags = sectionFlags | sectionFlags2 | sectionFlags3 | sectionFlags4;
								if (netSectionFlags != 0)
								{
									COSystemBase.baseLog.ErrorFormat(prefab2, "Net edge state ({0}) cannot require/set section flags: {1}", prefab2.name, netSectionFlags);
								}
								dynamicBuffer.Add(elem);
							}
						}
						if (prefab2.m_NodeStates == null)
						{
							continue;
						}
						for (int m = 0; m < prefab2.m_NodeStates.Length; m++)
						{
							NetNodeStateInfo netNodeStateInfo = prefab2.m_NodeStates[m];
							NetGeometryNodeState elem2 = default(NetGeometryNodeState);
							NetCompositionHelpers.GetRequirementFlags(netNodeStateInfo.m_RequireAll, out elem2.m_CompositionAll, out var sectionFlags5);
							NetCompositionHelpers.GetRequirementFlags(netNodeStateInfo.m_RequireAny, out elem2.m_CompositionAny, out var sectionFlags6);
							NetCompositionHelpers.GetRequirementFlags(netNodeStateInfo.m_RequireNone, out elem2.m_CompositionNone, out var sectionFlags7);
							NetCompositionHelpers.GetRequirementFlags(netNodeStateInfo.m_SetState, out elem2.m_State, out var sectionFlags8);
							NetSectionFlags netSectionFlags2 = sectionFlags5 | sectionFlags6 | sectionFlags7 | sectionFlags8;
							if (netSectionFlags2 != 0)
							{
								COSystemBase.baseLog.ErrorFormat(prefab2, "Net node state ({0}) cannot require/set section flags: {1}", prefab2.name, netSectionFlags2);
							}
							elem2.m_MatchType = netNodeStateInfo.m_MatchType;
							dynamicBuffer2.Add(elem2);
						}
					}
				}
				for (int n = 0; n < nativeArray5.Length; n++)
				{
					NetPrefab prefab3 = m_PrefabSystem.GetPrefab<NetPrefab>(nativeArray2[n]);
					PlaceableNetData value2 = nativeArray5[n];
					value2.m_SnapDistance = 8f;
					value2.m_MinWaterElevation = 5f;
					PlaceableNet component3 = prefab3.GetComponent<PlaceableNet>();
					if (component3 != null)
					{
						value2.m_ElevationRange = component3.m_ElevationRange;
						value2.m_XPReward = component3.m_XPReward;
						if (component3.m_UndergroundPrefab != null)
						{
							value2.m_UndergroundPrefab = m_PrefabSystem.GetEntity(component3.m_UndergroundPrefab);
						}
						if (component3.m_AllowParallelMode)
						{
							value2.m_PlacementFlags |= PlacementFlags.AllowParallel;
						}
					}
					NetUpgrade component4 = prefab3.GetComponent<NetUpgrade>();
					if (component4 != null)
					{
						NetCompositionHelpers.GetRequirementFlags(component4.m_SetState, out value2.m_SetUpgradeFlags, out var sectionFlags9);
						NetCompositionHelpers.GetRequirementFlags(component4.m_UnsetState, out value2.m_UnsetUpgradeFlags, out var sectionFlags10);
						value2.m_PlacementFlags |= PlacementFlags.IsUpgrade;
						if (!component4.m_Standalone)
						{
							value2.m_PlacementFlags |= PlacementFlags.UpgradeOnly;
						}
						if (component4.m_Underground)
						{
							value2.m_PlacementFlags |= PlacementFlags.UndergroundUpgrade;
						}
						if (((value2.m_SetUpgradeFlags | value2.m_UnsetUpgradeFlags) & CompositionFlags.nodeMask) != default(CompositionFlags))
						{
							value2.m_PlacementFlags |= PlacementFlags.NodeUpgrade;
						}
						NetSectionFlags netSectionFlags3 = sectionFlags9 | sectionFlags10;
						if (netSectionFlags3 != 0)
						{
							COSystemBase.baseLog.ErrorFormat(prefab3, "PlaceableNet ({0}) cannot upgrade section flags: {1}", prefab3.name, netSectionFlags3);
						}
					}
					nativeArray5[n] = value2;
				}
				BufferAccessor<SubObject> bufferAccessor4 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle9);
				for (int num = 0; num < bufferAccessor4.Length; num++)
				{
					NetSubObjects component5 = m_PrefabSystem.GetPrefab<NetPrefab>(nativeArray2[num]).GetComponent<NetSubObjects>();
					bool flag5 = false;
					NetGeometryData value3 = default(NetGeometryData);
					if (nativeArray4.Length != 0)
					{
						value3 = nativeArray4[num];
					}
					DynamicBuffer<SubObject> dynamicBuffer3 = bufferAccessor4[num];
					for (int num2 = 0; num2 < component5.m_SubObjects.Length; num2++)
					{
						NetSubObjectInfo netSubObjectInfo = component5.m_SubObjects[num2];
						ObjectPrefab prefab4 = netSubObjectInfo.m_Object;
						SubObject elem3 = new SubObject
						{
							m_Prefab = m_PrefabSystem.GetEntity(prefab4),
							m_Position = netSubObjectInfo.m_Position,
							m_Rotation = netSubObjectInfo.m_Rotation,
							m_Probability = 100
						};
						switch (netSubObjectInfo.m_Placement)
						{
						case NetObjectPlacement.EdgeEndsOrNode:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.AllowCombine;
							break;
						case NetObjectPlacement.EdgeMiddle:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.MiddlePlacement;
							if (base.EntityManager.HasComponent<PillarData>(elem3.m_Prefab))
							{
								value3.m_Flags |= GeometryFlags.MiddlePillars;
							}
							if (netSubObjectInfo.m_Spacing != 0f)
							{
								elem3.m_Flags |= SubObjectFlags.EvenSpacing;
								elem3.m_Position.z = netSubObjectInfo.m_Spacing;
							}
							break;
						case NetObjectPlacement.EdgeEnds:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement;
							break;
						case NetObjectPlacement.CourseStart:
							elem3.m_Flags |= SubObjectFlags.CoursePlacement | SubObjectFlags.StartPlacement;
							if (!flag5)
							{
								elem3.m_Flags |= SubObjectFlags.MakeOwner;
								value3.m_Flags |= GeometryFlags.SubOwner;
								flag5 = true;
							}
							break;
						case NetObjectPlacement.CourseEnd:
							elem3.m_Flags |= SubObjectFlags.CoursePlacement | SubObjectFlags.EndPlacement;
							if (!flag5)
							{
								elem3.m_Flags |= SubObjectFlags.MakeOwner;
								value3.m_Flags |= GeometryFlags.SubOwner;
								flag5 = true;
							}
							break;
						case NetObjectPlacement.NodeBeforeFixedSegment:
							elem3.m_Flags |= SubObjectFlags.StartPlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.NodeBetweenFixedSegment:
							elem3.m_Flags |= SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.NodeAfterFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EndPlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.EdgeMiddleFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.MiddlePlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							if (base.EntityManager.HasComponent<PillarData>(elem3.m_Prefab))
							{
								value3.m_Flags |= GeometryFlags.MiddlePillars;
							}
							if (netSubObjectInfo.m_Spacing != 0f)
							{
								elem3.m_Flags |= SubObjectFlags.EvenSpacing;
								elem3.m_Position.z = netSubObjectInfo.m_Spacing;
							}
							break;
						case NetObjectPlacement.EdgeEndsFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.EdgeStartFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.StartPlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.EdgeEndFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.EndPlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.EdgeEndsOrNodeFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.AllowCombine | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.EdgeStartOrNodeFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.AllowCombine | SubObjectFlags.StartPlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.EdgeEndOrNodeFixedSegment:
							elem3.m_Flags |= SubObjectFlags.EdgePlacement | SubObjectFlags.AllowCombine | SubObjectFlags.EndPlacement | SubObjectFlags.FixedPlacement;
							elem3.m_ParentIndex = netSubObjectInfo.m_FixedIndex;
							break;
						case NetObjectPlacement.WaterwayCrossingNode:
							elem3.m_Flags |= SubObjectFlags.WaterwayCrossing;
							value3.m_IntersectLayers |= Layer.Waterway;
							break;
						case NetObjectPlacement.NotWaterwayCrossingNode:
							elem3.m_Flags |= SubObjectFlags.NotWaterwayCrossing;
							value3.m_IntersectLayers |= Layer.Waterway;
							break;
						case NetObjectPlacement.NotWaterwayCrossingEdgeMiddle:
							elem3.m_Flags |= SubObjectFlags.NotWaterwayCrossing | SubObjectFlags.EdgePlacement | SubObjectFlags.MiddlePlacement;
							value3.m_IntersectLayers |= Layer.Waterway;
							if (base.EntityManager.HasComponent<PillarData>(elem3.m_Prefab))
							{
								value3.m_Flags |= GeometryFlags.MiddlePillars;
							}
							if (netSubObjectInfo.m_Spacing != 0f)
							{
								elem3.m_Flags |= SubObjectFlags.EvenSpacing;
								elem3.m_Position.z = netSubObjectInfo.m_Spacing;
							}
							break;
						case NetObjectPlacement.NotWaterwayCrossingEdgeEndsOrNode:
							elem3.m_Flags |= SubObjectFlags.NotWaterwayCrossing | SubObjectFlags.EdgePlacement | SubObjectFlags.AllowCombine;
							value3.m_IntersectLayers |= Layer.Waterway;
							break;
						}
						if (netSubObjectInfo.m_AnchorTop)
						{
							elem3.m_Flags |= SubObjectFlags.AnchorTop;
						}
						if (netSubObjectInfo.m_AnchorCenter)
						{
							elem3.m_Flags |= SubObjectFlags.AnchorCenter;
						}
						if (netSubObjectInfo.m_RequireElevated)
						{
							elem3.m_Flags |= SubObjectFlags.RequireElevated;
						}
						if (netSubObjectInfo.m_RequireOutsideConnection)
						{
							elem3.m_Flags |= SubObjectFlags.RequireOutsideConnection;
						}
						if (netSubObjectInfo.m_RequireDeadEnd)
						{
							elem3.m_Flags |= SubObjectFlags.RequireDeadEnd;
						}
						if (netSubObjectInfo.m_RequireOrphan)
						{
							elem3.m_Flags |= SubObjectFlags.RequireOrphan;
						}
						if (CollectionUtils.TryGet(nativeArray6, num, out var value4) && base.EntityManager.HasComponent<LeisureProviderData>(elem3.m_Prefab))
						{
							value4.m_LeisureProvider = true;
							nativeArray6[num] = value4;
						}
						dynamicBuffer3.Add(elem3);
					}
					if (nativeArray4.Length != 0)
					{
						nativeArray4[num] = value3;
					}
				}
				BufferAccessor<AuxiliaryNet> bufferAccessor5 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle13);
				for (int num3 = 0; num3 < bufferAccessor5.Length; num3++)
				{
					AuxiliaryNets component6 = m_PrefabSystem.GetPrefab<NetPrefab>(nativeArray2[num3]).GetComponent<AuxiliaryNets>();
					DynamicBuffer<AuxiliaryNet> dynamicBuffer4 = bufferAccessor5[num3];
					dynamicBuffer4.ResizeUninitialized(component6.m_AuxiliaryNets.Length);
					if (CollectionUtils.TryGet(nativeArray5, num3, out var value5))
					{
						if (component6.m_LinkEndOffsets)
						{
							value5.m_PlacementFlags |= PlacementFlags.LinkAuxOffsets;
						}
						nativeArray5[num3] = value5;
					}
					for (int num4 = 0; num4 < component6.m_AuxiliaryNets.Length; num4++)
					{
						AuxiliaryNetInfo auxiliaryNetInfo = component6.m_AuxiliaryNets[num4];
						dynamicBuffer4[num4] = new AuxiliaryNet
						{
							m_Prefab = m_PrefabSystem.GetEntity(auxiliaryNetInfo.m_Prefab),
							m_Position = auxiliaryNetInfo.m_Position,
							m_InvertMode = auxiliaryNetInfo.m_InvertWhen
						};
					}
				}
				BufferAccessor<NetSectionPiece> bufferAccessor6 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle2);
				if (bufferAccessor6.Length != 0)
				{
					BufferAccessor<NetSubSection> bufferAccessor7 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle);
					for (int num5 = 0; num5 < bufferAccessor6.Length; num5++)
					{
						NetSectionPrefab prefab5 = m_PrefabSystem.GetPrefab<NetSectionPrefab>(nativeArray2[num5]);
						DynamicBuffer<NetSubSection> dynamicBuffer5 = bufferAccessor7[num5];
						DynamicBuffer<NetSectionPiece> dynamicBuffer6 = bufferAccessor6[num5];
						if (prefab5.m_SubSections != null)
						{
							for (int num6 = 0; num6 < prefab5.m_SubSections.Length; num6++)
							{
								NetSubSectionInfo netSubSectionInfo = prefab5.m_SubSections[num6];
								NetSubSection elem4 = new NetSubSection
								{
									m_SubSection = m_PrefabSystem.GetEntity(netSubSectionInfo.m_Section)
								};
								NetCompositionHelpers.GetRequirementFlags(netSubSectionInfo.m_RequireAll, out elem4.m_CompositionAll, out elem4.m_SectionAll);
								NetCompositionHelpers.GetRequirementFlags(netSubSectionInfo.m_RequireAny, out elem4.m_CompositionAny, out elem4.m_SectionAny);
								NetCompositionHelpers.GetRequirementFlags(netSubSectionInfo.m_RequireNone, out elem4.m_CompositionNone, out elem4.m_SectionNone);
								dynamicBuffer5.Add(elem4);
							}
						}
						if (prefab5.m_Pieces == null)
						{
							continue;
						}
						for (int num7 = 0; num7 < prefab5.m_Pieces.Length; num7++)
						{
							NetPieceInfo netPieceInfo = prefab5.m_Pieces[num7];
							NetSectionPiece elem5 = new NetSectionPiece
							{
								m_Piece = m_PrefabSystem.GetEntity(netPieceInfo.m_Piece)
							};
							NetCompositionHelpers.GetRequirementFlags(netPieceInfo.m_RequireAll, out elem5.m_CompositionAll, out elem5.m_SectionAll);
							NetCompositionHelpers.GetRequirementFlags(netPieceInfo.m_RequireAny, out elem5.m_CompositionAny, out elem5.m_SectionAny);
							NetCompositionHelpers.GetRequirementFlags(netPieceInfo.m_RequireNone, out elem5.m_CompositionNone, out elem5.m_SectionNone);
							switch (netPieceInfo.m_Piece.m_Layer)
							{
							case NetPieceLayer.Surface:
								elem5.m_Flags |= NetPieceFlags.Surface;
								break;
							case NetPieceLayer.Bottom:
								elem5.m_Flags |= NetPieceFlags.Bottom;
								break;
							case NetPieceLayer.Top:
								elem5.m_Flags |= NetPieceFlags.Top;
								break;
							case NetPieceLayer.Side:
								elem5.m_Flags |= NetPieceFlags.Side;
								break;
							}
							if (netPieceInfo.m_Piece.meshCount != 0)
							{
								elem5.m_Flags |= NetPieceFlags.HasMesh;
							}
							NetDividerPiece component7 = netPieceInfo.m_Piece.GetComponent<NetDividerPiece>();
							if (component7 != null)
							{
								if (component7.m_PreserveShape)
								{
									elem5.m_Flags |= NetPieceFlags.PreserveShape | NetPieceFlags.DisableTiling;
								}
								if (component7.m_BlockTraffic)
								{
									elem5.m_Flags |= NetPieceFlags.BlockTraffic;
								}
								if (component7.m_BlockCrosswalk)
								{
									elem5.m_Flags |= NetPieceFlags.BlockCrosswalk;
								}
							}
							NetPieceTiling component8 = netPieceInfo.m_Piece.GetComponent<NetPieceTiling>();
							if (component8 != null && component8.m_DisableTextureTiling)
							{
								elem5.m_Flags |= NetPieceFlags.DisableTiling;
							}
							MovePieceVertices component9 = netPieceInfo.m_Piece.GetComponent<MovePieceVertices>();
							if (component9 != null)
							{
								if (component9.m_LowerBottomToTerrain)
								{
									elem5.m_Flags |= NetPieceFlags.LowerBottomToTerrain;
								}
								if (component9.m_RaiseTopToTerrain)
								{
									elem5.m_Flags |= NetPieceFlags.RaiseTopToTerrain;
								}
								if (component9.m_SmoothTopNormal)
								{
									elem5.m_Flags |= NetPieceFlags.SmoothTopNormal;
								}
							}
							AsymmetricPieceMesh component10 = netPieceInfo.m_Piece.GetComponent<AsymmetricPieceMesh>();
							if (component10 != null)
							{
								if (component10.m_Sideways)
								{
									elem5.m_Flags |= NetPieceFlags.AsymmetricMeshX;
								}
								if (component10.m_Lengthwise)
								{
									elem5.m_Flags |= NetPieceFlags.AsymmetricMeshZ;
								}
							}
							elem5.m_Offset = netPieceInfo.m_Offset;
							dynamicBuffer6.Add(elem5);
						}
					}
				}
				NativeArray<NetPieceData> nativeArray7 = archetypeChunk.GetNativeArray(ref typeHandle4);
				if (nativeArray7.Length != 0)
				{
					BufferAccessor<NetPieceLane> bufferAccessor8 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle3);
					BufferAccessor<NetPieceArea> bufferAccessor9 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle4);
					BufferAccessor<NetPieceObject> bufferAccessor10 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle5);
					NativeArray<NetCrosswalkData> nativeArray8 = archetypeChunk.GetNativeArray(ref typeHandle17);
					NativeArray<NetTerrainData> nativeArray9 = archetypeChunk.GetNativeArray(ref typeHandle32);
					for (int num8 = 0; num8 < nativeArray7.Length; num8++)
					{
						NetPiecePrefab prefab6 = m_PrefabSystem.GetPrefab<NetPiecePrefab>(nativeArray2[num8]);
						NetPieceData value6 = nativeArray7[num8];
						value6.m_HeightRange = prefab6.m_HeightRange;
						value6.m_SurfaceHeights = prefab6.m_SurfaceHeights;
						value6.m_Width = prefab6.m_Width;
						value6.m_Length = prefab6.m_Length;
						value6.m_WidthOffset = prefab6.m_WidthOffset;
						value6.m_NodeOffset = prefab6.m_NodeOffset;
						value6.m_SideConnectionOffset = prefab6.m_SideConnectionOffset;
						if (bufferAccessor8.Length != 0)
						{
							NetPieceLanes component11 = prefab6.GetComponent<NetPieceLanes>();
							if (component11.m_Lanes != null)
							{
								DynamicBuffer<NetPieceLane> dynamicBuffer7 = bufferAccessor8[num8];
								for (int num9 = 0; num9 < component11.m_Lanes.Length; num9++)
								{
									NetLaneInfo netLaneInfo = component11.m_Lanes[num9];
									NetPieceLane elem6 = new NetPieceLane
									{
										m_Lane = m_PrefabSystem.GetEntity(netLaneInfo.m_Lane),
										m_Position = netLaneInfo.m_Position
									};
									if (netLaneInfo.m_FindAnchor)
									{
										elem6.m_ExtraFlags |= LaneFlags.FindAnchor;
									}
									dynamicBuffer7.Add(elem6);
								}
								if (dynamicBuffer7.Length > 1)
								{
									dynamicBuffer7.AsNativeArray().Sort();
								}
							}
						}
						if (bufferAccessor9.Length != 0)
						{
							DynamicBuffer<NetPieceArea> dynamicBuffer8 = bufferAccessor9[num8];
							BuildableNetPiece component12 = prefab6.GetComponent<BuildableNetPiece>();
							if (component12 != null)
							{
								dynamicBuffer8.Add(new NetPieceArea
								{
									m_Flags = (component12.m_AllowOnBridge ? NetAreaFlags.Buildable : (NetAreaFlags.Buildable | NetAreaFlags.NoBridge)),
									m_Position = component12.m_Position,
									m_Width = component12.m_Width,
									m_SnapPosition = component12.m_SnapPosition,
									m_SnapWidth = component12.m_SnapWidth
								});
							}
							if (dynamicBuffer8.Length > 1)
							{
								dynamicBuffer8.AsNativeArray().Sort();
							}
						}
						if (bufferAccessor10.Length != 0)
						{
							DynamicBuffer<NetPieceObject> dynamicBuffer9 = bufferAccessor10[num8];
							NetPieceObjects component13 = prefab6.GetComponent<NetPieceObjects>();
							if (component13 != null)
							{
								dynamicBuffer9.ResizeUninitialized(component13.m_PieceObjects.Length);
								for (int num10 = 0; num10 < component13.m_PieceObjects.Length; num10++)
								{
									NetPieceObjectInfo netPieceObjectInfo = component13.m_PieceObjects[num10];
									NetPieceObject value7 = new NetPieceObject
									{
										m_Prefab = m_PrefabSystem.GetEntity(netPieceObjectInfo.m_Object),
										m_Position = netPieceObjectInfo.m_Position,
										m_Offset = netPieceObjectInfo.m_Offset,
										m_Spacing = netPieceObjectInfo.m_Spacing,
										m_UseCurveRotation = netPieceObjectInfo.m_UseCurveRotation,
										m_MinLength = netPieceObjectInfo.m_MinLength,
										m_Probability = math.select(netPieceObjectInfo.m_Probability, 100, netPieceObjectInfo.m_Probability == 0),
										m_CurveOffsetRange = netPieceObjectInfo.m_CurveOffsetRange,
										m_Rotation = netPieceObjectInfo.m_Rotation
									};
									NetCompositionHelpers.GetRequirementFlags(netPieceObjectInfo.m_RequireAll, out value7.m_CompositionAll, out value7.m_SectionAll);
									NetCompositionHelpers.GetRequirementFlags(netPieceObjectInfo.m_RequireAny, out value7.m_CompositionAny, out value7.m_SectionAny);
									NetCompositionHelpers.GetRequirementFlags(netPieceObjectInfo.m_RequireNone, out value7.m_CompositionNone, out value7.m_SectionNone);
									if (netPieceObjectInfo.m_FlipWhenInverted)
									{
										value7.m_Flags |= SubObjectFlags.FlipInverted;
									}
									if (netPieceObjectInfo.m_EvenSpacing)
									{
										value7.m_Flags |= SubObjectFlags.EvenSpacing;
									}
									if (netPieceObjectInfo.m_SpacingOverride)
									{
										value7.m_Flags |= SubObjectFlags.SpacingOverride;
									}
									dynamicBuffer9[num10] = value7;
								}
							}
						}
						if (nativeArray8.Length != 0)
						{
							NetPieceCrosswalk component14 = prefab6.GetComponent<NetPieceCrosswalk>();
							nativeArray8[num8] = new NetCrosswalkData
							{
								m_Lane = m_PrefabSystem.GetEntity(component14.m_Lane),
								m_Start = component14.m_Start,
								m_End = component14.m_End
							};
						}
						if (nativeArray9.Length != 0)
						{
							NetTerrainPiece component15 = prefab6.GetComponent<NetTerrainPiece>();
							nativeArray9[num8] = new NetTerrainData
							{
								m_WidthOffset = component15.m_WidthOffset,
								m_ClipHeightOffset = component15.m_ClipHeightOffset,
								m_MinHeightOffset = component15.m_MinHeightOffset,
								m_MaxHeightOffset = component15.m_MaxHeightOffset
							};
						}
						nativeArray7[num8] = value6;
					}
				}
				NativeArray<NetLaneData> nativeArray10 = archetypeChunk.GetNativeArray(ref typeHandle9);
				if (nativeArray10.Length != 0)
				{
					NativeArray<ParkingLaneData> nativeArray11 = archetypeChunk.GetNativeArray(ref typeHandle14);
					NativeArray<CarLaneData> nativeArray12 = archetypeChunk.GetNativeArray(ref typeHandle11);
					NativeArray<TrackLaneData> nativeArray13 = archetypeChunk.GetNativeArray(ref typeHandle12);
					NativeArray<UtilityLaneData> nativeArray14 = archetypeChunk.GetNativeArray(ref typeHandle13);
					NativeArray<SecondaryLaneData> nativeArray15 = archetypeChunk.GetNativeArray(ref typeHandle16);
					BufferAccessor<AuxiliaryNetLane> bufferAccessor11 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle12);
					bool flag6 = archetypeChunk.Has(ref typeHandle15);
					for (int num11 = 0; num11 < nativeArray10.Length; num11++)
					{
						NetLanePrefab prefab7 = m_PrefabSystem.GetPrefab<NetLanePrefab>(nativeArray2[num11]);
						NetLaneData value8 = nativeArray10[num11];
						if (prefab7.m_PathfindPrefab != null)
						{
							value8.m_PathfindPrefab = m_PrefabSystem.GetEntity(prefab7.m_PathfindPrefab);
						}
						if (nativeArray12.Length != 0)
						{
							CarLane component16 = prefab7.GetComponent<CarLane>();
							value8.m_Flags |= LaneFlags.Road;
							value8.m_Width = component16.m_Width;
							if (component16.m_StartingLane)
							{
								value8.m_Flags |= LaneFlags.DisconnectedStart;
							}
							if (component16.m_EndingLane)
							{
								value8.m_Flags |= LaneFlags.DisconnectedEnd;
							}
							if (component16.m_Twoway)
							{
								value8.m_Flags |= LaneFlags.Twoway;
							}
							if (component16.m_BusLane)
							{
								value8.m_Flags |= LaneFlags.PublicOnly;
							}
							if (component16.m_RoadType == RoadTypes.Watercraft)
							{
								value8.m_Flags |= LaneFlags.OnWater;
							}
							CarLaneData value9 = nativeArray12[num11];
							if (component16.m_NotTrackLane != null)
							{
								value9.m_NotTrackLanePrefab = m_PrefabSystem.GetEntity(component16.m_NotTrackLane);
							}
							if (component16.m_NotBusLane != null)
							{
								value9.m_NotBusLanePrefab = m_PrefabSystem.GetEntity(component16.m_NotBusLane);
							}
							value9.m_RoadTypes = component16.m_RoadType;
							value9.m_MaxSize = component16.m_MaxSize;
							nativeArray12[num11] = value9;
						}
						if (nativeArray13.Length != 0)
						{
							TrackLane component17 = prefab7.GetComponent<TrackLane>();
							value8.m_Flags |= LaneFlags.Track;
							value8.m_Width = component17.m_Width;
							if (component17.m_Twoway)
							{
								value8.m_Flags |= LaneFlags.Twoway;
							}
							TrackLaneData value10 = nativeArray13[num11];
							if (component17.m_FallbackLane != null)
							{
								value10.m_FallbackPrefab = m_PrefabSystem.GetEntity(component17.m_FallbackLane);
							}
							if (component17.m_EndObject != null)
							{
								value10.m_EndObjectPrefab = m_PrefabSystem.GetEntity(component17.m_EndObject);
							}
							value10.m_TrackTypes = component17.m_TrackType;
							value10.m_MaxCurviness = math.radians(component17.m_MaxCurviness);
							nativeArray13[num11] = value10;
						}
						if (nativeArray14.Length != 0)
						{
							UtilityLane component18 = prefab7.GetComponent<UtilityLane>();
							value8.m_Flags |= LaneFlags.Utility;
							value8.m_Width = component18.m_Width;
							if (component18.m_Underground)
							{
								value8.m_Flags |= LaneFlags.Underground;
							}
							UtilityLaneData value11 = nativeArray14[num11];
							if (component18.m_LocalConnectionLane != null)
							{
								value11.m_LocalConnectionPrefab = m_PrefabSystem.GetEntity(component18.m_LocalConnectionLane);
							}
							if (component18.m_LocalConnectionLane2 != null)
							{
								value11.m_LocalConnectionPrefab2 = m_PrefabSystem.GetEntity(component18.m_LocalConnectionLane2);
							}
							if (component18.m_NodeObject != null)
							{
								value11.m_NodeObjectPrefab = m_PrefabSystem.GetEntity(component18.m_NodeObject);
							}
							value11.m_VisualCapacity = component18.m_VisualCapacity;
							value11.m_Hanging = component18.m_Hanging;
							value11.m_UtilityTypes = component18.m_UtilityType;
							nativeArray14[num11] = value11;
						}
						if (nativeArray11.Length != 0)
						{
							ParkingLane component19 = prefab7.GetComponent<ParkingLane>();
							value8.m_Flags |= LaneFlags.Parking;
							ParkingLaneData value12 = nativeArray11[num11];
							value12.m_RoadTypes = component19.m_RoadType;
							value12.m_SlotSize = math.select(component19.m_SlotSize, 0f, component19.m_SlotSize < 0.001f);
							value12.m_SlotAngle = math.radians(math.clamp(component19.m_SlotAngle, 0f, 90f));
							value12.m_MaxCarLength = math.select(0f, value12.m_SlotSize.y + 0.4f, value12.m_SlotSize.y != 0f);
							float2 y = new float2(math.cos(value12.m_SlotAngle), math.sin(value12.m_SlotAngle));
							if (y.y < 0.001f)
							{
								value12.m_SlotInterval = value12.m_SlotSize.y;
							}
							else if (y.x < 0.001f)
							{
								value12.m_SlotInterval = value12.m_SlotSize.x;
								value8.m_Flags |= LaneFlags.Twoway;
							}
							else
							{
								float2 @float = value12.m_SlotSize / y.yx;
								@float = math.select(@float, 0f, @float < 0.001f);
								if (@float.x < @float.y)
								{
									value12.m_SlotInterval = @float.x;
								}
								else
								{
									value12.m_SlotInterval = @float.y;
									value12.m_MaxCarLength = math.max(0f, value12.m_SlotSize.y - 1f);
								}
							}
							value8.m_Width = math.dot(value12.m_SlotSize, y);
							value8.m_Width = math.select(value8.m_Width, value12.m_SlotSize.y, value12.m_SlotSize.y != 0f && value12.m_SlotSize.y < value8.m_Width);
							if (value12.m_SlotSize.x == 0f)
							{
								value8.m_Flags |= LaneFlags.Virtual;
							}
							if (component19.m_SpecialVehicles)
							{
								value8.m_Flags |= LaneFlags.PublicOnly;
							}
							nativeArray11[num11] = value12;
						}
						if (flag6)
						{
							PedestrianLane component20 = prefab7.GetComponent<PedestrianLane>();
							value8.m_Flags |= LaneFlags.Pedestrian | LaneFlags.Twoway;
							value8.m_Width = component20.m_Width;
							if (component20.m_OnWater)
							{
								value8.m_Flags |= LaneFlags.OnWater;
							}
						}
						if (nativeArray15.Length != 0)
						{
							Entity entity = nativeArray[num11];
							SecondaryLane component21 = prefab7.GetComponent<SecondaryLane>();
							value8.m_Flags |= LaneFlags.Secondary;
							bool flag7 = component21.m_LeftLanes != null && component21.m_LeftLanes.Length != 0;
							bool flag8 = component21.m_RightLanes != null && component21.m_RightLanes.Length != 0;
							bool flag9 = component21.m_CrossingLanes != null && component21.m_CrossingLanes.Length != 0;
							SecondaryLaneData value13 = nativeArray15[num11];
							if (component21.m_SkipSafePedestrianOverlap)
							{
								value13.m_Flags |= SecondaryLaneDataFlags.SkipSafePedestrianOverlap;
							}
							if (component21.m_SkipSafeCarOverlap)
							{
								value13.m_Flags |= SecondaryLaneDataFlags.SkipSafeCarOverlap;
							}
							if (component21.m_SkipUnsafeCarOverlap)
							{
								value13.m_Flags |= SecondaryLaneDataFlags.SkipUnsafeCarOverlap;
							}
							if (component21.m_SkipTrackOverlap)
							{
								value13.m_Flags |= SecondaryLaneDataFlags.SkipTrackOverlap;
							}
							if (component21.m_SkipMergeOverlap)
							{
								value13.m_Flags |= SecondaryLaneDataFlags.SkipMergeOverlap;
							}
							if (component21.m_FitToParkingSpaces)
							{
								value13.m_Flags |= SecondaryLaneDataFlags.FitToParkingSpaces;
							}
							if (component21.m_EvenSpacing)
							{
								value13.m_Flags |= SecondaryLaneDataFlags.EvenSpacing;
							}
							value13.m_PositionOffset = component21.m_PositionOffset;
							value13.m_LengthOffset = component21.m_LengthOffset;
							value13.m_CutMargin = component21.m_CutMargin;
							value13.m_CutOffset = component21.m_CutOffset;
							value13.m_CutOverlap = component21.m_CutOverlap;
							value13.m_Spacing = component21.m_Spacing;
							SecondaryNetLaneFlags secondaryNetLaneFlags = (SecondaryNetLaneFlags)0;
							if (component21.m_CanFlipSides)
							{
								secondaryNetLaneFlags |= SecondaryNetLaneFlags.CanFlipSides;
							}
							if (component21.m_DuplicateSides)
							{
								secondaryNetLaneFlags |= SecondaryNetLaneFlags.DuplicateSides;
							}
							if (component21.m_RequireParallel)
							{
								secondaryNetLaneFlags |= SecondaryNetLaneFlags.RequireParallel;
							}
							if (component21.m_RequireOpposite)
							{
								secondaryNetLaneFlags |= SecondaryNetLaneFlags.RequireOpposite;
							}
							if (flag7)
							{
								SecondaryNetLaneFlags secondaryNetLaneFlags2 = secondaryNetLaneFlags | SecondaryNetLaneFlags.Left;
								if (!flag8)
								{
									secondaryNetLaneFlags2 |= SecondaryNetLaneFlags.OneSided;
								}
								for (int num12 = 0; num12 < component21.m_LeftLanes.Length; num12++)
								{
									SecondaryLaneInfo secondaryLaneInfo = component21.m_LeftLanes[num12];
									SecondaryNetLaneFlags flags = secondaryNetLaneFlags2 | secondaryLaneInfo.GetFlags();
									Entity entity2 = m_PrefabSystem.GetEntity(secondaryLaneInfo.m_Lane);
									base.EntityManager.GetBuffer<SecondaryNetLane>(entity2).Add(new SecondaryNetLane
									{
										m_Lane = entity,
										m_Flags = flags
									});
								}
							}
							if (flag8)
							{
								SecondaryNetLaneFlags secondaryNetLaneFlags3 = secondaryNetLaneFlags | SecondaryNetLaneFlags.Right;
								if (!flag7)
								{
									secondaryNetLaneFlags3 |= SecondaryNetLaneFlags.OneSided;
								}
								for (int num13 = 0; num13 < component21.m_RightLanes.Length; num13++)
								{
									SecondaryLaneInfo secondaryLaneInfo2 = component21.m_RightLanes[num13];
									SecondaryNetLaneFlags secondaryNetLaneFlags4 = secondaryNetLaneFlags3 | secondaryLaneInfo2.GetFlags();
									Entity entity3 = m_PrefabSystem.GetEntity(secondaryLaneInfo2.m_Lane);
									DynamicBuffer<SecondaryNetLane> buffer = base.EntityManager.GetBuffer<SecondaryNetLane>(entity3);
									int num14 = 0;
									while (true)
									{
										if (num14 < buffer.Length)
										{
											SecondaryNetLane value14 = buffer[num14];
											if (value14.m_Lane == entity && ((value14.m_Flags ^ secondaryNetLaneFlags4) & ~(SecondaryNetLaneFlags.Left | SecondaryNetLaneFlags.Right)) == 0)
											{
												value14.m_Flags |= secondaryNetLaneFlags4;
												buffer[num14] = value14;
												break;
											}
											num14++;
											continue;
										}
										buffer.Add(new SecondaryNetLane
										{
											m_Lane = entity,
											m_Flags = secondaryNetLaneFlags4
										});
										break;
									}
								}
							}
							if (flag9)
							{
								SecondaryNetLaneFlags secondaryNetLaneFlags5 = SecondaryNetLaneFlags.Crossing;
								for (int num15 = 0; num15 < component21.m_CrossingLanes.Length; num15++)
								{
									SecondaryLaneInfo2 secondaryLaneInfo3 = component21.m_CrossingLanes[num15];
									SecondaryNetLaneFlags flags2 = secondaryNetLaneFlags5 | secondaryLaneInfo3.GetFlags();
									Entity entity4 = m_PrefabSystem.GetEntity(secondaryLaneInfo3.m_Lane);
									base.EntityManager.GetBuffer<SecondaryNetLane>(entity4).Add(new SecondaryNetLane
									{
										m_Lane = entity,
										m_Flags = flags2
									});
								}
							}
							nativeArray15[num11] = value13;
						}
						if (bufferAccessor11.Length != 0)
						{
							DynamicBuffer<AuxiliaryNetLane> dynamicBuffer10 = bufferAccessor11[num11];
							AuxiliaryLanes component22 = prefab7.GetComponent<AuxiliaryLanes>();
							if (component22 != null)
							{
								dynamicBuffer10.ResizeUninitialized(component22.m_AuxiliaryLanes.Length);
								for (int num16 = 0; num16 < component22.m_AuxiliaryLanes.Length; num16++)
								{
									AuxiliaryLaneInfo auxiliaryLaneInfo = component22.m_AuxiliaryLanes[num16];
									AuxiliaryNetLane value15 = new AuxiliaryNetLane
									{
										m_Prefab = m_PrefabSystem.GetEntity(auxiliaryLaneInfo.m_Lane),
										m_Position = auxiliaryLaneInfo.m_Position,
										m_Spacing = auxiliaryLaneInfo.m_Spacing
									};
									if (auxiliaryLaneInfo.m_EvenSpacing)
									{
										value15.m_Flags |= LaneFlags.EvenSpacing;
									}
									if (auxiliaryLaneInfo.m_FindAnchor)
									{
										value15.m_Flags |= LaneFlags.FindAnchor;
									}
									NetCompositionHelpers.GetRequirementFlags(auxiliaryLaneInfo.m_RequireAll, out value15.m_CompositionAll, out var sectionFlags11);
									NetCompositionHelpers.GetRequirementFlags(auxiliaryLaneInfo.m_RequireAny, out value15.m_CompositionAny, out var sectionFlags12);
									NetCompositionHelpers.GetRequirementFlags(auxiliaryLaneInfo.m_RequireNone, out value15.m_CompositionNone, out var sectionFlags13);
									NetSectionFlags netSectionFlags4 = sectionFlags11 | sectionFlags12 | sectionFlags13;
									if (netSectionFlags4 != 0)
									{
										COSystemBase.baseLog.ErrorFormat(prefab7, "Auxiliary net lane ({0}: {1}) cannot require section flags: {2}", prefab7.name, auxiliaryLaneInfo.m_Lane.name, netSectionFlags4);
									}
									dynamicBuffer10[num16] = value15;
									value8.m_Flags |= LaneFlags.HasAuxiliary;
								}
							}
						}
						nativeArray10[num11] = value8;
					}
					NativeArray<NetLaneGeometryData> nativeArray16 = archetypeChunk.GetNativeArray(ref typeHandle10);
					BufferAccessor<SubMesh> bufferAccessor12 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle10);
					for (int num17 = 0; num17 < nativeArray16.Length; num17++)
					{
						NetLaneGeometryPrefab prefab8 = m_PrefabSystem.GetPrefab<NetLaneGeometryPrefab>(nativeArray2[num17]);
						NetLaneData value16 = nativeArray10[num17];
						NetLaneGeometryData value17 = nativeArray16[num17];
						DynamicBuffer<SubMesh> dynamicBuffer11 = bufferAccessor12[num17];
						value17.m_MinLod = 255;
						value17.m_GameLayers = (MeshLayer)0;
						value17.m_EditorLayers = (MeshLayer)0;
						if (prefab8.m_Meshes != null)
						{
							for (int num18 = 0; num18 < prefab8.m_Meshes.Length; num18++)
							{
								NetLaneMeshInfo obj2 = prefab8.m_Meshes[num18];
								RenderPrefab mesh = obj2.m_Mesh;
								Entity entity5 = m_PrefabSystem.GetEntity(mesh);
								MeshData componentData = base.EntityManager.GetComponentData<MeshData>(entity5);
								float3 y2 = MathUtils.Size(mesh.bounds);
								componentData.m_MinLod = (byte)RenderingUtils.CalculateLodLimit(RenderingUtils.GetRenderingSize(y2.xy), componentData.m_LodBias);
								componentData.m_ShadowLod = (byte)RenderingUtils.CalculateLodLimit(RenderingUtils.GetShadowRenderingSize(y2.xy), componentData.m_ShadowBias);
								value17.m_Size = math.max(value17.m_Size, y2);
								value17.m_MinLod = math.min(value17.m_MinLod, componentData.m_MinLod);
								SubMeshFlags subMeshFlags = (SubMeshFlags)0u;
								if (obj2.m_RequireSafe)
								{
									subMeshFlags |= SubMeshFlags.RequireSafe;
								}
								if (obj2.m_RequireLevelCrossing)
								{
									subMeshFlags |= SubMeshFlags.RequireLevelCrossing;
								}
								if (obj2.m_RequireEditor)
								{
									subMeshFlags |= SubMeshFlags.RequireEditor;
								}
								if (obj2.m_RequireTrackCrossing)
								{
									subMeshFlags |= SubMeshFlags.RequireTrack;
								}
								if (obj2.m_RequireClear)
								{
									subMeshFlags |= SubMeshFlags.RequireClear;
								}
								if (obj2.m_RequireLeftHandTraffic)
								{
									subMeshFlags |= SubMeshFlags.RequireLeftHandTraffic;
								}
								if (obj2.m_RequireRightHandTraffic)
								{
									subMeshFlags |= SubMeshFlags.RequireRightHandTraffic;
								}
								dynamicBuffer11.Add(new SubMesh(entity5, subMeshFlags, (ushort)num18));
								MeshLayer meshLayer = ((componentData.m_DefaultLayers == (MeshLayer)0) ? MeshLayer.Default : componentData.m_DefaultLayers);
								if (!obj2.m_RequireEditor)
								{
									value17.m_GameLayers |= meshLayer;
								}
								value17.m_EditorLayers |= meshLayer;
								base.EntityManager.SetComponentData(entity5, componentData);
								if (mesh.Has<ColorProperties>())
								{
									value16.m_Flags |= LaneFlags.PseudoRandom;
								}
							}
						}
						nativeArray10[num17] = value16;
						nativeArray16[num17] = value17;
					}
					NativeArray<SpawnableObjectData> nativeArray17 = archetypeChunk.GetNativeArray(ref typeHandle31);
					if (nativeArray17.Length != 0)
					{
						for (int num19 = 0; num19 < nativeArray17.Length; num19++)
						{
							Entity obj3 = nativeArray[num19];
							SpawnableObjectData value18 = nativeArray17[num19];
							SpawnableLane component23 = m_PrefabSystem.GetPrefab<NetLanePrefab>(nativeArray2[num19]).GetComponent<SpawnableLane>();
							for (int num20 = 0; num20 < component23.m_Placeholders.Length; num20++)
							{
								NetLanePrefab prefab9 = component23.m_Placeholders[num20];
								Entity entity6 = m_PrefabSystem.GetEntity(prefab9);
								base.EntityManager.GetBuffer<PlaceholderObjectElement>(entity6).Add(new PlaceholderObjectElement(obj3));
							}
							if (component23.m_RandomizationGroup != null)
							{
								value18.m_RandomizationGroup = m_PrefabSystem.GetEntity(component23.m_RandomizationGroup);
							}
							value18.m_Probability = component23.m_Probability;
							nativeArray17[num19] = value18;
						}
					}
				}
				NativeArray<RoadData> nativeArray18 = archetypeChunk.GetNativeArray(ref typeHandle18);
				if (nativeArray18.Length != 0)
				{
					for (int num21 = 0; num21 < nativeArray18.Length; num21++)
					{
						RoadPrefab prefab10 = m_PrefabSystem.GetPrefab<RoadPrefab>(nativeArray2[num21]);
						NetData value19 = nativeArray3[num21];
						NetGeometryData value20 = nativeArray4[num21];
						RoadData value21 = nativeArray18[num21];
						switch (prefab10.m_RoadType)
						{
						case RoadType.Normal:
							value19.m_RequiredLayers |= Layer.Road;
							break;
						case RoadType.PublicTransport:
							value19.m_RequiredLayers |= Layer.PublicTransportRoad;
							break;
						}
						value19.m_ConnectLayers |= Layer.Road | Layer.TrainTrack | Layer.Pathway | Layer.TramTrack | Layer.Fence | Layer.PublicTransportRoad;
						value19.m_ConnectLayers |= value20.m_IntersectLayers & Layer.Waterway;
						value19.m_LocalConnectLayers |= Layer.Pathway | Layer.MarkerPathway;
						value19.m_NodePriority += 2000f;
						value20.m_MergeLayers |= Layer.Road | Layer.TramTrack | Layer.PublicTransportRoad;
						value20.m_IntersectLayers |= Layer.Road | Layer.TrainTrack | Layer.Pathway | Layer.TramTrack | Layer.PublicTransportRoad;
						value20.m_Flags |= GeometryFlags.SupportRoundabout | GeometryFlags.BlockZone | GeometryFlags.Directional | GeometryFlags.FlattenTerrain | GeometryFlags.ClipTerrain;
						value21.m_SpeedLimit = prefab10.m_SpeedLimit / 3.6f;
						if (prefab10.m_ZoneBlock != null)
						{
							value20.m_Flags |= GeometryFlags.SnapCellSize;
							value21.m_ZoneBlockPrefab = m_PrefabSystem.GetEntity(prefab10.m_ZoneBlock);
							value21.m_Flags |= RoadFlags.EnableZoning;
						}
						if (prefab10.m_TrafficLights)
						{
							value21.m_Flags |= RoadFlags.PreferTrafficLights;
						}
						if (prefab10.m_HighwayRules)
						{
							value21.m_Flags |= RoadFlags.UseHighwayRules;
							value20.m_MinNodeOffset = math.max(value20.m_MinNodeOffset, 2f);
							value20.m_Flags |= GeometryFlags.SmoothElevation;
						}
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value22 = nativeArray5[num21];
							value22.m_PlacementFlags |= PlacementFlags.OnGround;
							nativeArray5[num21] = value22;
						}
						nativeArray3[num21] = value19;
						nativeArray4[num21] = value20;
						nativeArray18[num21] = value21;
					}
				}
				NativeArray<TrackData> nativeArray19 = archetypeChunk.GetNativeArray(ref typeHandle19);
				if (nativeArray19.Length != 0)
				{
					for (int num22 = 0; num22 < nativeArray19.Length; num22++)
					{
						TrackPrefab prefab11 = m_PrefabSystem.GetPrefab<TrackPrefab>(nativeArray2[num22]);
						NetData value23 = nativeArray3[num22];
						NetGeometryData value24 = nativeArray4[num22];
						TrackData value25 = nativeArray19[num22];
						Layer layer;
						Layer layer2;
						float num23;
						float y3;
						switch (prefab11.m_TrackType)
						{
						case TrackTypes.Train:
							layer = Layer.TrainTrack;
							layer2 = Layer.TrainTrack | Layer.Pathway;
							num23 = 200f;
							y3 = 10f;
							value24.m_Flags |= GeometryFlags.SmoothElevation;
							break;
						case TrackTypes.Tram:
							layer = Layer.TramTrack;
							layer2 = Layer.TramTrack;
							num23 = 0f;
							y3 = 8f;
							value24.m_Flags |= GeometryFlags.SupportRoundabout;
							break;
						case TrackTypes.Subway:
							layer = Layer.SubwayTrack;
							layer2 = Layer.SubwayTrack;
							num23 = 200f;
							y3 = 9f;
							value24.m_Flags |= GeometryFlags.SmoothElevation;
							break;
						default:
							layer = Layer.None;
							layer2 = Layer.None;
							num23 = 0f;
							y3 = 0f;
							break;
						}
						value23.m_RequiredLayers |= layer;
						value23.m_ConnectLayers |= layer2;
						value23.m_ConnectLayers |= value24.m_IntersectLayers & Layer.Waterway;
						value23.m_LocalConnectLayers |= Layer.Pathway | Layer.MarkerPathway;
						value24.m_MergeLayers |= layer;
						value24.m_IntersectLayers |= layer2;
						value24.m_EdgeLengthRange.max = math.max(value24.m_EdgeLengthRange.max, num23 * 1.5f);
						value24.m_MinNodeOffset = math.max(value24.m_MinNodeOffset, y3);
						value24.m_Flags |= GeometryFlags.BlockZone | GeometryFlags.Directional | GeometryFlags.FlattenTerrain | GeometryFlags.ClipTerrain;
						value25.m_TrackType = prefab11.m_TrackType;
						value25.m_SpeedLimit = prefab11.m_SpeedLimit / 3.6f;
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value26 = nativeArray5[num22];
							value26.m_PlacementFlags |= PlacementFlags.OnGround;
							nativeArray5[num22] = value26;
						}
						nativeArray3[num22] = value23;
						nativeArray4[num22] = value24;
						nativeArray19[num22] = value25;
					}
				}
				NativeArray<WaterwayData> nativeArray20 = archetypeChunk.GetNativeArray(ref typeHandle20);
				if (nativeArray20.Length != 0)
				{
					for (int num24 = 0; num24 < nativeArray20.Length; num24++)
					{
						WaterwayPrefab prefab12 = m_PrefabSystem.GetPrefab<WaterwayPrefab>(nativeArray2[num24]);
						NetData value27 = nativeArray3[num24];
						NetGeometryData value28 = nativeArray4[num24];
						WaterwayData value29 = nativeArray20[num24];
						value27.m_RequiredLayers |= Layer.Waterway;
						value27.m_ConnectLayers |= Layer.Waterway;
						value27.m_LocalConnectLayers |= Layer.Pathway | Layer.MarkerPathway;
						value28.m_MergeLayers |= Layer.Waterway;
						value28.m_IntersectLayers |= Layer.Waterway;
						value28.m_EdgeLengthRange.max = 1000f;
						value28.m_ElevatedLength = 1000f;
						value28.m_Flags |= GeometryFlags.BlockZone | GeometryFlags.Directional | GeometryFlags.FlattenTerrain | GeometryFlags.OnWater;
						value29.m_SpeedLimit = prefab12.m_SpeedLimit / 3.6f;
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value30 = nativeArray5[num24];
							value30.m_PlacementFlags |= PlacementFlags.Floating;
							value30.m_SnapDistance = 16f;
							nativeArray5[num24] = value30;
						}
						nativeArray3[num24] = value27;
						nativeArray4[num24] = value28;
						nativeArray20[num24] = value29;
					}
				}
				if (nativeArray6.Length != 0)
				{
					NativeArray<LocalConnectData> nativeArray21 = archetypeChunk.GetNativeArray(ref typeHandle8);
					for (int num25 = 0; num25 < nativeArray6.Length; num25++)
					{
						PathwayPrefab prefab13 = m_PrefabSystem.GetPrefab<PathwayPrefab>(nativeArray2[num25]);
						NetData value31 = nativeArray3[num25];
						NetGeometryData value32 = nativeArray4[num25];
						LocalConnectData value33 = nativeArray21[num25];
						PathwayData value34 = nativeArray6[num25];
						Layer layer3 = (flag2 ? Layer.MarkerPathway : Layer.Pathway);
						value31.m_RequiredLayers |= layer3;
						value31.m_ConnectLayers |= Layer.Pathway | Layer.MarkerPathway;
						value31.m_LocalConnectLayers |= Layer.Pathway | Layer.MarkerPathway;
						value32.m_MergeLayers |= layer3;
						value32.m_IntersectLayers |= Layer.Pathway | Layer.MarkerPathway;
						value32.m_ElevationLimit = 2f;
						value32.m_Flags |= GeometryFlags.Directional;
						if (flag2)
						{
							value32.m_ElevatedLength = value32.m_EdgeLengthRange.max;
							value32.m_Flags |= GeometryFlags.LoweredIsTunnel | GeometryFlags.RaisedIsElevated;
						}
						else
						{
							value32.m_ElevatedLength = 40f;
							value32.m_Flags |= GeometryFlags.BlockZone | GeometryFlags.FlattenTerrain | GeometryFlags.ClipTerrain;
						}
						value33.m_Flags |= LocalConnectFlags.KeepOpen | LocalConnectFlags.RequireDeadend | LocalConnectFlags.ChooseBest | LocalConnectFlags.ChooseSides;
						value33.m_Layers |= Layer.Road | Layer.TrainTrack | Layer.Pathway | Layer.Waterway | Layer.TramTrack | Layer.SubwayTrack | Layer.MarkerPathway | Layer.PublicTransportRoad;
						value33.m_HeightRange = new Bounds1(-8f, 8f);
						value33.m_SearchDistance = 4f;
						value34.m_SpeedLimit = prefab13.m_SpeedLimit / 3.6f;
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value35 = nativeArray5[num25];
							value35.m_PlacementFlags |= PlacementFlags.OnGround;
							value35.m_SnapDistance = (flag2 ? 2f : 4f);
							value35.m_MinWaterElevation = 2.5f;
							nativeArray5[num25] = value35;
						}
						nativeArray3[num25] = value31;
						nativeArray4[num25] = value32;
						nativeArray21[num25] = value33;
						nativeArray6[num25] = value34;
					}
				}
				NativeArray<TaxiwayData> nativeArray22 = archetypeChunk.GetNativeArray(ref typeHandle22);
				if (nativeArray22.Length != 0)
				{
					for (int num26 = 0; num26 < nativeArray22.Length; num26++)
					{
						TaxiwayPrefab prefab14 = m_PrefabSystem.GetPrefab<TaxiwayPrefab>(nativeArray2[num26]);
						NetData value36 = nativeArray3[num26];
						NetGeometryData value37 = nativeArray4[num26];
						TaxiwayData value38 = nativeArray22[num26];
						Layer layer4 = (flag2 ? Layer.MarkerTaxiway : Layer.Taxiway);
						value36.m_RequiredLayers |= layer4;
						value36.m_ConnectLayers |= Layer.Pathway | Layer.Taxiway | Layer.MarkerPathway | Layer.MarkerTaxiway;
						value37.m_MergeLayers |= layer4;
						value37.m_IntersectLayers |= Layer.Pathway | Layer.Taxiway | Layer.MarkerPathway | Layer.MarkerTaxiway;
						value37.m_EdgeLengthRange.max = 1000f;
						value37.m_ElevatedLength = 1000f;
						value37.m_Flags |= GeometryFlags.Directional;
						if (!flag2)
						{
							value37.m_Flags |= GeometryFlags.BlockZone | GeometryFlags.FlattenTerrain | GeometryFlags.ClipTerrain;
						}
						value38.m_SpeedLimit = prefab14.m_SpeedLimit / 3.6f;
						if (prefab14.m_Airspace)
						{
							if (prefab14.m_Runway)
							{
								value38.m_Flags |= TaxiwayFlags.Runway;
							}
							else if (!prefab14.m_Taxiway)
							{
								value37.m_Flags |= GeometryFlags.RaisedIsElevated | GeometryFlags.BlockZone | GeometryFlags.FlattenTerrain;
							}
							value38.m_Flags |= TaxiwayFlags.Airspace;
						}
						else if (prefab14.m_Runway)
						{
							value38.m_Flags |= TaxiwayFlags.Runway;
						}
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value39 = nativeArray5[num26];
							value39.m_PlacementFlags |= PlacementFlags.OnGround;
							value39.m_SnapDistance = (flag2 ? 4f : 8f);
							nativeArray5[num26] = value39;
						}
						nativeArray3[num26] = value36;
						nativeArray4[num26] = value37;
						nativeArray22[num26] = value38;
					}
				}
				bool flag10 = archetypeChunk.Has(ref typeHandle23);
				if (flag10)
				{
					for (int num27 = 0; num27 < nativeArray.Length; num27++)
					{
						PowerLinePrefab prefab15 = m_PrefabSystem.GetPrefab<PowerLinePrefab>(nativeArray2[num27]);
						NetGeometryData value40 = nativeArray4[num27];
						bool flag11 = false;
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value41 = nativeArray5[num27];
							value41.m_PlacementFlags |= PlacementFlags.OnGround;
							flag11 = value41.m_ElevationRange.max < 0f;
							nativeArray5[num27] = value41;
						}
						value40.m_EdgeLengthRange.max = prefab15.m_MaxPylonDistance;
						value40.m_ElevatedLength = prefab15.m_MaxPylonDistance;
						value40.m_Hanging = prefab15.m_Hanging;
						value40.m_Flags |= GeometryFlags.StrictNodes | GeometryFlags.LoweredIsTunnel | GeometryFlags.RaisedIsElevated;
						if (!flag2)
						{
							value40.m_Flags |= GeometryFlags.FlattenTerrain;
						}
						if (flag11)
						{
							value40.m_IntersectLayers |= Layer.PowerlineLow | Layer.PowerlineHigh;
							value40.m_MergeLayers |= Layer.PowerlineLow | Layer.PowerlineHigh;
						}
						else
						{
							value40.m_Flags |= GeometryFlags.StraightEdges | GeometryFlags.NoEdgeConnection | GeometryFlags.SnapToNetAreas | GeometryFlags.BlockZone | GeometryFlags.StandingNodes;
						}
						nativeArray4[num27] = value40;
					}
				}
				NativeArray<WaterPipeConnectionData> nativeArray23 = archetypeChunk.GetNativeArray(ref typeHandle28);
				NativeArray<ResourceConnectionData> nativeArray24 = archetypeChunk.GetNativeArray(ref typeHandle29);
				bool flag12 = archetypeChunk.Has(ref typeHandle24);
				if (flag12)
				{
					for (int num28 = 0; num28 < nativeArray.Length; num28++)
					{
						m_PrefabSystem.GetPrefab<PipelinePrefab>(nativeArray2[num28]);
						NetGeometryData value42 = nativeArray4[num28];
						value42.m_ElevatedLength = value42.m_EdgeLengthRange.max;
						value42.m_Flags |= GeometryFlags.StrictNodes | GeometryFlags.LoweredIsTunnel | GeometryFlags.RaisedIsElevated;
						if (nativeArray23.Length != 0)
						{
							value42.m_IntersectLayers |= Layer.WaterPipe | Layer.SewagePipe | Layer.StormwaterPipe;
							value42.m_MergeLayers |= Layer.WaterPipe | Layer.SewagePipe | Layer.StormwaterPipe;
						}
						if (nativeArray24.Length != 0)
						{
							value42.m_IntersectLayers |= Layer.ResourceLine;
							value42.m_MergeLayers |= Layer.ResourceLine;
						}
						if (!flag2)
						{
							value42.m_Flags |= GeometryFlags.FlattenTerrain;
						}
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value43 = nativeArray5[num28];
							value43.m_PlacementFlags |= PlacementFlags.OnGround;
							nativeArray5[num28] = value43;
						}
						nativeArray4[num28] = value42;
					}
				}
				if (archetypeChunk.Has(ref typeHandle25))
				{
					for (int num29 = 0; num29 < nativeArray.Length; num29++)
					{
						m_PrefabSystem.GetPrefab<FencePrefab>(nativeArray2[num29]);
						NetData value44 = nativeArray3[num29];
						NetGeometryData value45 = nativeArray4[num29];
						value44.m_RequiredLayers |= Layer.Fence;
						value44.m_ConnectLayers |= Layer.Fence;
						value45.m_ElevatedLength = value45.m_EdgeLengthRange.max;
						value45.m_Flags |= GeometryFlags.StrictNodes | GeometryFlags.BlockZone | GeometryFlags.FlattenTerrain;
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value46 = nativeArray5[num29];
							value46.m_PlacementFlags |= PlacementFlags.OnGround;
							value46.m_SnapDistance = 4f;
							nativeArray5[num29] = value46;
						}
						nativeArray3[num29] = value44;
						nativeArray4[num29] = value45;
					}
				}
				if (archetypeChunk.Has(ref typeHandle26))
				{
					for (int num30 = 0; num30 < nativeArray3.Length; num30++)
					{
						NetData value47 = nativeArray3[num30];
						value47.m_RequiredLayers |= Layer.LaneEditor;
						value47.m_ConnectLayers |= Layer.LaneEditor;
						nativeArray3[num30] = value47;
					}
				}
				if (flag3)
				{
					BufferAccessor<FixedNetElement> bufferAccessor13 = archetypeChunk.GetBufferAccessor(ref bufferTypeHandle11);
					for (int num31 = 0; num31 < nativeArray4.Length; num31++)
					{
						NetGeometryPrefab prefab16 = m_PrefabSystem.GetPrefab<NetGeometryPrefab>(nativeArray2[num31]);
						Bridge component24 = prefab16.GetComponent<Bridge>();
						NetData value48 = nativeArray3[num31];
						NetGeometryData value49 = nativeArray4[num31];
						value48.m_NodePriority += 1000f;
						if (component24.m_SegmentLength > 0.1f)
						{
							if (!component24.m_AllowMinimalLength)
							{
								value49.m_EdgeLengthRange.min = component24.m_SegmentLength * 0.6f;
							}
							value49.m_EdgeLengthRange.max = component24.m_SegmentLength * 1.4f;
						}
						value49.m_ElevatedLength = value49.m_EdgeLengthRange.max;
						value49.m_Hanging = component24.m_Hanging;
						value49.m_Flags |= GeometryFlags.StraightEdges | GeometryFlags.StraightEnds | GeometryFlags.RequireElevated | GeometryFlags.SymmetricalEdges | GeometryFlags.SmoothSlopes;
						if (component24.m_CanCurve)
						{
							value49.m_Flags &= ~GeometryFlags.StraightEdges;
						}
						switch (component24.m_BuildStyle)
						{
						case BridgeBuildStyle.Raised:
							value49.m_Flags |= GeometryFlags.ElevatedIsRaised;
							break;
						case BridgeBuildStyle.Quay:
							value49.m_Flags |= GeometryFlags.ElevatedIsRaised;
							value49.m_Flags &= ~GeometryFlags.RequireElevated;
							break;
						}
						if (nativeArray5.Length != 0)
						{
							PlaceableNetData value50 = nativeArray5[num31];
							switch (component24.m_WaterFlow)
							{
							case BridgeWaterFlow.Left:
								value50.m_PlacementFlags |= PlacementFlags.FlowLeft;
								break;
							case BridgeWaterFlow.Right:
								value50.m_PlacementFlags |= PlacementFlags.FlowRight;
								break;
							}
							if (component24.m_BuildStyle == BridgeBuildStyle.Quay)
							{
								value50.m_PlacementFlags |= PlacementFlags.ShoreLine;
							}
							value50.m_MinWaterElevation = component24.m_ElevationOnWater;
							nativeArray5[num31] = value50;
						}
						if (bufferAccessor13.Length != 0)
						{
							DynamicBuffer<FixedNetElement> dynamicBuffer12 = bufferAccessor13[num31];
							dynamicBuffer12.ResizeUninitialized(component24.m_FixedSegments.Length);
							int num32 = 0;
							bool flag13 = false;
							for (int num33 = 0; num33 < dynamicBuffer12.Length; num33++)
							{
								FixedNetSegmentInfo fixedNetSegmentInfo = component24.m_FixedSegments[num33];
								flag13 |= fixedNetSegmentInfo.m_Length <= 0.1f;
							}
							for (int num34 = 0; num34 < dynamicBuffer12.Length; num34++)
							{
								FixedNetSegmentInfo fixedNetSegmentInfo2 = component24.m_FixedSegments[num34];
								value51.m_Flags = (FixedNetFlags)0u;
								if (fixedNetSegmentInfo2.m_Length > 0.1f)
								{
									if (flag13)
									{
										value51.m_LengthRange.min = fixedNetSegmentInfo2.m_Length;
										value51.m_LengthRange.max = fixedNetSegmentInfo2.m_Length;
									}
									else
									{
										value51.m_LengthRange.min = fixedNetSegmentInfo2.m_Length * 0.6f;
										value51.m_LengthRange.max = fixedNetSegmentInfo2.m_Length * 1.4f;
									}
								}
								else
								{
									value51.m_LengthRange = value49.m_EdgeLengthRange;
								}
								if (fixedNetSegmentInfo2.m_CanCurve)
								{
									value49.m_Flags &= ~GeometryFlags.StraightEdges;
									num32++;
								}
								else
								{
									value51.m_Flags |= FixedNetFlags.Straight;
								}
								value51.m_CountRange = fixedNetSegmentInfo2.m_CountRange;
								NetCompositionHelpers.GetRequirementFlags(fixedNetSegmentInfo2.m_SetState, out value51.m_SetState, out var sectionFlags14);
								NetCompositionHelpers.GetRequirementFlags(fixedNetSegmentInfo2.m_UnsetState, out value51.m_UnsetState, out var sectionFlags15);
								if ((sectionFlags14 | sectionFlags15) != 0)
								{
									COSystemBase.baseLog.ErrorFormat(prefab16, "Net segment state ({0}) cannot (un)set section flags: {1}", prefab16.name, sectionFlags14 | sectionFlags15);
								}
								dynamicBuffer12[num34] = value51;
							}
							if (num32 >= 2)
							{
								value49.m_Flags |= GeometryFlags.NoCurveSplit;
							}
						}
						nativeArray3[num31] = value48;
						nativeArray4[num31] = value49;
					}
				}
				NativeArray<ElectricityConnectionData> nativeArray25 = archetypeChunk.GetNativeArray(ref typeHandle27);
				if (nativeArray25.Length != 0)
				{
					NativeArray<LocalConnectData> nativeArray26 = archetypeChunk.GetNativeArray(ref typeHandle8);
					for (int num35 = 0; num35 < nativeArray25.Length; num35++)
					{
						NetPrefab prefab17 = m_PrefabSystem.GetPrefab<NetPrefab>(nativeArray2[num35]);
						ElectricityConnection component25 = prefab17.GetComponent<ElectricityConnection>();
						NetData value52 = nativeArray3[num35];
						ElectricityConnectionData value53 = nativeArray25[num35];
						Layer layer5;
						Layer layer6;
						float snapDistance;
						switch (component25.m_Voltage)
						{
						case ElectricityConnection.Voltage.Low:
							layer5 = Layer.PowerlineLow;
							layer6 = Layer.Road | Layer.PowerlineLow;
							snapDistance = 4f;
							break;
						case ElectricityConnection.Voltage.High:
							layer5 = Layer.PowerlineHigh;
							layer6 = Layer.PowerlineHigh;
							snapDistance = 8f;
							break;
						default:
							layer5 = Layer.None;
							layer6 = Layer.None;
							snapDistance = 8f;
							break;
						}
						if (flag10)
						{
							value52.m_RequiredLayers |= layer5;
							value52.m_ConnectLayers |= layer5;
							LocalConnectData value54 = nativeArray26[num35];
							value54.m_Flags |= LocalConnectFlags.ExplicitNodes | LocalConnectFlags.ChooseBest;
							value54.m_Layers |= layer6;
							value54.m_HeightRange = new Bounds1(-1000f, 1000f);
							value54.m_SearchDistance = 0f;
							if (flag2)
							{
								value54.m_Flags |= LocalConnectFlags.KeepOpen;
								value54.m_SearchDistance = 4f;
							}
							nativeArray26[num35] = value54;
							if (nativeArray5.Length != 0)
							{
								PlaceableNetData value55 = nativeArray5[num35];
								value55.m_SnapDistance = snapDistance;
								nativeArray5[num35] = value55;
							}
						}
						value52.m_LocalConnectLayers |= layer5;
						value53.m_Direction = component25.m_Direction;
						value53.m_Capacity = component25.m_Capacity;
						value53.m_Voltage = component25.m_Voltage;
						NetCompositionHelpers.GetRequirementFlags(component25.m_RequireAll, out value53.m_CompositionAll, out var sectionFlags16);
						NetCompositionHelpers.GetRequirementFlags(component25.m_RequireAny, out value53.m_CompositionAny, out var sectionFlags17);
						NetCompositionHelpers.GetRequirementFlags(component25.m_RequireNone, out value53.m_CompositionNone, out var sectionFlags18);
						NetSectionFlags netSectionFlags5 = sectionFlags16 | sectionFlags17 | sectionFlags18;
						if (netSectionFlags5 != 0)
						{
							COSystemBase.baseLog.ErrorFormat(prefab17, "Electricity connection ({0}) cannot require section flags: {1}", prefab17.name, netSectionFlags5);
						}
						nativeArray3[num35] = value52;
						nativeArray25[num35] = value53;
					}
				}
				if (nativeArray23.Length != 0)
				{
					NativeArray<LocalConnectData> nativeArray27 = archetypeChunk.GetNativeArray(ref typeHandle8);
					for (int num36 = 0; num36 < nativeArray23.Length; num36++)
					{
						WaterPipeConnection component26 = m_PrefabSystem.GetPrefab<NetPrefab>(nativeArray2[num36]).GetComponent<WaterPipeConnection>();
						NetData value56 = nativeArray3[num36];
						WaterPipeConnectionData value57 = nativeArray23[num36];
						Layer layer7 = Layer.None;
						if (component26.m_FreshCapacity != 0)
						{
							layer7 |= Layer.WaterPipe;
						}
						if (component26.m_SewageCapacity != 0)
						{
							layer7 |= Layer.SewagePipe;
						}
						if (component26.m_StormCapacity != 0)
						{
							layer7 |= Layer.StormwaterPipe;
						}
						if (flag12)
						{
							value56.m_RequiredLayers |= layer7;
							value56.m_ConnectLayers |= layer7;
							LocalConnectData value58 = nativeArray27[num36];
							value58.m_Flags |= LocalConnectFlags.ExplicitNodes | LocalConnectFlags.ChooseBest;
							value58.m_Layers |= Layer.Road | layer7;
							value58.m_HeightRange = new Bounds1(-1000f, 1000f);
							value58.m_SearchDistance = 0f;
							if (flag2)
							{
								value58.m_Flags |= LocalConnectFlags.KeepOpen;
								value58.m_SearchDistance = 4f;
							}
							nativeArray27[num36] = value58;
							if (nativeArray5.Length != 0)
							{
								PlaceableNetData value59 = nativeArray5[num36];
								value59.m_SnapDistance = 4f;
								nativeArray5[num36] = value59;
							}
						}
						value56.m_LocalConnectLayers |= layer7;
						value57.m_FreshCapacity = component26.m_FreshCapacity;
						value57.m_SewageCapacity = component26.m_SewageCapacity;
						value57.m_StormCapacity = component26.m_StormCapacity;
						nativeArray3[num36] = value56;
						nativeArray23[num36] = value57;
					}
				}
				if (nativeArray24.Length != 0)
				{
					NativeArray<LocalConnectData> nativeArray28 = archetypeChunk.GetNativeArray(ref typeHandle8);
					for (int num37 = 0; num37 < nativeArray.Length; num37++)
					{
						NetData value60 = nativeArray3[num37];
						if (flag12)
						{
							value60.m_RequiredLayers |= Layer.ResourceLine;
							value60.m_ConnectLayers |= Layer.ResourceLine;
							LocalConnectData value61 = nativeArray28[num37];
							value61.m_Flags |= LocalConnectFlags.ExplicitNodes | LocalConnectFlags.ChooseBest;
							value61.m_Layers |= Layer.Pathway | Layer.ResourceLine;
							value61.m_HeightRange = new Bounds1(-1000f, 1000f);
							value61.m_SearchDistance = 0f;
							if (flag2)
							{
								value61.m_Flags |= LocalConnectFlags.KeepOpen;
								value61.m_SearchDistance = 4f;
							}
							nativeArray28[num37] = value61;
							if (nativeArray5.Length != 0)
							{
								PlaceableNetData value62 = nativeArray5[num37];
								value62.m_SnapDistance = 4f;
								nativeArray5[num37] = value62;
							}
						}
						value60.m_LocalConnectLayers |= Layer.ResourceLine;
						nativeArray3[num37] = value60;
					}
				}
				if (flag4)
				{
					for (int num38 = 0; num38 < nativeArray3.Length; num38++)
					{
						NetData netData = nativeArray3[num38];
						m_InGameLayersTwice |= m_InGameLayersOnce & netData.m_RequiredLayers;
						m_InGameLayersOnce |= netData.m_RequiredLayers;
					}
				}
			}
		}
		catch
		{
			chunks.Dispose();
			throw;
		}
		m_PathfindHeuristicData.value = new PathfindHeuristicData
		{
			m_CarCosts = new PathfindCosts(1000000f, 1000000f, 1000000f, 1000000f),
			m_TrackCosts = new PathfindCosts(1000000f, 1000000f, 1000000f, 1000000f),
			m_PedestrianCosts = new PathfindCosts(1000000f, 1000000f, 1000000f, 1000000f),
			m_FlyingCosts = new PathfindCosts(1000000f, 1000000f, 1000000f, 1000000f),
			m_TaxiCosts = new PathfindCosts(1000000f, 1000000f, 1000000f, 1000000f),
			m_OffRoadCosts = new PathfindCosts(1000000f, 1000000f, 1000000f, 1000000f)
		};
		InitializeNetDefaultsJob jobData = new InitializeNetDefaultsJob
		{
			m_Chunks = chunks,
			m_NetGeometrySectionType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometrySection_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PlaceableNetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableNetData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_RoadData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DefaultNetLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_DefaultNetLane_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetPieceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetPieceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetVertexMatchData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetVertexMatchData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableNetPieceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetPieceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetSubSectionData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetSubSection_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetSectionPieceData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetSectionPiece_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetPieceLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetPieceLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetPieceObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetPieceObject_RO_BufferLookup, ref base.CheckedStateRef)
		};
		CollectPathfindDataJob jobData2 = new CollectPathfindDataJob
		{
			m_NetLaneDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectionLaneDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ConnectionLaneData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathfindCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindCarData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathfindTrackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTrackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathfindPedestrianData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindPedestrianData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathfindTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTransportData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathfindConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathfindHeuristicData = m_PathfindHeuristicData
		};
		JobHandle job = IJobParallelForExtensions.Schedule(jobData, chunks.Length, 1, base.Dependency);
		JobHandle jobHandle = JobHandle.CombineDependencies(job, m_PathfindHeuristicDeps = JobChunkExtensions.Schedule(jobData2, m_LaneQuery, base.Dependency));
		if (flag)
		{
			JobHandle job2 = JobChunkExtensions.ScheduleParallel(new FixPlaceholdersJob
			{
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PlaceholderObjectElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceholderObjectElement_RW_BufferTypeHandle, ref base.CheckedStateRef)
			}, m_PlaceholderQuery, base.Dependency);
			jobHandle = JobHandle.CombineDependencies(jobHandle, job2);
		}
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Prefabs.NetInitializeSystem+FixPlaceholdersJob`  
- `Game.Prefabs.NetInitializeSystem+InitializeNetDefaultsJob`  
- `Game.Prefabs.NetInitializeSystem+CollectPathfindDataJob`  
- `Game.Prefabs.NetInitializeSystem+TypeHandle`  

