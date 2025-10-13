# Game.Policies.BuildingModifierInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingModifierInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
    private Game.Policies.BuildingModifierInitializeSystem+TypeHandle __TypeHandle;

    public BuildingModifierInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedQuery;
```

- `private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData`  

```csharp
private Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData m_BuildingModifierRefreshData;
```

- `private Game.Policies.BuildingModifierInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.BuildingModifierInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BuildingModifierInitializeSystem()`  

```csharp
[Preserve]
	public BuildingModifierInitializeSystem()
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
		m_BuildingModifierRefreshData = new BuildingModifierRefreshData(this);
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadWrite<Building>(), ComponentType.Exclude<Temp>());
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
		m_BuildingModifierRefreshData.Update(this);
		InitializeBuildingModifiersJob jobData = new InitializeBuildingModifiersJob
		{
			m_BuildingModifierRefreshData = m_BuildingModifierRefreshData,
			m_PolicyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Policies_Policy_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingModifierType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_BuildingModifier_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedQuery, base.Dependency);
	}
```


## Nested types

- `Game.Policies.BuildingModifierInitializeSystem+InitializeBuildingModifiersJob`  
- `Game.Policies.BuildingModifierInitializeSystem+BuildingModifierRefreshData`  
- `Game.Policies.BuildingModifierInitializeSystem+TypeHandle`  

