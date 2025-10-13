# Game.Simulation.XPBuiltSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class XPBuiltSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuiltGroup;
    private Unity.Entities.EntityQuery m_ElectricityGroup;
    private Game.Simulation.XPSystem m_XPSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
    private Game.Simulation.XPBuiltSystem+TypeHandle __TypeHandle;
    private static readonly System.Int32 kElectricityGridXPBonus;

    public XPBuiltSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuiltGroup`  

```csharp
private Unity.Entities.EntityQuery m_BuiltGroup;
```

- `private Unity.Entities.EntityQuery m_ElectricityGroup`  

```csharp
private Unity.Entities.EntityQuery m_ElectricityGroup;
```

- `private Game.Simulation.XPSystem m_XPSystem`  

```csharp
private Game.Simulation.XPSystem m_XPSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationEndBarrier;
```

- `private Game.Simulation.XPBuiltSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.XPBuiltSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Int32 kElectricityGridXPBonus`  

```csharp
private static readonly System.Int32 kElectricityGridXPBonus;
```


## Constructors

- `public XPBuiltSystem()`  

```csharp
[Preserve]
	public XPBuiltSystem()
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
		m_XPSystem = base.World.GetOrCreateSystemManaged<XPSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_ModificationEndBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_BuiltGroup = GetEntityQuery(ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		m_ElectricityGroup = GetEntityQuery(ComponentType.ReadOnly<ElectricityConsumer>(), ComponentType.Exclude<Temp>());
		RequireAnyForUpdate(m_BuiltGroup, m_ElectricityGroup);
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
		if (m_ToolSystem.actionMode.IsGame())
		{
			JobHandle deps;
			NativeQueue<XPGain> queue = m_XPSystem.GetQueue(out deps);
			if (!m_BuiltGroup.IsEmptyIgnoreFilter)
			{
				XPBuiltJob jobData = new XPBuiltJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PlaceableObjectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_SignatureBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PlacedSignatureBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlacedSignatureBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ServiceUpgradeDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_XPQueue = queue,
					m_CommandBuffer = m_ModificationEndBarrier.CreateCommandBuffer().AsParallelWriter()
				};
				base.Dependency = JobChunkExtensions.Schedule(jobData, m_BuiltGroup, JobHandle.CombineDependencies(deps, base.Dependency));
			}
			if ((base.EntityManager.GetComponentData<XP>(m_CitySystem.City).m_XPRewardRecord & XPRewardFlags.ElectricityGridBuilt) == 0 && !m_ElectricityGroup.IsEmptyIgnoreFilter)
			{
				XPElectricityJob jobData2 = new XPElectricityJob
				{
					m_ElectricityConsumers = m_ElectricityGroup.ToComponentDataArray<ElectricityConsumer>(Allocator.TempJob),
					m_City = m_CitySystem.City,
					m_CityXPs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_XP_RW_ComponentLookup, ref base.CheckedStateRef),
					m_XPQueue = queue
				};
				base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
			}
			m_XPSystem.AddQueueWriter(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.XPBuiltSystem+XPBuiltJob`  
- `Game.Simulation.XPBuiltSystem+XPElectricityJob`  
- `Game.Simulation.XPBuiltSystem+TypeHandle`  

