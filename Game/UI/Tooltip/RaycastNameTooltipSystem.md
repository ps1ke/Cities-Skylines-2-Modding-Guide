# Game.UI.Tooltip.RaycastNameTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RaycastNameTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.UI.NameSystem m_NameSystem;
    private Game.UI.ImageSystem m_ImageSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.UI.Tooltip.NameTooltip m_Tooltip;

    public RaycastNameTooltipSystem();

    private System.Void AdjustTargets(Unity.Entities.Entity& instance, Unity.Entities.Entity& prefab);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.UI.ImageSystem m_ImageSystem`  

```csharp
private Game.UI.ImageSystem m_ImageSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.UI.Tooltip.NameTooltip m_Tooltip`  

```csharp
private Game.UI.Tooltip.NameTooltip m_Tooltip;
```


## Constructors

- `public RaycastNameTooltipSystem()`  

```csharp
[Preserve]
	public RaycastNameTooltipSystem()
	{
	}
```


## Methods

- `private AdjustTargets(Unity.Entities.Entity& instance, Unity.Entities.Entity& prefab) : System.Void`  

```csharp
private void AdjustTargets(ref Entity instance, ref Entity prefab)
	{
		if (base.EntityManager.TryGetComponent<Game.Creatures.Resident>(instance, out var component) && base.EntityManager.TryGetComponent<PrefabRef>(component.m_Citizen, out var component2))
		{
			instance = component.m_Citizen;
			prefab = component2.m_Prefab;
		}
		if (base.EntityManager.TryGetComponent<Controller>(instance, out var component3) && base.EntityManager.TryGetComponent<PrefabRef>(component3.m_Controller, out var component4))
		{
			instance = component3.m_Controller;
			prefab = component4.m_Prefab;
		}
		if (base.EntityManager.TryGetComponent<Game.Creatures.Pet>(instance, out var component5) && base.EntityManager.TryGetComponent<PrefabRef>(component5.m_HouseholdPet, out var component6))
		{
			instance = component5.m_HouseholdPet;
			prefab = component6.m_Prefab;
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_DefaultTool = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_NameSystem = base.World.GetOrCreateSystemManaged<NameSystem>();
		m_ImageSystem = base.World.GetOrCreateSystemManaged<ImageSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_Tooltip = new NameTooltip
		{
			path = "raycastName",
			nameBinder = m_NameSystem
		};
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.activeTool == m_DefaultTool && m_ToolRaycastSystem.GetRaycastResult(out var result) && (base.EntityManager.HasComponent<Building>(result.m_Owner) || base.EntityManager.HasComponent<Game.Routes.TransportStop>(result.m_Owner) || base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(result.m_Owner) || base.EntityManager.HasComponent<Route>(result.m_Owner) || base.EntityManager.HasComponent<Creature>(result.m_Owner) || base.EntityManager.HasComponent<Vehicle>(result.m_Owner) || base.EntityManager.HasComponent<Aggregate>(result.m_Owner) || base.EntityManager.HasComponent<Game.Objects.NetObject>(result.m_Owner)) && base.EntityManager.TryGetComponent<PrefabRef>(result.m_Owner, out var component))
		{
			Entity instance = result.m_Owner;
			Entity prefab = component.m_Prefab;
			AdjustTargets(ref instance, ref prefab);
			m_Tooltip.icon = m_ImageSystem.GetInstanceIcon(instance, prefab);
			m_Tooltip.entity = instance;
			AddMouseTooltip(m_Tooltip);
		}
	}
```


