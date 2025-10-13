# Game.UI.InGame.UpgradesSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpgradesSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Collections.NativeList<Unity.Entities.Entity> <extensions>k__BackingField;
    private Unity.Collections.NativeList<Unity.Entities.Entity> <subBuildings>k__BackingField;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
    private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
    private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
    private Game.Audio.AudioManager m_AudioManager;
    private Unity.Entities.EntityQuery m_SoundQuery;

    protected System.String group { protected get; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> extensions { private get; private set; }
    private Unity.Collections.NativeList<Unity.Entities.Entity> subBuildings { private get; private set; }

    public UpgradesSection();

    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    private System.Void OnDelete(Unity.Entities.Entity entity);
    protected virtual System.Void OnDestroy();
    private System.Void OnFocus(Unity.Entities.Entity entity);
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnProcess();
    private System.Void OnRelocate(Unity.Entities.Entity entity);
    private System.Void OnToggle(Unity.Entities.Entity entity);
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <extensions>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <extensions>k__BackingField;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> <subBuildings>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> <subBuildings>k__BackingField;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem`  

```csharp
private Game.Prefabs.UIInitializeSystem m_UIInitializeSystem;
```

- `private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem`  

```csharp
private Game.UI.InGame.PoliciesUISystem m_PoliciesUISystem;
```

- `private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy`  

```csharp
private Game.Prefabs.PolicyPrefab m_BuildingOutOfServicePolicy;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> extensions { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> extensions { private get; private set; }
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> subBuildings { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> subBuildings { private get; private set; }
```


## Constructors

- `public UpgradesSection()`  

```csharp
[Preserve]
	public UpgradesSection()
	{
	}
```


## Methods

- `private GetUpgradable(Unity.Entities.Entity entity) : Unity.Entities.Entity`  

```csharp
private Entity GetUpgradable(Entity entity)
	{
		if (base.EntityManager.TryGetComponent<Attached>(entity, out var component))
		{
			return component.m_Parent;
		}
		return entity;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetExistingSystemManaged<ToolSystem>();
		m_ObjectToolSystem = base.World.GetExistingSystemManaged<ObjectToolSystem>();
		m_UIInitializeSystem = base.World.GetOrCreateSystemManaged<UIInitializeSystem>();
		m_PoliciesUISystem = base.World.GetOrCreateSystemManaged<PoliciesUISystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		extensions = new NativeList<Entity>(5, Allocator.Persistent);
		subBuildings = new NativeList<Entity>(10, Allocator.Persistent);
		AddBinding(new TriggerBinding<Entity>(group, "delete", OnDelete));
		AddBinding(new TriggerBinding<Entity>(group, "relocate", OnRelocate));
		AddBinding(new TriggerBinding<Entity>(group, "focus", OnFocus));
		AddBinding(new TriggerBinding<Entity>(group, "toggle", OnToggle));
	}
```

- `private OnDelete(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnDelete(Entity entity)
	{
		if (base.EntityManager.Exists(entity))
		{
			m_AudioManager.PlayUISound(m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_BulldozeSound);
			m_EndFrameBarrier.CreateCommandBuffer().AddComponent<Deleted>(entity);
		}
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		extensions.Dispose();
		subBuildings.Dispose();
	}
```

- `private OnFocus(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnFocus(Entity entity)
	{
		bool flag = SelectedInfoUISystem.s_CameraController != null && SelectedInfoUISystem.s_CameraController.controllerEnabled && SelectedInfoUISystem.s_CameraController.followedEntity == entity;
		m_InfoUISystem.Focus((!flag) ? entity : Entity.Null);
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		foreach (PolicyPrefab policy in m_UIInitializeSystem.policies)
		{
			if (policy.name == "Out of Service")
			{
				m_BuildingOutOfServicePolicy = policy;
			}
		}
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (!base.EntityManager.TryGetBuffer(GetUpgradable(selectedEntity), isReadOnly: true, out DynamicBuffer<InstalledUpgrade> buffer))
		{
			return;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			Entity value = buffer[i].m_Upgrade;
			if (base.EntityManager.HasComponent<UIObjectData>(base.EntityManager.GetComponentData<PrefabRef>(value).m_Prefab))
			{
				if (base.EntityManager.HasComponent<Extension>(value))
				{
					extensions.Add(in value);
				}
				else
				{
					subBuildings.Add(in value);
				}
			}
		}
	}
```

- `private OnRelocate(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnRelocate(Entity entity)
	{
		m_ObjectToolSystem.StartMoving(entity);
		m_ToolSystem.activeTool = m_ObjectToolSystem;
	}
```

- `private OnToggle(Unity.Entities.Entity entity) : System.Void`  

```csharp
private void OnToggle(Entity entity)
	{
		Building component;
		Extension component2;
		bool flag = (base.EntityManager.TryGetComponent<Building>(entity, out component) && BuildingUtils.CheckOption(component, BuildingOption.Inactive)) || (base.EntityManager.TryGetComponent<Extension>(entity, out component2) && (component2.m_Flags & ExtensionFlags.Disabled) != 0);
		m_PoliciesUISystem.SetSelectedInfoPolicy(entity, m_PrefabSystem.GetEntity(m_BuildingOutOfServicePolicy), !flag);
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
		writer.PropertyName("extensions");
		writer.ArrayBegin(extensions.Length);
		for (int i = 0; i < extensions.Length; i++)
		{
			Entity entity = extensions[i];
			writer.TypeBegin(group + ".Upgrade");
			writer.PropertyName("name");
			m_NameSystem.BindName(writer, entity);
			writer.PropertyName("entity");
			writer.Write(entity);
			Extension component;
			bool value = base.EntityManager.TryGetComponent<Extension>(entity, out component) && (component.m_Flags & ExtensionFlags.Disabled) != 0;
			writer.PropertyName("disabled");
			writer.Write(value);
			bool value2 = SelectedInfoUISystem.s_CameraController != null && SelectedInfoUISystem.s_CameraController.controllerEnabled && SelectedInfoUISystem.s_CameraController.followedEntity == entity;
			writer.PropertyName("focused");
			writer.Write(value2);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
		writer.PropertyName("subBuildings");
		writer.ArrayBegin(subBuildings.Length);
		for (int j = 0; j < subBuildings.Length; j++)
		{
			Entity entity2 = subBuildings[j];
			writer.TypeBegin(group + ".Upgrade");
			writer.PropertyName("name");
			m_NameSystem.BindName(writer, entity2);
			writer.PropertyName("entity");
			writer.Write(entity2);
			Building component2;
			bool value3 = base.EntityManager.TryGetComponent<Building>(entity2, out component2) && BuildingUtils.CheckOption(component2, BuildingOption.Inactive);
			writer.PropertyName("disabled");
			writer.Write(value3);
			bool value4 = SelectedInfoUISystem.s_CameraController != null && SelectedInfoUISystem.s_CameraController.controllerEnabled && SelectedInfoUISystem.s_CameraController.followedEntity == entity2;
			writer.PropertyName("focused");
			writer.Write(value4);
			writer.TypeEnd();
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		extensions.Clear();
		subBuildings.Clear();
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		bool result = false;
		if (base.EntityManager.TryGetComponent<PrefabRef>(GetUpgradable(selectedEntity), out var component) && base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<BuildingUpgradeElement> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity upgrade = buffer[i].m_Upgrade;
				if (base.EntityManager.HasComponent<UIObjectData>(upgrade))
				{
					result = true;
					break;
				}
			}
		}
		return result;
	}
```


