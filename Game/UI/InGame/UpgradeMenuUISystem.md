# Game.UI.InGame.UpgradeMenuUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpgradeMenuUISystem : Game.UI.UISystemBase
{
    private Unity.Entities.EntityQuery m_UnlockedUpgradeQuery;
    private Unity.Entities.EntityQuery m_CreatedExtensionQuery;
    private Unity.Entities.EntityQuery m_DeletedExtensionQuery;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
    private Game.Tools.AreaToolSystem m_AreaToolSystem;
    private Game.Tools.NetToolSystem m_NetToolSystem;
    private Game.Tools.RouteToolSystem m_RouteToolSystem;
    private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem;
    private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
    private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradesBinding;
    private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradeDetailsBinding;
    private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedUpgradeBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_UpgradingBinding;
    private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Upgrades;
    private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Modules;
    private System.Boolean m_UniqueAssetStatusChanged;
    private static const System.String kGroup;

    public Game.GameMode gameMode { get; }
    public System.Boolean upgrading { get; }

    public UpgradeMenuUISystem();

    private System.Void BindUpgradeDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgrade);
    private System.Void BindUpgrades(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgradable);
    private System.ValueTuple<System.Boolean, System.Boolean> CheckExtensionBuiltStatus(Unity.Entities.Entity upgradableEntity, Unity.Entities.Entity upgradeEntity);
    private System.Void ClearUpgradeSelection();
    private Unity.Entities.Entity GetUpgradable(Unity.Entities.Entity entity);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    private System.Void OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position);
    protected virtual System.Void OnStartRunning();
    protected virtual System.Void OnStopRunning();
    private System.Void OnToolChanged(Game.Tools.ToolBaseSystem tool);
    private System.Void OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed);
    protected virtual System.Void OnUpdate();
    private System.Void SelectUpgrade(Unity.Entities.Entity upgradable, Unity.Entities.Entity upgrade);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UnlockedUpgradeQuery`  

```csharp
private Unity.Entities.EntityQuery m_UnlockedUpgradeQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedExtensionQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedExtensionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedExtensionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedExtensionQuery;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Tools.ObjectToolSystem m_ObjectToolSystem`  

```csharp
private Game.Tools.ObjectToolSystem m_ObjectToolSystem;
```

- `private Game.Tools.AreaToolSystem m_AreaToolSystem`  

```csharp
private Game.Tools.AreaToolSystem m_AreaToolSystem;
```

- `private Game.Tools.NetToolSystem m_NetToolSystem`  

```csharp
private Game.Tools.NetToolSystem m_NetToolSystem;
```

- `private Game.Tools.RouteToolSystem m_RouteToolSystem`  

```csharp
private Game.Tools.RouteToolSystem m_RouteToolSystem;
```

- `private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem`  

```csharp
private Game.Tools.UpgradeToolSystem m_UpgradeToolSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem`  

```csharp
private Game.UI.InGame.ToolbarUISystem m_ToolbarUISystem;
```

- `private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem`  

```csharp
private Game.UI.InGame.SelectedInfoUISystem m_SelectedInfoUISystem;
```

- `private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem`  

```csharp
private Game.UI.InGame.UniqueAssetTrackingSystem m_UniqueAssetTrackingSystem;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradesBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradesBinding;
```

- `private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradeDetailsBinding`  

```csharp
private Colossal.UI.Binding.RawMapBinding<Unity.Entities.Entity> m_UpgradeDetailsBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedUpgradeBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Unity.Entities.Entity> m_SelectedUpgradeBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_UpgradingBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_UpgradingBinding;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Upgrades`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Upgrades;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Modules`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UpgradeMenuUISystem+SortableEntity> m_Modules;
```

- `private System.Boolean m_UniqueAssetStatusChanged`  

```csharp
private System.Boolean m_UniqueAssetStatusChanged;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Properties

- `public Game.GameMode gameMode { get }`  

```csharp
public Game.GameMode gameMode { get; }
```

- `public System.Boolean upgrading { get }`  

```csharp
public System.Boolean upgrading { get; }
```


## Constructors

- `public UpgradeMenuUISystem()`  

```csharp
[Preserve]
	public UpgradeMenuUISystem()
	{
	}
```


## Methods

- `private BindUpgradeDetails(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgrade) : System.Void`  

```csharp
private void BindUpgradeDetails(IJsonWriter writer, Entity upgrade)
	{
		Entity upgradable = GetUpgradable(m_SelectedInfoUISystem.selectedEntity);
		var (unique, placed) = CheckExtensionBuiltStatus(upgradable, upgrade);
		m_PrefabUISystem.BindPrefabDetails(writer, upgrade, unique, placed);
	}
```

- `private BindUpgrades(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity upgradable) : System.Void`  

```csharp
private void BindUpgrades(IJsonWriter writer, Entity upgradable)
	{
		upgradable = GetUpgradable(upgradable);
		if (!base.EntityManager.Exists(upgradable) || !base.EntityManager.TryGetComponent<PrefabRef>(upgradable, out var component))
		{
			writer.WriteEmptyArray();
			return;
		}
		m_Upgrades.Clear();
		m_Modules.Clear();
		if (base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<BuildingUpgradeElement> buffer) && !base.EntityManager.HasComponent<Destroyed>(upgradable))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity upgrade = buffer[i].m_Upgrade;
				if (base.EntityManager.TryGetComponent<UIObjectData>(upgrade, out var component2))
				{
					ref NativeList<SortableEntity> reference = ref m_Upgrades;
					SortableEntity value = new SortableEntity
					{
						m_Entity = upgrade,
						m_Priority = component2.m_Priority
					};
					reference.Add(in value);
				}
			}
		}
		if (base.EntityManager.TryGetBuffer(component.m_Prefab, isReadOnly: true, out DynamicBuffer<BuildingModule> buffer2) && !base.EntityManager.HasComponent<Destroyed>(upgradable))
		{
			for (int j = 0; j < buffer2.Length; j++)
			{
				Entity module = buffer2[j].m_Module;
				if (base.EntityManager.TryGetComponent<UIObjectData>(module, out var component3))
				{
					ref NativeList<SortableEntity> reference2 = ref m_Modules;
					SortableEntity value = new SortableEntity
					{
						m_Entity = module,
						m_Priority = component3.m_Priority
					};
					reference2.Add(in value);
				}
			}
		}
		m_Upgrades.Sort();
		m_Modules.Sort();
		writer.ArrayBegin(m_Upgrades.Length + m_Modules.Length);
		for (int k = 0; k < m_Upgrades.Length; k++)
		{
			SortableEntity sortableEntity = m_Upgrades[k];
			var (unique, placed) = CheckExtensionBuiltStatus(upgradable, sortableEntity.m_Entity);
			m_ToolbarUISystem.BindAsset(writer, sortableEntity.m_Entity, unique, placed);
		}
		for (int l = 0; l < m_Modules.Length; l++)
		{
			SortableEntity sortableEntity2 = m_Modules[l];
			m_ToolbarUISystem.BindAsset(writer, sortableEntity2.m_Entity);
		}
		writer.ArrayEnd();
	}
```

- `private CheckExtensionBuiltStatus(Unity.Entities.Entity upgradableEntity, Unity.Entities.Entity upgradeEntity) : System.ValueTuple<System.Boolean, System.Boolean>`  

```csharp
private System.ValueTuple<System.Boolean, System.Boolean> CheckExtensionBuiltStatus(Unity.Entities.Entity upgradableEntity, Unity.Entities.Entity upgradeEntity);
```

- `private ClearUpgradeSelection() : System.Void`  

```csharp
private void ClearUpgradeSelection()
	{
		if (m_SelectedUpgradeBinding.value != Entity.Null)
		{
			m_ToolSystem.activeTool = m_DefaultTool;
			SelectUpgrade(Entity.Null, Entity.Null);
		}
	}
```

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
		m_UnlockedUpgradeQuery = GetEntityQuery(ComponentType.ReadOnly<Unlock>());
		m_CreatedExtensionQuery = GetEntityQuery(ComponentType.ReadOnly<Extension>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		m_DeletedExtensionQuery = GetEntityQuery(ComponentType.ReadOnly<Extension>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_DefaultTool = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_ToolbarUISystem = base.World.GetOrCreateSystemManaged<ToolbarUISystem>();
		m_SelectedInfoUISystem = base.World.GetOrCreateSystemManaged<SelectedInfoUISystem>();
		m_UpgradeToolSystem = base.World.GetOrCreateSystemManaged<UpgradeToolSystem>();
		m_ObjectToolSystem = base.World.GetOrCreateSystemManaged<ObjectToolSystem>();
		m_AreaToolSystem = base.World.GetOrCreateSystemManaged<AreaToolSystem>();
		m_NetToolSystem = base.World.GetOrCreateSystemManaged<NetToolSystem>();
		m_RouteToolSystem = base.World.GetOrCreateSystemManaged<RouteToolSystem>();
		m_UniqueAssetTrackingSystem = base.World.GetOrCreateSystemManaged<UniqueAssetTrackingSystem>();
		UniqueAssetTrackingSystem uniqueAssetTrackingSystem = m_UniqueAssetTrackingSystem;
		uniqueAssetTrackingSystem.EventUniqueAssetStatusChanged = (Action<Entity, bool>)Delegate.Combine(uniqueAssetTrackingSystem.EventUniqueAssetStatusChanged, new Action<Entity, bool>(OnUniqueAssetStatusChanged));
		AddBinding(m_UpgradesBinding = new RawMapBinding<Entity>("upgradeMenu", "upgrades", BindUpgrades));
		AddBinding(m_SelectedUpgradeBinding = new ValueBinding<Entity>("upgradeMenu", "selectedUpgrade", Entity.Null));
		AddBinding(m_UpgradeDetailsBinding = new RawMapBinding<Entity>("upgradeMenu", "upgradeDetails", BindUpgradeDetails));
		AddBinding(new TriggerBinding<Entity, Entity>("upgradeMenu", "selectUpgrade", SelectUpgrade));
		AddBinding(new TriggerBinding("upgradeMenu", "clearUpgradeSelection", ClearUpgradeSelection));
		AddBinding(m_UpgradingBinding = new ValueBinding<bool>("upgradeMenu", "upgrading", initialValue: false));
		m_Upgrades = new NativeList<SortableEntity>(9, Allocator.Persistent);
		m_Modules = new NativeList<SortableEntity>(9, Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_Upgrades.Dispose();
		m_Modules.Dispose();
		base.OnDestroy();
	}
```

- `private OnSelectionChanged(Unity.Entities.Entity entity, Unity.Entities.Entity prefab, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private void OnSelectionChanged(Entity entity, Entity prefab, float3 position)
	{
		if (InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse)
		{
			ClearUpgradeSelection();
		}
	}
```

- `protected virtual OnStartRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStartRunning()
	{
		base.OnStartRunning();
		SelectedInfoUISystem selectedInfoUISystem = m_SelectedInfoUISystem;
		selectedInfoUISystem.eventSelectionChanged = (Action<Entity, Entity, float3>)Delegate.Combine(selectedInfoUISystem.eventSelectionChanged, new Action<Entity, Entity, float3>(OnSelectionChanged));
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Combine(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		SelectedInfoUISystem selectedInfoUISystem = m_SelectedInfoUISystem;
		selectedInfoUISystem.eventSelectionChanged = (Action<Entity, Entity, float3>)Delegate.Remove(selectedInfoUISystem.eventSelectionChanged, new Action<Entity, Entity, float3>(OnSelectionChanged));
		ToolSystem toolSystem = m_ToolSystem;
		toolSystem.EventToolChanged = (Action<ToolBaseSystem>)Delegate.Remove(toolSystem.EventToolChanged, new Action<ToolBaseSystem>(OnToolChanged));
		base.OnStopRunning();
	}
```

- `private OnToolChanged(Game.Tools.ToolBaseSystem tool) : System.Void`  

```csharp
private void OnToolChanged(ToolBaseSystem tool)
	{
		if (tool == m_DefaultTool && InputManager.instance.activeControlScheme == InputManager.ControlScheme.KeyboardAndMouse)
		{
			ClearUpgradeSelection();
		}
		bool flag = tool == m_ObjectToolSystem && m_ObjectToolSystem.mode == ObjectToolSystem.Mode.Upgrade;
		bool flag2 = tool == m_NetToolSystem && m_NetToolSystem.serviceUpgrade;
		bool flag3 = tool == m_RouteToolSystem && m_RouteToolSystem.serviceUpgrade;
		Owner component;
		bool flag4 = m_ToolSystem.activeTool == m_AreaToolSystem && base.EntityManager.TryGetComponent<Owner>(m_AreaToolSystem.recreate, out component) && base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(component.m_Owner);
		PrefabBase prefab = tool.GetPrefab();
		Entity entity = (((object)prefab != null) ? m_PrefabSystem.GetEntity(prefab) : Entity.Null);
		m_UpgradingBinding.Update(base.EntityManager.HasComponent<BuildingModuleData>(entity) || flag || flag2 || flag3 || flag4 || tool == m_UpgradeToolSystem);
	}
```

- `private OnUniqueAssetStatusChanged(Unity.Entities.Entity prefabEntity, System.Boolean placed) : System.Void`  

```csharp
private void OnUniqueAssetStatusChanged(Entity prefabEntity, bool placed)
	{
		m_UniqueAssetStatusChanged = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		Entity upgradable = GetUpgradable(m_SelectedInfoUISystem.selectedEntity);
		if (PrefabUtils.HasUnlockedPrefabAll<BuildingUpgradeElement, UIObjectData>(base.EntityManager, m_UnlockedUpgradeQuery) || PrefabUtils.HasUnlockedPrefabAll<BuildingModuleData, UIObjectData>(base.EntityManager, m_UnlockedUpgradeQuery) || !m_CreatedExtensionQuery.IsEmptyIgnoreFilter || !m_DeletedExtensionQuery.IsEmptyIgnoreFilter || m_UniqueAssetStatusChanged || (base.EntityManager.HasComponent<Updated>(upgradable) && base.EntityManager.HasComponent<Destroyed>(upgradable) != (m_Upgrades.Length == 0)))
		{
			m_UpgradesBinding.UpdateAll();
			m_UpgradeDetailsBinding.UpdateAll();
		}
		m_UniqueAssetStatusChanged = false;
	}
```

- `private SelectUpgrade(Unity.Entities.Entity upgradable, Unity.Entities.Entity upgrade) : System.Void`  

```csharp
private void SelectUpgrade(Entity upgradable, Entity upgrade)
	{
		upgradable = GetUpgradable(upgradable);
		m_SelectedUpgradeBinding.Update(upgrade);
		bool item = CheckExtensionBuiltStatus(upgradable, upgrade).built;
		if (upgradable != Entity.Null && upgrade != Entity.Null && !base.EntityManager.HasEnabledComponent<Locked>(upgrade) && !item)
		{
			PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(upgrade);
			m_UpgradingBinding.Update(newValue: true);
			m_UpgradesBinding.UpdateAll();
			m_ToolSystem.ActivatePrefabTool(prefab);
			return;
		}
		PrefabBase prefab2 = m_ToolSystem.activeTool.GetPrefab();
		if (prefab2 == null)
		{
			m_ToolSystem.activeTool = m_DefaultTool;
			return;
		}
		Entity entity = m_PrefabSystem.GetEntity(prefab2);
		if (!(m_SelectedUpgradeBinding.value != Entity.Null) || !base.EntityManager.TryGetBuffer(entity, isReadOnly: true, out DynamicBuffer<BuildingUpgradeElement> buffer))
		{
			return;
		}
		for (int i = 0; i < buffer.Length; i++)
		{
			if (!(m_SelectedUpgradeBinding.value != buffer[i].m_Upgrade))
			{
				m_ToolSystem.activeTool = m_DefaultTool;
				break;
			}
		}
	}
```


## Nested types

- `Game.UI.InGame.UpgradeMenuUISystem+SortableEntity`  

