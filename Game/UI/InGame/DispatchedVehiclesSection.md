# Game.UI.InGame.DispatchedVehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DispatchedVehiclesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_VehiclesResult;
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
    private Game.UI.InGame.DispatchedVehiclesSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }
    private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }

    public DispatchedVehiclesSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ServiceDispatchQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_VehiclesResult`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_VehiclesResult;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> <vehicleList>k__BackingField;
```

- `private Game.UI.InGame.DispatchedVehiclesSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.DispatchedVehiclesSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.VehiclesSection+UIVehicle> vehicleList { private get; private set; }
```


## Constructors

- `public DispatchedVehiclesSection()`  

```csharp
[Preserve]
	public DispatchedVehiclesSection()
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
		m_ServiceDispatchQuery = GetEntityQuery(ComponentType.ReadOnly<Vehicle>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_VehiclesResult = new NativeList<Entity>(5, Allocator.Persistent);
		vehicleList = new NativeList<VehiclesSection.UIVehicle>(5, Allocator.Persistent);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		vehicleList.Dispose();
		m_VehiclesResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		for (int i = 0; i < m_VehiclesResult.Length; i++)
		{
			Entity vehicle = m_VehiclesResult[i];
			VehiclesSection.AddVehicle(base.EntityManager, vehicle, vehicleList);
		}
		vehicleList.Sort();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobChunkExtensions.Schedule(new CollectDispatchedVehiclesJob
		{
			m_SelectedEntity = selectedEntity,
			m_EntityHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ServiceDispatchHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FireRequestFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_FireRescueRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PoliceRequestFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_PoliceEmergencyRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthcareRequestFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_HealthcareRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EvacuationRequestFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_EvacuationRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageCollectionRequest = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_GarbageCollectionRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OnFireFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AccidentSiteFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_AccidentSite_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InDangerFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InDanger_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FireEngineFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_FireEngine_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AmbulanceFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Ambulance_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PoliceCarFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PoliceCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PublicTransportFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HearseFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Hearse_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MaintenanceVehicleFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_MaintenanceVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MaintenanceRequest = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_MaintenanceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehiclesResult = m_VehiclesResult
		}, m_ServiceDispatchQuery, base.Dependency).Complete();
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("vehicleList");
		writer.ArrayBegin(vehicleList.Length);
		for (int i = 0; i < vehicleList.Length; i++)
		{
			VehiclesSection.BindVehicle(m_NameSystem, writer, vehicleList[i]);
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		vehicleList.Clear();
		m_VehiclesResult.Clear();
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return m_VehiclesResult.Length > 0;
	}
```


## Nested types

- `Game.UI.InGame.DispatchedVehiclesSection+CollectDispatchedVehiclesJob`  
- `Game.UI.InGame.DispatchedVehiclesSection+TypeHandle`  

