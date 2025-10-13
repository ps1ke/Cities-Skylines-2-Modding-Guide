# Game.Prefabs.NetCompositionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetCompositionSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CompositionQuery;
    private Game.Prefabs.NetCompositionSystem+TypeHandle __TypeHandle;

    public NetCompositionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CompositionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompositionQuery;
```

- `private Game.Prefabs.NetCompositionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Prefabs.NetCompositionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetCompositionSystem()`  

```csharp
[Preserve]
	public NetCompositionSystem()
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
		m_CompositionQuery = GetEntityQuery(ComponentType.ReadWrite<NetCompositionData>(), ComponentType.ReadWrite<NetCompositionPiece>(), ComponentType.ReadOnly<NetCompositionMeshRef>(), ComponentType.ReadOnly<Created>());
		RequireForUpdate(m_CompositionQuery);
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
		InitializeCompositionJob jobData = new InitializeCompositionJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PlaceableNetCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PlaceableNetComposition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RoadCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_RoadComposition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrackCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TrackComposition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterwayCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_WaterwayComposition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathwayCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PathwayComposition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TaxiwayCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TaxiwayComposition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TerrainCompositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_TerrainComposition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionPieceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionPiece_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionLane_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionObject_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionAreaType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionArea_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionCrosswalkType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionCrosswalk_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetCompositionCarriagewayType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Prefabs_NetCompositionCarriageway_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableNetPieceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableNetPieceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetPieceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetPieceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetCrosswalkData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCrosswalkData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetVertexMatchData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetVertexMatchData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterwayData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathwayData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiwayData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TaxiwayData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StreetLightData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StreetLightData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneDirectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LaneDirectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficSignData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrafficSignData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UtilityObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeshData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MeshData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TerrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetTerrainData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BridgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BridgeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetPieceLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetPieceLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetPieceObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetPieceObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetPieceAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_NetPieceArea_RO_BufferLookup, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CompositionQuery, base.Dependency);
	}
```


## Nested types

- `Game.Prefabs.NetCompositionSystem+InitializeCompositionJob`  
- `Game.Prefabs.NetCompositionSystem+TypeHandle`  

