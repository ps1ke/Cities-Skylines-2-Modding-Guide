# Game.Simulation.BatteryAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatteryAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BatteryQuery;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.BatteryAISystem+TypeHandle __TypeHandle;

    public BatteryAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BatteryQuery`  

```csharp
private Unity.Entities.EntityQuery m_BatteryQuery;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.BatteryAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BatteryAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BatteryAISystem()`  

```csharp
[Preserve]
	public BatteryAISystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 128;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 0;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_BatteryQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.Battery>(), ComponentType.ReadOnly<ElectricityBuildingConnection>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_SettingsQuery = GetEntityQuery(ComponentType.ReadOnly<ElectricityParameterData>());
		RequireForUpdate(m_BatteryQuery);
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
		BatteryTickJob jobData = new BatteryTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Simulation_ElectricityBuildingConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BatteryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Battery_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EmergencyGeneratorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_EmergencyGenerator_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BatteryDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BatteryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EmergencyGeneratorDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EmergencyGeneratorData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourceConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ResourceConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUsages = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUsage_RW_ComponentLookup, ref base.CheckedStateRef),
			m_FlowEdges = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ElectricityFlowEdge_RW_ComponentLookup, ref base.CheckedStateRef),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_ElectricityParameterData = m_SettingsQuery.GetSingleton<ElectricityParameterData>()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_BatteryQuery, base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.BatteryAISystem+BatteryTickJob`  
- `Game.Simulation.BatteryAISystem+TypeHandle`  

