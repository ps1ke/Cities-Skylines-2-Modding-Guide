# Game.UI.InGame.DestroyedBuildingSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DestroyedBuildingSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
    private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Rebuilding;
    private Unity.Entities.EntityQuery m_FireStationQuery;
    private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
    private Unity.Entities.Entity <destroyer>k__BackingField;
    private System.Boolean <cleared>k__BackingField;
    private System.Single <progress>k__BackingField;
    private Game.UI.InGame.DestroyedBuildingSection+Status <status>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity destroyer { private get; private set; }
    private System.Boolean cleared { private get; private set; }
    private System.Single progress { private get; private set; }
    private Game.UI.InGame.DestroyedBuildingSection+Status status { private get; private set; }
    protected System.Boolean displayForDestroyedObjects { protected get; }
    protected System.Boolean displayForUpgrades { protected get; }

    public DestroyedBuildingSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    private System.Void OnToggleRebuild();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean VehicleAtTarget(Unity.Entities.Entity vehicle);
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultToolSystem`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultToolSystem;
```

- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  

```csharp
private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Rebuilding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_Rebuilding;
```

- `private Unity.Entities.EntityQuery m_FireStationQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireStationQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceDispatchQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceDispatchQuery;
```

- `private Unity.Entities.Entity <destroyer>k__BackingField`  

```csharp
private Unity.Entities.Entity <destroyer>k__BackingField;
```

- `private System.Boolean <cleared>k__BackingField`  

```csharp
private System.Boolean <cleared>k__BackingField;
```

- `private System.Single <progress>k__BackingField`  

```csharp
private System.Single <progress>k__BackingField;
```

- `private Game.UI.InGame.DestroyedBuildingSection+Status <status>k__BackingField`  

```csharp
private Game.UI.InGame.DestroyedBuildingSection+Status <status>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Entities.Entity destroyer { private get; private set }`  

```csharp
private Unity.Entities.Entity destroyer { private get; private set; }
```

- `private System.Boolean cleared { private get; private set }`  

```csharp
private System.Boolean cleared { private get; private set; }
```

- `private System.Single progress { private get; private set }`  

```csharp
private System.Single progress { private get; private set; }
```

- `private Game.UI.InGame.DestroyedBuildingSection+Status status { private get; private set }`  

```csharp
private Game.UI.InGame.DestroyedBuildingSection+Status status { private get; private set; }
```

- `protected System.Boolean displayForDestroyedObjects { protected get }`  

```csharp
protected System.Boolean displayForDestroyedObjects { protected get; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```


## Constructors

- `public DestroyedBuildingSection()`  

```csharp
[Preserve]
	public DestroyedBuildingSection()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_DefaultToolSystem = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_UpgradeToolSystem = base.World.GetOrCreateSystemManaged<UpgradeToolSystem>();
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Combine(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
		m_FireStationQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<Game.Buildings.FireStation>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ServiceDispatchQuery = GetEntityQuery(ComponentType.ReadOnly<Vehicle>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		AddBinding(new TriggerBinding(group, "toggleRebuild", OnToggleRebuild));
		AddBinding(m_Rebuilding = new ValueBinding<bool>(group, "rebuilding", initialValue: false));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Remove(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Destroyed componentData = base.EntityManager.GetComponentData<Destroyed>(selectedEntity);
		base.EntityManager.TryGetComponent<PrefabRef>(componentData.m_Event, out var component);
		destroyer = component.m_Prefab;
		progress = math.max(0f, componentData.m_Cleared);
		cleared = progress >= 1f;
		if (!cleared)
		{
			NativeArray<PrefabRef> nativeArray = m_FireStationQuery.ToComponentDataArray<PrefabRef>(Allocator.TempJob);
			NativeArray<Entity> nativeArray2 = m_ServiceDispatchQuery.ToEntityArray(Allocator.TempJob);
			bool flag = false;
			for (int i = 0; i < nativeArray.Length; i++)
			{
				if (base.EntityManager.TryGetComponent<FireStationData>(nativeArray[i].m_Prefab, out var component2) && component2.m_DisasterResponseCapacity > 0)
				{
					flag = true;
					break;
				}
			}
			if (!flag)
			{
				status = Status.NoService;
			}
			else
			{
				for (int j = 0; j < nativeArray2.Length; j++)
				{
					DynamicBuffer<ServiceDispatch> buffer = base.EntityManager.GetBuffer<ServiceDispatch>(nativeArray2[j], isReadOnly: true);
					for (int k = 0; k < buffer.Length; k++)
					{
						if (base.EntityManager.TryGetComponent<FireRescueRequest>(buffer[k].m_Request, out var component3) && component3.m_Type == FireRescueRequestType.Disaster && component3.m_Target == selectedEntity && VehicleAtTarget(nativeArray2[j]))
						{
							status = Status.Searching;
							break;
						}
					}
				}
			}
			if (status == Status.None)
			{
				status = Status.Waiting;
			}
			nativeArray.Dispose();
			nativeArray2.Dispose();
		}
		else
		{
			status = Status.Rebuild;
		}
		if (status != Status.None)
		{
			base.tooltipKeys.Add(status.ToString());
		}
		m_InfoUISystem.tooltipTags.Add(TooltipTags.Destroyed);
	}
```

- `private OnToggleRebuild() : System.Void`  

```csharp
private void OnToggleRebuild()
	{
		if (m_ToolSystem.activeTool == m_UpgradeToolSystem)
		{
			m_ToolSystem.activeTool = m_DefaultToolSystem;
			return;
		}
		m_UpgradeToolSystem.prefab = null;
		m_ToolSystem.activeTool = m_UpgradeToolSystem;
	}
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private void OnToolChanged(ToolBaseSystem tool)
	{
		m_Rebuilding.Update(tool == m_UpgradeToolSystem);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		base.visible = Visible();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("destroyer");
		if (destroyer != Entity.Null)
		{
			PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(destroyer);
			writer.Write(prefab.name);
		}
		else
		{
			writer.WriteNull();
		}
		writer.PropertyName("progress");
		writer.Write(progress * 100f);
		writer.PropertyName("cleared");
		writer.Write(cleared);
		writer.PropertyName("status");
		writer.Write(status.ToString());
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		destroyer = Entity.Null;
		status = Status.None;
		cleared = false;
		progress = 0f;
	}
```

- `private VehicleAtTarget(Unity.Entities.Entity vehicle) : System.Boolean`  

```csharp
private bool VehicleAtTarget(Entity vehicle)
	{
		if (base.EntityManager.TryGetComponent<Game.Vehicles.FireEngine>(vehicle, out var component))
		{
			return (component.m_State & FireEngineFlags.Rescueing) != 0;
		}
		return false;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.Destroyed && base.EntityManager.HasComponent<Building>(selectedEntity) && (!base.EntityManager.HasComponent<Owner>(selectedEntity) || base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(selectedEntity)))
		{
			if (base.EntityManager.HasComponent<SpawnableBuildingData>(selectedPrefab) && !base.EntityManager.HasComponent<PlacedSignatureBuildingData>(selectedPrefab))
			{
				return base.EntityManager.HasComponent<Attached>(selectedEntity);
			}
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.UI.InGame.DestroyedBuildingSection+Status`  

