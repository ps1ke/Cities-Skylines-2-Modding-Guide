# Game.Objects.OutsideConnectionInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OutsideConnectionInitializeSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Unity.Entities.EntityQuery m_ExistingQuery;
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Objects.OutsideConnectionInitializeSystem+TypeHandle __TypeHandle;
    private static const System.Single kNearbyMaxDistanceSqr;

    public OutsideConnectionInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static Game.Prefabs.OutsideConnectionTransferType GetTransferType(Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionData);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private static System.Boolean TryGetNearestConnectionRandomIndex(Unity.Collections.NativeList<Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo> connections, Game.Prefabs.OutsideConnectionTransferType transferType, Unity.Mathematics.float3 position, Game.Common.RandomLocalizationIndex& randomIndex);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ExistingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExistingQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Objects.OutsideConnectionInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.OutsideConnectionInitializeSystem+TypeHandle __TypeHandle;
```

- `private static const System.Single kNearbyMaxDistanceSqr`  

```csharp
private static const System.Single kNearbyMaxDistanceSqr;
```


## Constructors

- `public OutsideConnectionInitializeSystem()`  

```csharp
[Preserve]
	public OutsideConnectionInitializeSystem()
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

- `private static GetTransferType(Unity.Entities.Entity prefab, Unity.Entities.ComponentLookup`1[[Game.Prefabs.OutsideConnectionData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& outsideConnectionData) : Game.Prefabs.OutsideConnectionTransferType`  

```csharp
private static OutsideConnectionTransferType GetTransferType(Entity prefab, ref ComponentLookup<OutsideConnectionData> outsideConnectionData)
	{
		if (!outsideConnectionData.TryGetComponent(prefab, out var componentData))
		{
			return OutsideConnectionTransferType.None;
		}
		return componentData.m_Type;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ExistingQuery = GetEntityQuery(ComponentType.ReadOnly<OutsideConnection>(), ComponentType.ReadOnly<RandomLocalizationIndex>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Created>());
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<OutsideConnection>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadWrite<RandomLocalizationIndex>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_CreatedQuery);
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
		int initialCapacity = m_ExistingQuery.CalculateEntityCount() + m_CreatedQuery.CalculateEntityCount();
		NativeList<OutsideConnectionInfo> outsideConnections = new NativeList<OutsideConnectionInfo>(initialCapacity, Allocator.TempJob);
		JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(new CollectOutsideConnectionsJob
		{
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RandomLocalizationIndexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Common_RandomLocalizationIndex_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnections = outsideConnections.AsParallelWriter()
		}, m_ExistingQuery, base.Dependency);
		InitializeLocalizationJob jobData = new InitializeLocalizationJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_RandomLocalizationIndexType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Common_RandomLocalizationIndex_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalizationCounts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LocalizationCount_RO_BufferLookup, ref base.CheckedStateRef),
			m_OutsideConnections = outsideConnections,
			m_RandomSeed = RandomSeed.Next()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_CreatedQuery, dependsOn);
		outsideConnections.Dispose(base.Dependency);
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		if (!(context.version < Version.outsideConnNames))
		{
			return;
		}
		EntityQuery entityQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<OutsideConnection>(), ComponentType.ReadOnly<Transform>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<RandomLocalizationIndex>());
		if (!entityQuery.IsEmptyIgnoreFilter)
		{
			NativeList<OutsideConnectionInfo> connections = new NativeList<OutsideConnectionInfo>(Allocator.TempJob);
			NativeArray<Entity> nativeArray = entityQuery.ToEntityArray(Allocator.TempJob);
			NativeArray<PrefabRef> nativeArray2 = entityQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			NativeArray<Transform> nativeArray3 = entityQuery.ToComponentDataArray<Transform>(Allocator.TempJob);
			RandomSeed randomSeed = RandomSeed.Next();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity prefab = nativeArray2[i].m_Prefab;
				OutsideConnectionData component;
				OutsideConnectionTransferType transferType = (base.EntityManager.TryGetComponent<OutsideConnectionData>(prefab, out component) ? component.m_Type : OutsideConnectionTransferType.None);
				float3 position = nativeArray3[i].m_Position;
				if (base.EntityManager.HasBuffer<LocalizationCount>(prefab))
				{
					DynamicBuffer<RandomLocalizationIndex> indices = base.EntityManager.AddBuffer<RandomLocalizationIndex>(nativeArray[i]);
					DynamicBuffer<LocalizationCount> buffer = base.EntityManager.GetBuffer<LocalizationCount>(prefab, isReadOnly: true);
					if (buffer.Length == 1 && TryGetNearestConnectionRandomIndex(connections, transferType, position, out var randomIndex) && randomIndex.m_Index < buffer[0].m_Count)
					{
						indices.ResizeUninitialized(1);
						indices[0] = randomIndex;
					}
					else
					{
						Random random = randomSeed.GetRandom(nativeArray[i].Index + 1);
						RandomLocalizationIndex.GenerateRandomIndices(indices, buffer, ref random);
					}
					if (indices.Length == 1)
					{
						OutsideConnectionInfo value = new OutsideConnectionInfo
						{
							m_TransferType = transferType,
							m_Position = position,
							m_RandomIndex = indices[0]
						};
						connections.Add(in value);
					}
				}
			}
			nativeArray.Dispose();
			nativeArray2.Dispose();
			nativeArray3.Dispose();
			connections.Dispose();
		}
		entityQuery.Dispose();
	}
```

- `private static TryGetNearestConnectionRandomIndex(Unity.Collections.NativeList<Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo> connections, Game.Prefabs.OutsideConnectionTransferType transferType, Unity.Mathematics.float3 position, Game.Common.RandomLocalizationIndex& randomIndex) : System.Boolean`  

```csharp
private static bool TryGetNearestConnectionRandomIndex(NativeList<OutsideConnectionInfo> connections, OutsideConnectionTransferType transferType, float3 position, out RandomLocalizationIndex randomIndex)
	{
		randomIndex = default(RandomLocalizationIndex);
		float num = 10000f;
		foreach (OutsideConnectionInfo item in connections)
		{
			if ((item.m_TransferType & transferType) != OutsideConnectionTransferType.None)
			{
				float num2 = math.distancesq(item.m_Position, position);
				if (num2 < num)
				{
					randomIndex = item.m_RandomIndex;
					num = num2;
				}
			}
		}
		return num < 10000f;
	}
```


## Nested types

- `Game.Objects.OutsideConnectionInitializeSystem+CollectOutsideConnectionsJob`  
- `Game.Objects.OutsideConnectionInitializeSystem+InitializeLocalizationJob`  
- `Game.Objects.OutsideConnectionInitializeSystem+OutsideConnectionInfo`  
- `Game.Objects.OutsideConnectionInitializeSystem+TypeHandle`  

