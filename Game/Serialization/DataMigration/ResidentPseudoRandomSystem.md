# Game.Serialization.DataMigration.ResidentPseudoRandomSystem

**Assembly:** `Game`  
**Namespace:** `Game.Serialization.DataMigration`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ResidentPseudoRandomSystem : Game.GameSystemBase
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Unity.Entities.EntityQuery m_Query;
    private Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle __TypeHandle;

    public ResidentPseudoRandomSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Unity.Entities.EntityQuery m_Query`  

```csharp
private Unity.Entities.EntityQuery m_Query;
```

- `private Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ResidentPseudoRandomSystem()`  

```csharp
[Preserve]
	public ResidentPseudoRandomSystem()
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
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_Query = GetEntityQuery(ComponentType.ReadOnly<Resident>(), ComponentType.ReadWrite<PseudoRandomSeed>());
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
		if (!(m_LoadGameSystem.context.version >= Version.residentPseudoRandomFix) && !m_Query.IsEmptyIgnoreFilter)
		{
			ResidentPseudoRandomJob jobData = new ResidentPseudoRandomJob
			{
				m_ResidentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PseudoRandomSeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CitizenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef)
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_Query, base.Dependency);
		}
	}
```


## Nested types

- `Game.Serialization.DataMigration.ResidentPseudoRandomSystem+ResidentPseudoRandomJob`  
- `Game.Serialization.DataMigration.ResidentPseudoRandomSystem+TypeHandle`  

