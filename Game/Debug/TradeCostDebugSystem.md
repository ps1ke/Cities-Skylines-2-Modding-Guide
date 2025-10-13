# Game.Debug.TradeCostDebugSystem

**Assembly:** `Game`  
**Namespace:** `Game.Debug`  

**Type:** class public  

**Base:** `Game.Debug.BaseDebugSystem`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TradeCostDebugSystem : Game.Debug.BaseDebugSystem
{
    private Unity.Entities.EntityQuery m_StorageGroup;
    private Colossal.GizmosSystem m_GizmosSystem;
    private Game.Economy.Resource m_SelectedResource;
    private Game.Debug.BaseDebugSystem+Option m_StorageOption;
    private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
    private Game.Debug.TradeCostDebugSystem+TypeHandle __TypeHandle;

    public TradeCostDebugSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Int32 <OnEnabled>b__6_0();
    private System.Void <OnEnabled>b__6_1(System.Int32 value);
    private System.Int32 <OnEnabled>b__6_2();
    private System.Void <OnEnabled>b__6_3(System.Int32 value);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    public virtual System.Void OnEnabled(UnityEngine.Rendering.DebugUI+Container container);
    protected virtual Unity.Jobs.JobHandle OnUpdate(Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_StorageGroup`  

```csharp
private Unity.Entities.EntityQuery m_StorageGroup;
```

- `private Colossal.GizmosSystem m_GizmosSystem`  

```csharp
private Colossal.GizmosSystem m_GizmosSystem;
```

- `private Game.Economy.Resource m_SelectedResource`  

```csharp
private Game.Economy.Resource m_SelectedResource;
```

- `private Game.Debug.BaseDebugSystem+Option m_StorageOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_StorageOption;
```

- `private Game.Debug.BaseDebugSystem+Option m_CompanyOption`  

```csharp
private Game.Debug.BaseDebugSystem+Option m_CompanyOption;
```

- `private Game.Debug.TradeCostDebugSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Debug.TradeCostDebugSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TradeCostDebugSystem()`  

```csharp
[Preserve]
	public TradeCostDebugSystem()
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

- `private <OnEnabled>b__6_0() : System.Int32`  

```csharp
private System.Int32 <OnEnabled>b__6_0();
```

- `private <OnEnabled>b__6_1(System.Int32 value) : System.Void`  

```csharp
private System.Void <OnEnabled>b__6_1(System.Int32 value);
```

- `private <OnEnabled>b__6_2() : System.Int32`  

```csharp
private System.Int32 <OnEnabled>b__6_2();
```

- `private <OnEnabled>b__6_3(System.Int32 value) : System.Void`  

```csharp
private System.Void <OnEnabled>b__6_3(System.Int32 value);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_StorageOption = AddOption("Warehouses", defaultEnabled: true);
		m_CompanyOption = AddOption("Companies", defaultEnabled: false);
		m_GizmosSystem = base.World.GetOrCreateSystemManaged<GizmosSystem>();
		m_StorageGroup = GetEntityQuery(ComponentType.ReadOnly<TradeCost>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Hidden>());
		base.Enabled = false;
		m_SelectedResource = Resource.Grain;
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

- `public virtual OnEnabled(UnityEngine.Rendering.DebugUI+Container container) : System.Void`  

```csharp
public override void OnEnabled(DebugUI.Container container)
	{
		container.children.Add(new DebugUI.EnumField
		{
			displayName = "Resource",
			getter = () => EconomyUtils.GetResourceIndex(m_SelectedResource) + 1,
			setter = delegate(int value)
			{
				m_SelectedResource = EconomyUtils.GetResource(value - 1);
			},
			autoEnum = typeof(ResourceInEditor),
			getIndex = () => EconomyUtils.GetResourceIndex(m_SelectedResource) + 1,
			setIndex = delegate(int value)
			{
				m_SelectedResource = EconomyUtils.GetResource(value - 1);
			}
		});
	}
```

- `protected virtual OnUpdate(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
[Preserve]
	protected override JobHandle OnUpdate(JobHandle inputDeps)
	{
		if (m_StorageGroup.IsEmptyIgnoreFilter)
		{
			return inputDeps;
		}
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new TradeCostGizmoJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TradeCostType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Companies_TradeCost_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GizmoBatcher = m_GizmosSystem.GetGizmosBatcher(out dependencies),
			m_Resource = m_SelectedResource,
			m_StorageOption = m_StorageOption.enabled,
			m_CompanyOption = m_CompanyOption.enabled
		}, m_StorageGroup, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_GizmosSystem.AddGizmosBatcherWriter(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Debug.TradeCostDebugSystem+TradeCostGizmoJob`  
- `Game.Debug.TradeCostDebugSystem+TypeHandle`  

