# Game.Events.InitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class InitializeSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_InstanceQuery;
    private Unity.Entities.EntityQuery m_DisasterConfigQuery;
    private Unity.Entities.EntityQuery m_TargetQuery;
    private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
    private Unity.Entities.EntityArchetype m_IgniteEventArchetype;
    private Unity.Entities.EntityArchetype m_ImpactEventArchetype;
    private Unity.Entities.EntityArchetype m_AccidentSiteEventArchetype;
    private Unity.Entities.EntityArchetype m_HealthEventArchetype;
    private Unity.Entities.EntityArchetype m_DamageEventArchetype;
    private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
    private Unity.Entities.EntityArchetype m_SpectateEventArchetype;
    private Unity.Entities.EntityArchetype m_CriminalEventArchetype;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
    private Game.Events.InitializeSystem+TypeHandle __TypeHandle;

    public InitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void AddRandomTarget(Unity.Entities.DynamicBuffer<Game.Events.TargetElement> targets, Game.Prefabs.EventTargetType targetType, Game.Prefabs.TransportType transportType);
    private System.Int32 CountInstances(Unity.Entities.Entity prefab);
    private Unity.Mathematics.float3 FindRandomLocation(Unity.Mathematics.Random& random);
    private Unity.Entities.EntityCommandBuffer GetCommandBuffer();
    private System.Void InitializeCalendarEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeCrimeEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeDestruction(Unity.Entities.Entity eventEntity);
    private System.Void InitializeFire(Unity.Entities.Entity eventEntity);
    private System.Void InitializeHealthEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeMeetingEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeSpectatorEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeTrafficAccident(Unity.Entities.Entity eventEntity);
    private System.Void InitializeWaterLevelChangeEvent(Unity.Entities.Entity eventEntity);
    private System.Void InitializeWeatherEvent(Unity.Entities.Entity eventEntity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_InstanceQuery`  

```csharp
private Unity.Entities.EntityQuery m_InstanceQuery;
```

- `private Unity.Entities.EntityQuery m_DisasterConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_DisasterConfigQuery;
```

- `private Unity.Entities.EntityQuery m_TargetQuery`  

```csharp
private Unity.Entities.EntityQuery m_TargetQuery;
```

- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_EDWSBuildingQuery;
```

- `private Unity.Entities.EntityArchetype m_IgniteEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_IgniteEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_ImpactEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ImpactEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_AccidentSiteEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AccidentSiteEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_HealthEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HealthEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DamageEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_DestroyEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_SpectateEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_SpectateEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_CriminalEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_CriminalEventArchetype;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Unity.Entities.EntityCommandBuffer m_CommandBuffer`  

```csharp
private Unity.Entities.EntityCommandBuffer m_CommandBuffer;
```

- `private Game.Events.InitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.InitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public InitializeSystem()`  

```csharp
[Preserve]
	public InitializeSystem()
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

- `private AddRandomTarget(Unity.Entities.DynamicBuffer<Game.Events.TargetElement> targets, Game.Prefabs.EventTargetType targetType, Game.Prefabs.TransportType transportType) : System.Void`  

```csharp
private void AddRandomTarget(DynamicBuffer<TargetElement> targets, EventTargetType targetType, TransportType transportType)
	{
		NativeValue<Entity> result = new NativeValue<Entity>(Allocator.TempJob);
		try
		{
			IJobExtensions.Run(new RandomEventTargetJob
			{
				m_TargetChunks = m_TargetQuery.ToArchetypeChunkArray(Allocator.TempJob),
				m_TargetType = targetType,
				m_TransportType = transportType,
				m_RandomSeed = RandomSeed.Next(),
				m_Result = result,
				m_EntitiesType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TransportDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportDepot_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TreeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabTransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentLookup, ref base.CheckedStateRef)
			});
			if (result.value != Entity.Null)
			{
				targets.Add(new TargetElement(result.value));
			}
		}
		finally
		{
			result.Dispose();
		}
	}
```

- `private CountInstances(Unity.Entities.Entity prefab) : System.Int32`  

```csharp
private int CountInstances(Entity prefab)
	{
		ComponentTypeHandle<PrefabRef> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		NativeArray<ArchetypeChunk> nativeArray = m_InstanceQuery.ToArchetypeChunkArray(Allocator.Temp);
		CompleteDependency();
		int num = 0;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			NativeArray<PrefabRef> nativeArray2 = nativeArray[i].GetNativeArray(ref typeHandle);
			for (int j = 0; j < nativeArray2.Length; j++)
			{
				if (nativeArray2[j].m_Prefab == prefab)
				{
					num++;
				}
			}
		}
		nativeArray.Dispose();
		return num;
	}
```

- `private FindRandomLocation(Unity.Mathematics.Random& random) : Unity.Mathematics.float3`  

```csharp
private float3 FindRandomLocation(ref Unity.Mathematics.Random random)
	{
		return new float3
		{
			xz = random.NextFloat2(-6000f, 6000f)
		};
	}
```

- `private GetCommandBuffer() : Unity.Entities.EntityCommandBuffer`  

```csharp
private EntityCommandBuffer GetCommandBuffer()
	{
		if (!m_CommandBuffer.IsCreated)
		{
			m_CommandBuffer = new EntityCommandBuffer(Allocator.TempJob);
		}
		return m_CommandBuffer;
	}
```

- `private InitializeCalendarEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeCalendarEvent(Entity eventEntity)
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		CalendarEventData componentData2 = base.EntityManager.GetComponentData<CalendarEventData>(componentData.m_Prefab);
		Duration componentData3 = base.EntityManager.GetComponentData<Duration>(eventEntity);
		componentData3.m_StartFrame = m_SimulationSystem.frameIndex;
		componentData3.m_EndFrame = componentData3.m_StartFrame + (uint)(componentData2.m_Duration * 262144 / 4);
		base.EntityManager.SetComponentData(eventEntity, componentData3);
		GetCommandBuffer().AddComponent<FindingEventParticipants>(eventEntity);
	}
```

- `private InitializeCrimeEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeCrimeEvent(Entity eventEntity)
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		CrimeData componentData2 = base.EntityManager.GetComponentData<CrimeData>(componentData.m_Prefab);
		if (componentData2.m_RandomTargetType == EventTargetType.None)
		{
			return;
		}
		DynamicBuffer<TargetElement> buffer = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
		if (buffer.Length == 0)
		{
			AddRandomTarget(buffer, componentData2.m_RandomTargetType, TransportType.None);
		}
		RandomSeed.Next().GetRandom(eventEntity.Index);
		EntityCommandBuffer commandBuffer = GetCommandBuffer();
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity entity = buffer[i].m_Entity;
			if (base.EntityManager.TryGetComponent<Game.Creatures.Resident>(entity, out var component))
			{
				entity = component.m_Citizen;
				buffer[i] = new TargetElement(entity);
			}
			if (base.EntityManager.TryGetComponent<Citizen>(entity, out var _))
			{
				CriminalFlags criminalFlags = CriminalFlags.Planning;
				if (componentData2.m_CrimeType == CrimeType.Robbery)
				{
					criminalFlags |= CriminalFlags.Robber;
				}
				Entity e = commandBuffer.CreateEntity(m_CriminalEventArchetype);
				commandBuffer.SetComponent(e, new AddCriminal
				{
					m_Event = eventEntity,
					m_Target = entity,
					m_Flags = criminalFlags
				});
			}
		}
	}
```

- `private InitializeDestruction(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeDestruction(Entity eventEntity)
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		DestructionData componentData2 = base.EntityManager.GetComponentData<DestructionData>(componentData.m_Prefab);
		if (componentData2.m_RandomTargetType == EventTargetType.None)
		{
			return;
		}
		DynamicBuffer<TargetElement> buffer = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
		if (buffer.Length == 0)
		{
			AddRandomTarget(buffer, componentData2.m_RandomTargetType, TransportType.None);
		}
		EntityCommandBuffer commandBuffer = GetCommandBuffer();
		IconCommandBuffer iconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer();
		DisasterConfigurationData disasterConfigurationData = default(DisasterConfigurationData);
		if (!m_DisasterConfigQuery.IsEmpty)
		{
			disasterConfigurationData = m_DisasterConfigQuery.GetSingleton<DisasterConfigurationData>();
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity entity = buffer[i].m_Entity;
			Entity e = commandBuffer.CreateEntity(m_DamageEventArchetype);
			commandBuffer.SetComponent(e, new Damage
			{
				m_Object = entity,
				m_Delta = new float3(1f, 0f, 0f)
			});
			Entity e2 = commandBuffer.CreateEntity(m_DestroyEventArchetype);
			commandBuffer.SetComponent(e2, new Destroy
			{
				m_Event = eventEntity,
				m_Object = entity
			});
			if (disasterConfigurationData.m_DestroyedNotificationPrefab != Entity.Null)
			{
				iconCommandBuffer.Remove(entity, IconPriority.Problem);
				iconCommandBuffer.Remove(entity, IconPriority.FatalProblem);
				iconCommandBuffer.Add(entity, disasterConfigurationData.m_DestroyedNotificationPrefab, IconPriority.FatalProblem, IconClusterLayer.Default, IconFlags.IgnoreTarget, eventEntity);
			}
		}
	}
```

- `private InitializeFire(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeFire(Entity eventEntity)
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		FireData componentData2 = base.EntityManager.GetComponentData<FireData>(componentData.m_Prefab);
		if (componentData2.m_RandomTargetType != EventTargetType.None)
		{
			DynamicBuffer<TargetElement> buffer = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
			if (buffer.Length == 0)
			{
				AddRandomTarget(buffer, componentData2.m_RandomTargetType, TransportType.None);
			}
			EntityCommandBuffer commandBuffer = GetCommandBuffer();
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity entity = buffer[i].m_Entity;
				Entity e = commandBuffer.CreateEntity(m_IgniteEventArchetype);
				commandBuffer.SetComponent(e, new Ignite
				{
					m_Event = eventEntity,
					m_Target = entity,
					m_Intensity = componentData2.m_StartIntensity
				});
			}
		}
	}
```

- `private InitializeHealthEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeHealthEvent(Entity eventEntity)
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		HealthEventData componentData2 = base.EntityManager.GetComponentData<HealthEventData>(componentData.m_Prefab);
		if (componentData2.m_RandomTargetType == EventTargetType.None)
		{
			return;
		}
		DynamicBuffer<TargetElement> buffer = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
		if (buffer.Length == 0)
		{
			AddRandomTarget(buffer, componentData2.m_RandomTargetType, TransportType.None);
		}
		Unity.Mathematics.Random random = RandomSeed.Next().GetRandom(eventEntity.Index);
		EntityCommandBuffer commandBuffer = GetCommandBuffer();
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity entity = buffer[i].m_Entity;
			if (base.EntityManager.TryGetComponent<Game.Creatures.Resident>(entity, out var component))
			{
				entity = component.m_Citizen;
				buffer[i] = new TargetElement(entity);
			}
			if (base.EntityManager.TryGetComponent<Citizen>(entity, out var component2))
			{
				HealthProblemFlags healthProblemFlags = HealthProblemFlags.None;
				switch (componentData2.m_HealthEventType)
				{
				case HealthEventType.Disease:
					healthProblemFlags |= HealthProblemFlags.Sick;
					break;
				case HealthEventType.Injury:
					healthProblemFlags |= HealthProblemFlags.Injured;
					break;
				case HealthEventType.Death:
					healthProblemFlags |= HealthProblemFlags.Dead;
					break;
				}
				float num = math.lerp(componentData2.m_TransportProbability.max, componentData2.m_TransportProbability.min, (float)(int)component2.m_Health * 0.01f);
				if (random.NextFloat(100f) < num)
				{
					healthProblemFlags |= HealthProblemFlags.RequireTransport;
				}
				Entity e = commandBuffer.CreateEntity(m_HealthEventArchetype);
				if (componentData2.m_RequireTracking)
				{
					commandBuffer.SetComponent(e, new AddHealthProblem
					{
						m_Event = eventEntity,
						m_Target = entity,
						m_Flags = healthProblemFlags
					});
				}
				else
				{
					commandBuffer.SetComponent(e, new AddHealthProblem
					{
						m_Target = entity,
						m_Flags = healthProblemFlags
					});
				}
			}
		}
		if (!componentData2.m_RequireTracking)
		{
			buffer.Clear();
		}
	}
```

- `private InitializeMeetingEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeMeetingEvent(Entity eventEntity)
	{
		DynamicBuffer<CoordinatedMeetingAttendee> buffer = base.EntityManager.GetBuffer<CoordinatedMeetingAttendee>(eventEntity);
		DynamicBuffer<TargetElement> buffer2 = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
		for (int i = 0; i < buffer2.Length; i++)
		{
			Entity entity = buffer2[i].m_Entity;
			if (base.EntityManager.HasComponent<HouseholdCitizen>(entity) && !base.EntityManager.HasComponent<AttendingEvent>(entity))
			{
				DynamicBuffer<HouseholdCitizen> buffer3 = base.EntityManager.GetBuffer<HouseholdCitizen>(entity, isReadOnly: true);
				for (int j = 0; j < buffer3.Length; j++)
				{
					buffer.Add(new CoordinatedMeetingAttendee
					{
						m_Attendee = buffer3[j].m_Citizen
					});
				}
			}
			else if (base.EntityManager.HasComponent<Citizen>(entity))
			{
				buffer.Add(new CoordinatedMeetingAttendee
				{
					m_Attendee = entity
				});
			}
		}
	}
```

- `private InitializeSpectatorEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeSpectatorEvent(Entity eventEntity)
	{
		Duration componentData = base.EntityManager.GetComponentData<Duration>(eventEntity);
		PrefabRef componentData2 = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		SpectatorEventData componentData3 = base.EntityManager.GetComponentData<SpectatorEventData>(componentData2.m_Prefab);
		if (componentData3.m_RandomSiteType != EventTargetType.None)
		{
			DynamicBuffer<TargetElement> buffer = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
			if (buffer.Length == 0)
			{
				if (base.EntityManager.TryGetComponent<VehicleLaunchData>(componentData2.m_Prefab, out var component))
				{
					AddRandomTarget(buffer, componentData3.m_RandomSiteType, component.m_TransportType);
				}
				else
				{
					AddRandomTarget(buffer, componentData3.m_RandomSiteType, TransportType.None);
				}
			}
			EntityCommandBuffer commandBuffer = GetCommandBuffer();
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity entity = buffer[i].m_Entity;
				Entity e = commandBuffer.CreateEntity(m_SpectateEventArchetype);
				commandBuffer.SetComponent(e, new Spectate
				{
					m_Event = eventEntity,
					m_Target = entity
				});
			}
		}
		componentData.m_StartFrame = m_SimulationSystem.frameIndex + (uint)(262144f * componentData3.m_PreparationDuration);
		componentData.m_EndFrame = componentData.m_StartFrame + (uint)(262144f * componentData3.m_ActiveDuration);
		base.EntityManager.SetComponentData(eventEntity, componentData);
	}
```

- `private InitializeTrafficAccident(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeTrafficAccident(Entity eventEntity)
	{
		PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		TrafficAccidentData componentData2 = base.EntityManager.GetComponentData<TrafficAccidentData>(componentData.m_Prefab);
		if (componentData2.m_RandomSiteType == EventTargetType.None)
		{
			return;
		}
		DynamicBuffer<TargetElement> buffer = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
		if (buffer.Length == 0)
		{
			AddRandomTarget(buffer, componentData2.m_RandomSiteType, TransportType.None);
		}
		Unity.Mathematics.Random random = RandomSeed.Next().GetRandom(eventEntity.Index);
		EntityCommandBuffer commandBuffer = GetCommandBuffer();
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity entity = buffer[i].m_Entity;
			Road component3;
			if (base.EntityManager.TryGetComponent<Moving>(entity, out var component))
			{
				Impact component2 = new Impact
				{
					m_Event = eventEntity,
					m_Target = entity,
					m_Severity = 5f
				};
				if (random.NextBool())
				{
					component2.m_AngularVelocityDelta.y = -2f;
					component2.m_VelocityDelta.xz = component2.m_Severity * MathUtils.Left(math.normalizesafe(component.m_Velocity.xz));
				}
				else
				{
					component2.m_AngularVelocityDelta.y = 2f;
					component2.m_VelocityDelta.xz = component2.m_Severity * MathUtils.Right(math.normalizesafe(component.m_Velocity.xz));
				}
				Entity e = commandBuffer.CreateEntity(m_ImpactEventArchetype);
				commandBuffer.SetComponent(e, component2);
			}
			else if (base.EntityManager.TryGetComponent<Road>(entity, out component3))
			{
				AddAccidentSite component4 = new AddAccidentSite
				{
					m_Event = eventEntity,
					m_Target = entity,
					m_Flags = (AccidentSiteFlags.StageAccident | AccidentSiteFlags.TrafficAccident)
				};
				Entity e2 = commandBuffer.CreateEntity(m_AccidentSiteEventArchetype);
				commandBuffer.SetComponent(e2, component4);
			}
		}
	}
```

- `private InitializeWaterLevelChangeEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeWaterLevelChangeEvent(Entity eventEntity)
	{
		WaterLevelChange componentData = base.EntityManager.GetComponentData<WaterLevelChange>(eventEntity);
		PrefabRef componentData2 = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		WaterLevelChangeData componentData3 = base.EntityManager.GetComponentData<WaterLevelChangeData>(componentData2.m_Prefab);
		Duration componentData4 = base.EntityManager.GetComponentData<Duration>(eventEntity);
		float num = RandomSeed.Next().GetRandom(eventEntity.Index).NextFloat();
		componentData.m_MaxIntensity = 0.3f + 0.7f * num * num;
		componentData.m_Direction = new float2(0f, 1f);
		EntityQuery entityQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Simulation.WaterSourceData>(), ComponentType.ReadOnly<Game.Objects.Transform>());
		NativeArray<Game.Simulation.WaterSourceData> nativeArray = entityQuery.ToComponentDataArray<Game.Simulation.WaterSourceData>(Allocator.TempJob);
		NativeArray<Game.Objects.Transform> nativeArray2 = entityQuery.ToComponentDataArray<Game.Objects.Transform>(Allocator.TempJob);
		componentData4.m_StartFrame = m_SimulationSystem.frameIndex;
		if (componentData3.m_ChangeType == WaterLevelChangeType.Sine)
		{
			componentData4.m_EndFrame = (uint)(componentData4.m_StartFrame + Mathf.CeilToInt((float)WaterLevelChangeSystem.TsunamiEndDelay + 12000f * componentData.m_MaxIntensity));
		}
		else
		{
			componentData4.m_EndFrame = componentData4.m_StartFrame + 10000;
		}
		base.EntityManager.SetComponentData(eventEntity, componentData4);
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Game.Simulation.WaterSourceData source = nativeArray[i];
			Game.Objects.Transform transform = nativeArray2[i];
			if (((source.m_ConstantDepth == 2 && (componentData3.m_TargetType & WaterLevelTargetType.River) != WaterLevelTargetType.None) || (source.m_ConstantDepth == 3 && (componentData3.m_TargetType & WaterLevelTargetType.Sea) != WaterLevelTargetType.None)) && WaterSystem.SourceMatchesDirection(source, transform, componentData.m_Direction))
			{
				componentData.m_DangerHeight = math.max(componentData.m_DangerHeight, source.m_Amount + source.m_Multiplier * componentData.m_MaxIntensity * 2f);
			}
		}
		nativeArray.Dispose();
		nativeArray2.Dispose();
		base.EntityManager.SetComponentData(eventEntity, componentData);
	}
```

- `private InitializeWeatherEvent(Unity.Entities.Entity eventEntity) : System.Void`  

```csharp
private void InitializeWeatherEvent(Entity eventEntity)
	{
		WeatherPhenomenon componentData = base.EntityManager.GetComponentData<WeatherPhenomenon>(eventEntity);
		Duration componentData2 = base.EntityManager.GetComponentData<Duration>(eventEntity);
		DynamicBuffer<TargetElement> buffer = base.EntityManager.GetBuffer<TargetElement>(eventEntity);
		PrefabRef componentData3 = base.EntityManager.GetComponentData<PrefabRef>(eventEntity);
		WeatherPhenomenonData componentData4 = base.EntityManager.GetComponentData<WeatherPhenomenonData>(componentData3.m_Prefab);
		DynamicBuffer<HotspotFrame> buffer2 = base.EntityManager.GetBuffer<HotspotFrame>(eventEntity);
		Unity.Mathematics.Random random = RandomSeed.Next().GetRandom(eventEntity.Index);
		if (componentData.m_PhenomenonRadius == 0f)
		{
			componentData.m_PhenomenonRadius = random.NextFloat(componentData4.m_PhenomenonRadius.min, componentData4.m_PhenomenonRadius.max);
		}
		if (componentData.m_HotspotRadius == 0f)
		{
			componentData.m_HotspotRadius = componentData.m_PhenomenonRadius * random.NextFloat(componentData4.m_HotspotRadius.min, componentData4.m_HotspotRadius.max);
		}
		if (componentData2.m_StartFrame == 0)
		{
			float value = 0f;
			if (componentData4.m_DangerFlags != 0)
			{
				DynamicBuffer<CityModifier> buffer3 = base.EntityManager.GetBuffer<CityModifier>(m_CitySystem.City, isReadOnly: true);
				CityUtils.ApplyModifier(ref value, buffer3, CityModifierType.DisasterWarningTime);
			}
			componentData2.m_StartFrame = m_SimulationSystem.frameIndex + (uint)(value * 60f);
		}
		if (componentData2.m_EndFrame == 0)
		{
			float num = random.NextFloat(componentData4.m_Duration.min, componentData4.m_Duration.max);
			componentData2.m_EndFrame = componentData2.m_StartFrame + (uint)(num * 60f);
		}
		bool flag = !componentData.m_PhenomenonPosition.Equals(default(float3));
		for (int i = 0; i < buffer.Length; i++)
		{
			if (flag)
			{
				break;
			}
			Entity entity = buffer[i].m_Entity;
			if (base.EntityManager.TryGetComponent<Game.Objects.Transform>(entity, out var component))
			{
				componentData.m_PhenomenonPosition = component.m_Position;
				flag = true;
			}
		}
		if (!flag)
		{
			componentData.m_PhenomenonPosition = FindRandomLocation(ref random);
		}
		if (componentData.m_HotspotPosition.Equals(default(float3)))
		{
			componentData.m_HotspotPosition = componentData.m_PhenomenonPosition;
			componentData.m_HotspotPosition.xz += random.NextFloat2Direction() * random.NextFloat(componentData.m_PhenomenonRadius - componentData.m_HotspotRadius);
		}
		if (componentData.m_LightningTimer == 0f && componentData4.m_LightningInterval.min > 0.001f)
		{
			float min = componentData4.m_LightningInterval.min;
			min = math.min(min, (float)(componentData2.m_EndFrame - componentData2.m_StartFrame) / 60f);
			componentData.m_LightningTimer = 5f + math.max(0f, min - 10f);
		}
		buffer2.ResizeUninitialized(4);
		for (int j = 0; j < buffer2.Length; j++)
		{
			buffer2[j] = new HotspotFrame(componentData);
		}
		if (base.EntityManager.HasComponent<EarlyDisasterWarningEventData>(componentData3.m_Prefab) && !m_EDWSBuildingQuery.IsEmptyIgnoreFilter)
		{
			foreach (Entity item in m_EDWSBuildingQuery.ToEntityArray(Allocator.Temp))
			{
				base.EntityManager.AddComponentData(item, new EarlyDisasterWarningDuration
				{
					m_EndFrame = componentData2.m_EndFrame
				});
			}
		}
		base.EntityManager.SetComponentData(eventEntity, componentData);
		base.EntityManager.SetComponentData(eventEntity, componentData2);
		base.EntityManager.SetComponentData(eventEntity, new InterpolatedTransform(componentData));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Event>());
		m_InstanceQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.Exclude<Deleted>());
		m_DisasterConfigQuery = GetEntityQuery(ComponentType.ReadOnly<DisasterConfigurationData>());
		m_TargetQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[5]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Tree>(),
				ComponentType.ReadOnly<Road>(),
				ComponentType.ReadOnly<Citizen>(),
				ComponentType.ReadOnly<Household>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_EDWSBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.EarlyDisasterWarningSystem>());
		m_IgniteEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Ignite>());
		m_ImpactEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Impact>());
		m_AccidentSiteEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<AddAccidentSite>());
		m_HealthEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<AddHealthProblem>());
		m_DamageEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Damage>());
		m_DestroyEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Destroy>());
		m_SpectateEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<Spectate>());
		m_CriminalEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<AddCriminal>());
		RequireForUpdate(m_EventQuery);
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
		NativeArray<Entity> nativeArray = m_EventQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			NativeQueue<TriggerAction> nativeQueue = m_TriggerSystem.CreateActionBuffer();
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity entity = nativeArray[i];
				PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(entity);
				EventData componentData2 = base.EntityManager.GetComponentData<EventData>(componentData.m_Prefab);
				if (componentData2.m_ConcurrentLimit > 0 && CountInstances(componentData.m_Prefab) > componentData2.m_ConcurrentLimit)
				{
					base.EntityManager.AddComponent<Deleted>(entity);
					continue;
				}
				if (base.EntityManager.HasComponent<Fire>(entity))
				{
					InitializeFire(entity);
				}
				if (base.EntityManager.HasComponent<TrafficAccident>(entity))
				{
					InitializeTrafficAccident(entity);
				}
				if (base.EntityManager.HasComponent<WeatherPhenomenon>(entity))
				{
					InitializeWeatherEvent(entity);
				}
				if (base.EntityManager.HasComponent<HealthEvent>(entity))
				{
					InitializeHealthEvent(entity);
				}
				if (base.EntityManager.HasComponent<Destruction>(entity))
				{
					InitializeDestruction(entity);
				}
				if (base.EntityManager.HasComponent<SpectatorEvent>(entity))
				{
					InitializeSpectatorEvent(entity);
				}
				if (base.EntityManager.HasComponent<Crime>(entity))
				{
					InitializeCrimeEvent(entity);
				}
				if (base.EntityManager.HasComponent<WaterLevelChange>(entity))
				{
					InitializeWaterLevelChangeEvent(entity);
				}
				if (base.EntityManager.HasComponent<CalendarEvent>(entity))
				{
					InitializeCalendarEvent(entity);
				}
				if (base.EntityManager.HasComponent<CoordinatedMeeting>(entity))
				{
					InitializeMeetingEvent(entity);
				}
				if (base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<TargetElement> buffer) && buffer.Length > 0)
				{
					for (int j = 0; j < buffer.Length; j++)
					{
						nativeQueue.Enqueue(new TriggerAction
						{
							m_TriggerPrefab = componentData.m_Prefab,
							m_PrimaryTarget = buffer[j].m_Entity,
							m_SecondaryTarget = Entity.Null,
							m_TriggerType = TriggerType.EventHappened
						});
					}
				}
				else
				{
					nativeQueue.Enqueue(new TriggerAction
					{
						m_TriggerPrefab = componentData.m_Prefab,
						m_PrimaryTarget = Entity.Null,
						m_SecondaryTarget = Entity.Null,
						m_TriggerType = TriggerType.EventHappened
					});
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		if (m_CommandBuffer.IsCreated)
		{
			m_CommandBuffer.Playback(base.EntityManager);
			m_CommandBuffer.Dispose();
		}
	}
```


## Nested types

- `Game.Events.InitializeSystem+RandomEventTargetJob`  
- `Game.Events.InitializeSystem+TypeHandle`  

