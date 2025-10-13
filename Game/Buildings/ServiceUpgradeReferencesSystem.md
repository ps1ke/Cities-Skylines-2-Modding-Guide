# Game.Buildings.ServiceUpgradeReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceUpgradeReferencesSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpgradeQuery;
    private Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle __TypeHandle;

    public ServiceUpgradeReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpgradeQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpgradeQuery;
```

- `private Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ServiceUpgradeReferencesSystem()`  

```csharp
[Preserve]
	public ServiceUpgradeReferencesSystem()
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
		m_UpgradeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<ServiceUpgrade>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<Object>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		RequireForUpdate(m_UpgradeQuery);
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
		JobHandle dependency = JobChunkExtensions.Schedule(new UpdateUpgradeReferencesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ExtensionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Extension_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef)
		}, m_UpgradeQuery, base.Dependency);
		base.Dependency = dependency;
	}
```


## Nested types

- `Game.Buildings.ServiceUpgradeReferencesSystem+UpdateUpgradeReferencesJob`  
- `Game.Buildings.ServiceUpgradeReferencesSystem+TypeHandle`  

