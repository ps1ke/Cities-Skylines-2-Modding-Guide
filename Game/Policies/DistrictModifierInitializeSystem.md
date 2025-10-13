# Game.Policies.DistrictModifierInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Policies`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DistrictModifierInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CreatedQuery;
    private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
    private Game.Policies.DistrictModifierInitializeSystem+TypeHandle __TypeHandle;

    public DistrictModifierInitializeSystem();

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

- `private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData`  

```csharp
private Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData m_DistrictModifierRefreshData;
```

- `private Game.Policies.DistrictModifierInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Policies.DistrictModifierInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DistrictModifierInitializeSystem()`  

```csharp
[Preserve]
	public DistrictModifierInitializeSystem()
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
		m_DistrictModifierRefreshData = new DistrictModifierRefreshData(this);
		m_CreatedQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadWrite<District>(), ComponentType.Exclude<Temp>());
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
		m_DistrictModifierRefreshData.Update(this);
		InitializeDistrictModifiersJob jobData = new InitializeDistrictModifiersJob
		{
			m_DistrictModifierRefreshData = m_DistrictModifierRefreshData,
			m_PolicyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Policies_Policy_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_DistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_District_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DistrictModifierType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_DistrictModifier_RW_BufferTypeHandle, ref base.CheckedStateRef)
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CreatedQuery, base.Dependency);
	}
```


## Nested types

- `Game.Policies.DistrictModifierInitializeSystem+InitializeDistrictModifiersJob`  
- `Game.Policies.DistrictModifierInitializeSystem+DistrictModifierRefreshData`  
- `Game.Policies.DistrictModifierInitializeSystem+TypeHandle`  

