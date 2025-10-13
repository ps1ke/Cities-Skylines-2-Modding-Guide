# Game.UI.InGame.VehicleCountSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class VehicleCountSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Unity.Entities.Entity m_VehicleCountPolicy;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Collections.NativeArray<System.Int32> m_IntResults;
    private Unity.Collections.NativeReference<System.Single> m_DurationResult;
    private System.Int32 <vehicleCountMin>k__BackingField;
    private System.Int32 <vehicleCountMax>k__BackingField;
    private System.Int32 <vehicleCount>k__BackingField;
    private System.Int32 <activeVehicles>k__BackingField;
    private System.Single <stableDuration>k__BackingField;
    private Game.UI.InGame.VehicleCountSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Int32 vehicleCountMin { private get; private set; }
    private System.Int32 vehicleCountMax { private get; private set; }
    private System.Int32 vehicleCount { private get; private set; }
    private System.Int32 activeVehicles { private get; private set; }
    private System.Single stableDuration { private get; private set; }

    public VehicleCountSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnSetVehicleCount(System.Single newVehicleCount);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Unity.Entities.Entity m_VehicleCountPolicy`  

```csharp
private Unity.Entities.Entity m_VehicleCountPolicy;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Collections.NativeArray<System.Int32> m_IntResults`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_IntResults;
```

- `private Unity.Collections.NativeReference<System.Single> m_DurationResult`  

```csharp
private Unity.Collections.NativeReference<System.Single> m_DurationResult;
```

- `private System.Int32 <vehicleCountMin>k__BackingField`  

```csharp
private System.Int32 <vehicleCountMin>k__BackingField;
```

- `private System.Int32 <vehicleCountMax>k__BackingField`  

```csharp
private System.Int32 <vehicleCountMax>k__BackingField;
```

- `private System.Int32 <vehicleCount>k__BackingField`  

```csharp
private System.Int32 <vehicleCount>k__BackingField;
```

- `private System.Int32 <activeVehicles>k__BackingField`  

```csharp
private System.Int32 <activeVehicles>k__BackingField;
```

- `private System.Single <stableDuration>k__BackingField`  

```csharp
private System.Single <stableDuration>k__BackingField;
```

- `private Game.UI.InGame.VehicleCountSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.VehicleCountSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 vehicleCountMin { private get; private set }`  

```csharp
private System.Int32 vehicleCountMin { private get; private set; }
```

- `private System.Int32 vehicleCountMax { private get; private set }`  

```csharp
private System.Int32 vehicleCountMax { private get; private set; }
```

- `private System.Int32 vehicleCount { private get; private set }`  

```csharp
private System.Int32 vehicleCount { private get; private set; }
```

- `private System.Int32 activeVehicles { private get; private set }`  

```csharp
private System.Int32 activeVehicles { private get; private set; }
```

- `private System.Single stableDuration { private get; private set }`  

```csharp
private System.Single stableDuration { private get; private set; }
```


## Constructors

- `public VehicleCountSection()`  

```csharp
[Preserve]
	public VehicleCountSection()
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
		m_PoliciesUISystem = base.World.GetOrCreateSystemManaged<PoliciesUISystem>();
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UITransportConfigurationData>());
		AddBinding(new TriggerBinding<float>(group, "setVehicleCount", OnSetVehicleCount));
		m_IntResults = new NativeArray<int>(4, Allocator.Persistent);
		m_DurationResult = new NativeReference<float>(0f, Allocator.Persistent);
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
		m_IntResults.Dispose();
		m_DurationResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		if (!m_ConfigQuery.IsEmptyIgnoreFilter)
		{
			UITransportConfigurationPrefab singletonPrefab = m_PrefabSystem.GetSingletonPrefab<UITransportConfigurationPrefab>(m_ConfigQuery);
			m_VehicleCountPolicy = m_PrefabSystem.GetEntity(singletonPrefab.m_VehicleCountPolicy);
		}
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		vehicleCountMin = m_IntResults[2];
		vehicleCountMax = m_IntResults[3];
		vehicleCount = m_IntResults[0];
		activeVehicles = m_IntResults[1];
		stableDuration = m_DurationResult.Value;
		base.tooltipTags.Add("TransportLine");
		base.tooltipTags.Add("CargoRoute");
	}
```

- `private OnSetVehicleCount(System.Single newVehicleCount) : System.Void`  

```csharp
private void OnSetVehicleCount(float newVehicleCount)
	{
		DynamicBuffer<RouteModifierData> buffer = base.EntityManager.GetBuffer<RouteModifierData>(m_VehicleCountPolicy, isReadOnly: true);
		PolicySliderData componentData = base.EntityManager.GetComponentData<PolicySliderData>(m_VehicleCountPolicy);
		float adjustment = CalculateVehicleCountJob.CalculateAdjustmentFromVehicleCount((int)newVehicleCount, base.EntityManager.GetComponentData<TransportLineData>(selectedPrefab).m_DefaultVehicleInterval, stableDuration, buffer, componentData);
		m_PoliciesUISystem.SetPolicy(selectedEntity, m_VehicleCountPolicy, active: true, adjustment);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
		if (base.visible)
		{
			IJobExtensions.Schedule(new CalculateVehicleCountJob
			{
				m_SelectedEntity = selectedEntity,
				m_SelectedPrefab = selectedPrefab,
				m_Policy = m_VehicleCountPolicy,
				m_TransportLineDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PolicySliderDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PolicySliderData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_VehicleTimings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_VehicleTiming_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathInformations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RouteVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteVehicle_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteSegments = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_RouteModifierDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_RouteModifierData_RO_BufferLookup, ref base.CheckedStateRef),
				m_IntResults = m_IntResults,
				m_Duration = m_DurationResult
			}, base.Dependency).Complete();
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("vehicleCountMin");
		writer.Write(vehicleCountMin);
		writer.PropertyName("vehicleCountMax");
		writer.Write(vehicleCountMax);
		writer.PropertyName("vehicleCount");
		writer.Write(vehicleCount);
		writer.PropertyName("activeVehicles");
		writer.Write(activeVehicles);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		vehicleCountMin = 0;
		vehicleCountMax = 0;
		vehicleCount = 0;
		activeVehicles = 0;
		stableDuration = 0f;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Route>(selectedEntity) && base.EntityManager.HasComponent<TransportLine>(selectedEntity) && base.EntityManager.HasComponent<RouteWaypoint>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Policy>(selectedEntity);
		}
		return false;
	}
```


## Nested types

- `Game.UI.InGame.VehicleCountSection+Result`  
- `Game.UI.InGame.VehicleCountSection+CalculateVehicleCountJob`  
- `Game.UI.InGame.VehicleCountSection+TypeHandle`  

