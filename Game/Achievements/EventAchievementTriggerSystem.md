# Game.Achievements.EventAchievementTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EventAchievementTriggerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationEndBarrier m_ModifiactionEndBarrier;
    private Unity.Entities.EntityQuery m_TrackingQuery;
    private Unity.Entities.EntityQuery m_CreatedEventQuery;
    private Unity.Entities.EntityArchetype m_TrackingArchetype;
    private Game.Achievements.EventAchievementTriggerSystem+TypeHandle __TypeHandle;

    public EventAchievementTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    private System.Void StartTracking(Colossal.PSI.Common.AchievementId id, System.UInt32 startFrame, Unity.Entities.EntityCommandBuffer buffer);
    private System.Void StopTracking(Game.Achievements.EventAchievementTrackingData data, Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer buffer);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModifiactionEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModifiactionEndBarrier;
```

- `private Unity.Entities.EntityQuery m_TrackingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TrackingQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEventQuery;
```

- `private Unity.Entities.EntityArchetype m_TrackingArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TrackingArchetype;
```

- `private Game.Achievements.EventAchievementTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Achievements.EventAchievementTriggerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EventAchievementTriggerSystem()`  

```csharp
[Preserve]
	public EventAchievementTriggerSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ModifiactionEndBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_CreatedEventQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Events.Event>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<EventAchievement>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		m_TrackingArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<EventAchievementTrackingData>());
		m_TrackingQuery = GetEntityQuery(ComponentType.ReadWrite<EventAchievementTrackingData>());
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
		if (!m_CreatedEventQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<ArchetypeChunk> nativeArray = m_CreatedEventQuery.ToArchetypeChunkArray(Allocator.TempJob);
			BufferLookup<EventAchievementData> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_EventAchievementData_RO_BufferLookup, ref base.CheckedStateRef);
			ComponentTypeHandle<Duration> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Duration_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			ComponentTypeHandle<PrefabRef> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
			EntityCommandBuffer buffer = m_ModifiactionEndBarrier.CreateCommandBuffer();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (nativeArray[i].Has(ref typeHandle))
				{
					NativeArray<Duration> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
					NativeArray<PrefabRef> nativeArray3 = nativeArray[i].GetNativeArray(ref typeHandle2);
					for (int j = 0; j < nativeArray2.Length; j++)
					{
						DynamicBuffer<EventAchievementData> dynamicBuffer = bufferLookup[nativeArray3[j].m_Prefab];
						for (int k = 0; k < dynamicBuffer.Length; k++)
						{
							StartTracking(dynamicBuffer[k].m_ID, nativeArray2[j].m_StartFrame + dynamicBuffer[k].m_FrameDelay, buffer);
						}
					}
					continue;
				}
				NativeArray<PrefabRef> nativeArray4 = nativeArray[i].GetNativeArray(ref typeHandle2);
				for (int l = 0; l < nativeArray4.Length; l++)
				{
					DynamicBuffer<EventAchievementData> dynamicBuffer2 = bufferLookup[nativeArray4[l].m_Prefab];
					for (int m = 0; m < dynamicBuffer2.Length; m++)
					{
						StartTracking(dynamicBuffer2[m].m_ID, m_SimulationSystem.frameIndex + dynamicBuffer2[m].m_FrameDelay, buffer);
					}
				}
			}
			nativeArray.Dispose();
		}
		if (m_TrackingQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		NativeArray<EventAchievementTrackingData> nativeArray5 = m_TrackingQuery.ToComponentDataArray<EventAchievementTrackingData>(Allocator.TempJob);
		NativeArray<Entity> nativeArray6 = m_TrackingQuery.ToEntityArray(Allocator.TempJob);
		EntityCommandBuffer buffer2 = m_ModifiactionEndBarrier.CreateCommandBuffer();
		for (int n = 0; n < nativeArray5.Length; n++)
		{
			if (m_SimulationSystem.frameIndex > nativeArray5[n].m_StartFrame)
			{
				StopTracking(nativeArray5[n], nativeArray6[n], buffer2);
			}
		}
		nativeArray5.Dispose();
		nativeArray6.Dispose();
	}
```

- `private StartTracking(Colossal.PSI.Common.AchievementId id, System.UInt32 startFrame, Unity.Entities.EntityCommandBuffer buffer) : System.Void`  

```csharp
private void StartTracking(AchievementId id, uint startFrame, EntityCommandBuffer buffer)
	{
		Entity e = buffer.CreateEntity(m_TrackingArchetype);
		buffer.SetComponent(e, new EventAchievementTrackingData
		{
			m_ID = id,
			m_StartFrame = startFrame
		});
	}
```

- `private StopTracking(Game.Achievements.EventAchievementTrackingData data, Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer buffer) : System.Void`  

```csharp
private void StopTracking(EventAchievementTrackingData data, Entity entity, EntityCommandBuffer buffer)
	{
		buffer.AddComponent<Deleted>(entity);
		PlatformManager.instance.UnlockAchievement(data.m_ID);
	}
```


## Nested types

- `Game.Achievements.EventAchievementTriggerSystem+TypeHandle`  

