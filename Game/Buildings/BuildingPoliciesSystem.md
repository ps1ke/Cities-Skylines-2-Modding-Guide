# Game.Buildings.BuildingPoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BuildingPoliciesSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_PolicyModifyQuery;
    private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
    private Game.Buildings.BuildingPoliciesSystem+TypeHandle __TypeHandle;

    public BuildingPoliciesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_PolicyModifyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyModifyQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingSettingsQuery;
```

- `private Game.Buildings.BuildingPoliciesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.BuildingPoliciesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public BuildingPoliciesSystem()`  

```csharp
[Preserve]
	public BuildingPoliciesSystem()
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
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_PolicyModifyQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Modify>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<ServiceUpgrade>(),
				ComponentType.ReadOnly<Building>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_BuildingSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		RequireForUpdate(m_PolicyModifyQuery);
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
		JobHandle jobHandle = JobChunkExtensions.Schedule(new CheckBuildingsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ModifyType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Policies_Modify_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_DestroyedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OnFireType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Extension_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingOptionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingOptionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RW_BufferLookup, ref base.CheckedStateRef),
			m_BuildingConfigurationData = m_BuildingSettingsQuery.GetSingleton<BuildingConfigurationData>(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		}, m_PolicyModifyQuery, base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Buildings.BuildingPoliciesSystem+CheckBuildingsJob`  
- `Game.Buildings.BuildingPoliciesSystem+TypeHandle`  

