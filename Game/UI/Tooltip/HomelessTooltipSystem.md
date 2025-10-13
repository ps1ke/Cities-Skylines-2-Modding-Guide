# Game.UI.Tooltip.HomelessTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HomelessTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.UI.Tooltip.IntTooltip m_HomelessCountTooltip;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Unity.Entities.EntityQuery m_ConfigQuery;

    public HomelessTooltipSystem();

    private System.Boolean IsInfomodeActivated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.UI.Tooltip.IntTooltip m_HomelessCountTooltip`  

```csharp
private Game.UI.Tooltip.IntTooltip m_HomelessCountTooltip;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```


## Constructors

- `public HomelessTooltipSystem()`  

```csharp
[Preserve]
	public HomelessTooltipSystem()
	{
	}
```


## Methods

- `private IsInfomodeActivated() : System.Boolean`  

```csharp
private bool IsInfomodeActivated()
	{
		Entity singletonEntity = m_ConfigQuery.GetSingletonEntity();
		if (m_PrefabSystem.TryGetPrefab<UIInfoviewsConfigurationPrefab>(singletonEntity, out var prefab))
		{
			Entity entity = m_PrefabSystem.GetEntity(prefab.m_HomelessInfomodePrefab);
			return base.EntityManager.HasComponent<InfomodeActive>(entity);
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ConfigQuery = GetEntityQuery(ComponentType.ReadOnly<UIInfoviewsConfigurationData>());
		m_HomelessCountTooltip = new IntTooltip
		{
			path = "HomelessCount",
			label = LocalizedString.Id("Infoviews.INFOVIEW[HomelessCount]"),
			unit = "integer"
		};
		RequireForUpdate(m_ConfigQuery);
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!IsInfomodeActivated())
		{
			return;
		}
		CompleteDependency();
		m_HomelessCountTooltip.value = 0;
		if (m_ToolRaycastSystem.GetRaycastResult(out var result) && BuildingUtils.IsHomelessShelterBuilding(base.EntityManager, result.m_Owner) && base.EntityManager.TryGetBuffer(result.m_Owner, isReadOnly: true, out DynamicBuffer<Renter> buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Renter renter = buffer[i];
				if (!base.EntityManager.HasComponent<HomelessHousehold>(renter.m_Renter) || !base.EntityManager.TryGetBuffer(renter.m_Renter, isReadOnly: true, out DynamicBuffer<HouseholdCitizen> buffer2))
				{
					continue;
				}
				for (int j = 0; j < buffer2.Length; j++)
				{
					HouseholdCitizen householdCitizen = buffer2[j];
					if (!CitizenUtils.IsDead(base.EntityManager, householdCitizen.m_Citizen))
					{
						m_HomelessCountTooltip.value++;
					}
				}
			}
		}
		if (m_HomelessCountTooltip.value > 0)
		{
			AddMouseTooltip(m_HomelessCountTooltip);
		}
	}
```


