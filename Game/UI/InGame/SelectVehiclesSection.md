# Game.UI.InGame.SelectVehiclesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SelectVehiclesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Unity.Entities.EntityQuery m_DepotQuery;
    private Unity.Entities.Entity <primaryVehicle>k__BackingField;
    private Unity.Entities.Entity <secondaryVehicle>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <primaryVehicles>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <secondaryVehicles>k__BackingField;
    private Unity.Collections.NativeArray<System.Int32> m_Results;
    private Game.UI.InGame.SelectVehiclesSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private Unity.Entities.Entity primaryVehicle { private get; private set; }
    private Unity.Entities.Entity secondaryVehicle { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> primaryVehicles { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> secondaryVehicles { private get; private set; }

    public SelectVehiclesSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Void SetVehicleModel(Unity.Entities.Entity primary, Unity.Entities.Entity secondary);
    private System.Boolean Visible();
    private System.Void WriteVehicle(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_DepotQuery`  

```csharp
private Unity.Entities.EntityQuery m_DepotQuery;
```

- `private Unity.Entities.Entity <primaryVehicle>k__BackingField`  

```csharp
private Unity.Entities.Entity <primaryVehicle>k__BackingField;
```

- `private Unity.Entities.Entity <secondaryVehicle>k__BackingField`  

```csharp
private Unity.Entities.Entity <secondaryVehicle>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <primaryVehicles>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <primaryVehicles>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <secondaryVehicles>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <secondaryVehicles>k__BackingField;
```

- `private Unity.Collections.NativeArray<System.Int32> m_Results`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_Results;
```

- `private Game.UI.InGame.SelectVehiclesSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.SelectVehiclesSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Entities.Entity primaryVehicle { private get; private set }`  

```csharp
private Unity.Entities.Entity primaryVehicle { private get; private set; }
```

- `private Unity.Entities.Entity secondaryVehicle { private get; private set }`  

```csharp
private Unity.Entities.Entity secondaryVehicle { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> primaryVehicles { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> primaryVehicles { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> secondaryVehicles { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> secondaryVehicles { private get; private set; }
```


## Constructors

- `public SelectVehiclesSection()`  

```csharp
[Preserve]
	public SelectVehiclesSection()
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
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_TransportVehicleSelectData = new TransportVehicleSelectData(this);
		m_DepotQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.TransportDepot>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_VehiclePrefabQuery = GetEntityQuery(TransportVehicleSelectData.GetEntityQueryDesc());
		primaryVehicles = new NativeList<Entity>(20, Allocator.Persistent);
		secondaryVehicles = new NativeList<Entity>(20, Allocator.Persistent);
		m_Results = new NativeArray<int>(2, Allocator.Persistent);
		AddBinding(new TriggerBinding<Entity, Entity>(group, "selectVehicles", SetVehicleModel));
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
		primaryVehicles.Dispose();
		secondaryVehicles.Dispose();
		m_Results.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		VehicleModel componentData = base.EntityManager.GetComponentData<VehicleModel>(selectedEntity);
		primaryVehicle = componentData.m_PrimaryPrefab;
		secondaryVehicle = componentData.m_SecondaryPrefab;
		base.tooltipTags.Add("TransportLine");
		base.tooltipTags.Add("CargoRoute");
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (base.visible = Visible())
		{
			TransportLineData componentData = base.EntityManager.GetComponentData<TransportLineData>(selectedPrefab);
			JobChunkExtensions.Schedule(new DepotsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_InstalledUpgradesType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportDepotDataFromEntity = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportType = componentData.m_TransportType,
				m_Results = m_Results
			}, m_DepotQuery, base.Dependency).Complete();
			bool flag2 = m_InfoUISystem.tooltipTags.Contains(TooltipTags.CargoRoute);
			m_TransportVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_VehiclePrefabQuery, Allocator.TempJob, out var jobHandle);
			JobHandle jobHandle2 = IJobExtensions.Schedule(new VehiclesListJob
			{
				m_Resources = (Resource)(flag2 ? 8 : 0),
				m_EnergyTypes = (EnergyTypes)m_Results[1],
				m_SizeClass = componentData.m_SizeClass,
				m_PublicTransportPurpose = ((!flag2) ? PublicTransportPurpose.TransportLine : ((PublicTransportPurpose)0)),
				m_TransportType = componentData.m_TransportType,
				m_PrimaryList = primaryVehicles,
				m_SecondaryList = secondaryVehicles,
				m_VehicleSelectData = m_TransportVehicleSelectData
			}, JobHandle.CombineDependencies(base.Dependency, jobHandle));
			m_TransportVehicleSelectData.PostUpdate(jobHandle2);
			jobHandle2.Complete();
			base.visible = primaryVehicles.Length > 1 || secondaryVehicles.Length > 1;
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("primaryVehicle");
		if (primaryVehicle == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			WriteVehicle(writer, primaryVehicle);
		}
		writer.PropertyName("secondaryVehicle");
		if (secondaryVehicle == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			WriteVehicle(writer, secondaryVehicle);
		}
		writer.PropertyName("primaryVehicles");
		writer.ArrayBegin(primaryVehicles.Length);
		for (int i = 0; i < primaryVehicles.Length; i++)
		{
			WriteVehicle(writer, primaryVehicles[i]);
		}
		writer.ArrayEnd();
		writer.PropertyName("secondaryVehicles");
		if (base.EntityManager.HasComponent<TrainCarriageData>(primaryVehicle) && !base.EntityManager.HasComponent<MultipleUnitTrainData>(primaryVehicle))
		{
			writer.ArrayBegin(secondaryVehicles.Length);
			for (int j = 0; j < secondaryVehicles.Length; j++)
			{
				WriteVehicle(writer, secondaryVehicles[j]);
			}
			writer.ArrayEnd();
		}
		else
		{
			writer.WriteNull();
		}
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		primaryVehicles.Clear();
		secondaryVehicles.Clear();
		for (int i = 0; i < m_Results.Length; i++)
		{
			m_Results[i] = 0;
		}
	}
```

- `private SetVehicleModel(Unity.Entities.Entity primary, Unity.Entities.Entity secondary) : System.Void`  

```csharp
private void SetVehicleModel(Entity primary, Entity secondary)
	{
		EntityCommandBuffer entityCommandBuffer = m_EndFrameBarrier.CreateCommandBuffer();
		VehicleModel componentData = base.EntityManager.GetComponentData<VehicleModel>(selectedEntity);
		componentData.m_PrimaryPrefab = primary;
		componentData.m_SecondaryPrefab = secondary;
		entityCommandBuffer.SetComponent(selectedEntity, componentData);
		m_InfoUISystem.RequestUpdate();
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<VehicleModel>(selectedEntity))
		{
			return base.EntityManager.HasComponent<TransportLineData>(selectedPrefab);
		}
		return false;
	}
```

- `private WriteVehicle(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void WriteVehicle(IJsonWriter writer, Entity entity)
	{
		writer.TypeBegin(GetType().FullName + "+VehiclePrefab");
		writer.PropertyName("entity");
		writer.Write(entity);
		writer.PropertyName("id");
		writer.Write(m_PrefabSystem.GetPrefabName(entity));
		writer.PropertyName("locked");
		writer.Write(base.EntityManager.HasEnabledComponent<Locked>(entity));
		writer.PropertyName("requirements");
		m_PrefabUISystem.BindPrefabRequirements(writer, entity);
		writer.PropertyName("thumbnail");
		writer.Write(m_ImageSystem.GetThumbnail(entity) ?? m_ImageSystem.placeholderIcon);
		writer.TypeEnd();
	}
```


## Nested types

- `Game.UI.InGame.SelectVehiclesSection+Result`  
- `Game.UI.InGame.SelectVehiclesSection+DepotsJob`  
- `Game.UI.InGame.SelectVehiclesSection+VehiclesListJob`  
- `Game.UI.InGame.SelectVehiclesSection+TypeHandle`  

