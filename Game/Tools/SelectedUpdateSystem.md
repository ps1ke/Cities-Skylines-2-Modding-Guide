# Game.Tools.SelectedUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SelectedUpdateSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;

    public SelectedUpdateSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```


## Constructors

- `public SelectedUpdateSystem()`  

```csharp
[Preserve]
	public SelectedUpdateSystem()
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
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.selected == Entity.Null)
		{
			return;
		}
		if (!base.EntityManager.Exists(m_ToolSystem.selected))
		{
			m_ToolSystem.selected = Entity.Null;
		}
		else
		{
			if (!base.EntityManager.HasComponent<Deleted>(m_ToolSystem.selected))
			{
				return;
			}
			Entity entity = m_ToolSystem.selected;
			if (base.EntityManager.HasComponent<Icon>(entity) && base.EntityManager.TryGetComponent<Owner>(entity, out var component) && base.EntityManager.Exists(component.m_Owner))
			{
				if (!base.EntityManager.HasComponent<Deleted>(component.m_Owner))
				{
					m_ToolSystem.selected = component.m_Owner;
					return;
				}
				entity = component.m_Owner;
			}
			Pet component3;
			if (base.EntityManager.TryGetComponent<Resident>(entity, out var component2))
			{
				if (base.EntityManager.Exists(component2.m_Citizen))
				{
					m_ToolSystem.selected = component2.m_Citizen;
				}
			}
			else if (base.EntityManager.TryGetComponent<Pet>(entity, out component3) && base.EntityManager.Exists(component3.m_HouseholdPet))
			{
				m_ToolSystem.selected = component3.m_HouseholdPet;
			}
			if (base.EntityManager.HasComponent<Deleted>(m_ToolSystem.selected))
			{
				m_ToolSystem.selected = Entity.Null;
			}
		}
	}
```


