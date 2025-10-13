# Game.UI.InGame.UpkeepSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class UpkeepSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
    private Unity.Entities.EntityQuery m_BudgetDataQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <moneyUpkeep>k__BackingField;
    private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <resourceUpkeep>k__BackingField;
    private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> <upkeeps>k__BackingField;
    private System.Int32 <total>k__BackingField;
    private System.Boolean <inactive>k__BackingField;
    private Game.UI.InGame.UpkeepSection+TypeHandle __TypeHandle;

    protected System.String group { protected get; }
    private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> moneyUpkeep { private get; private set; }
    private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> resourceUpkeep { private get; private set; }
    private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> upkeeps { private get; private set; }
    private System.Int32 total { private get; private set; }
    private System.Boolean inactive { private get; private set; }
    protected System.Boolean displayForUpgrades { protected get; }

    public UpkeepSection();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void CalculateServiceUpkeepDatas(Unity.Entities.Entity entity, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity buildingOwnerEntity, Unity.Entities.DynamicBuffer<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, System.Boolean inactiveBuilding, System.Boolean inactiveUpgrade);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  

```csharp
private Game.UI.InGame.PrefabUISystem m_PrefabUISystem;
```

- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_BudgetDataQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <moneyUpkeep>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <moneyUpkeep>k__BackingField;
```

- `private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <resourceUpkeep>k__BackingField`  

```csharp
private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> <resourceUpkeep>k__BackingField;
```

- `private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> <upkeeps>k__BackingField`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> <upkeeps>k__BackingField;
```

- `private System.Int32 <total>k__BackingField`  

```csharp
private System.Int32 <total>k__BackingField;
```

- `private System.Boolean <inactive>k__BackingField`  

```csharp
private System.Boolean <inactive>k__BackingField;
```

- `private Game.UI.InGame.UpkeepSection+TypeHandle __TypeHandle`  

```csharp
private Game.UI.InGame.UpkeepSection+TypeHandle __TypeHandle;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> moneyUpkeep { private get; private set }`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.UI.InGame.UpkeepSection+UIUpkeepItem> moneyUpkeep { private get; private set; }
```

- `private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> resourceUpkeep { private get; private set }`  

```csharp
private System.Collections.Generic.Dictionary<Game.Economy.Resource, Game.UI.InGame.UpkeepSection+UIUpkeepItem> resourceUpkeep { private get; private set; }
```

- `private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> upkeeps { private get; private set }`  

```csharp
private System.Collections.Generic.List<Game.UI.InGame.UpkeepSection+UIUpkeepItem> upkeeps { private get; private set; }
```

- `private System.Int32 total { private get; private set }`  

```csharp
private System.Int32 total { private get; private set; }
```

- `private System.Boolean inactive { private get; private set }`  

```csharp
private System.Boolean inactive { private get; private set; }
```

- `protected System.Boolean displayForUpgrades { protected get }`  

```csharp
protected System.Boolean displayForUpgrades { protected get; }
```


## Constructors

- `public UpkeepSection()`  

```csharp
[Preserve]
	public UpkeepSection()
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

- `private CalculateServiceUpkeepDatas(Unity.Entities.Entity entity, Unity.Entities.Entity prefabEntity, Unity.Entities.Entity buildingOwnerEntity, Unity.Entities.DynamicBuffer<Game.Prefabs.ServiceUpkeepData> serviceUpkeepDatas, System.Boolean inactiveBuilding, System.Boolean inactiveUpgrade) : System.Void`  

```csharp
private void CalculateServiceUpkeepDatas(Entity entity, Entity prefabEntity, Entity buildingOwnerEntity, DynamicBuffer<ServiceUpkeepData> serviceUpkeepDatas, bool inactiveBuilding, bool inactiveUpgrade)
	{
		string prefabName = m_PrefabSystem.GetPrefabName(prefabEntity);
		for (int i = 0; i < serviceUpkeepDatas.Length; i++)
		{
			ServiceUpkeepData serviceUpkeepData = serviceUpkeepDatas[i];
			Resource resource = serviceUpkeepData.m_Upkeep.m_Resource;
			int num = serviceUpkeepData.m_Upkeep.m_Amount;
			m_PrefabUISystem.GetTitleAndDescription(prefabEntity, out var titleId, out var descriptionId);
			if (!m_BudgetDataQuery.IsEmptyIgnoreFilter && resource == Resource.Money)
			{
				int num2 = CityServiceUpkeepSystem.CalculateUpkeep(num, selectedPrefab, m_BudgetDataQuery.GetSingletonEntity(), base.EntityManager);
				if (inactiveBuilding || inactiveUpgrade)
				{
					num2 = (int)((float)num2 * 0.1f);
				}
				if (!moneyUpkeep.TryGetValue(prefabName, out var value))
				{
					moneyUpkeep[prefabName] = value;
				}
				Dictionary<string, UIUpkeepItem> dictionary = moneyUpkeep;
				descriptionId = prefabName;
				dictionary[descriptionId] += new UIUpkeepItem(num, num2, Resource.Money, titleId);
			}
			else
			{
				if (inactiveUpgrade)
				{
					continue;
				}
				int num3 = Mathf.RoundToInt((float)num * EconomyUtils.GetMarketPrice(resource, m_ResourceSystem.GetPrefabs(), base.EntityManager));
				if (serviceUpkeepData.m_ScaleWithUsage && base.EntityManager.TryGetComponent<ServiceUsage>(buildingOwnerEntity, out var component))
				{
					num = (int)((float)num * component.m_Usage);
					num3 = (int)((float)num3 * component.m_Usage);
				}
				if (num != 0 && num3 != 0)
				{
					if (!resourceUpkeep.TryGetValue(resource, out var value2))
					{
						resourceUpkeep[resource] = value2;
					}
					resourceUpkeep[resource] += new UIUpkeepItem(num, num3, resource, string.Empty);
					if (!base.tooltipKeys.Contains(resource.ToString()))
					{
						base.tooltipKeys.Add(resource.ToString());
					}
				}
			}
		}
		if (!m_EconomyParameterQuery.IsEmptyIgnoreFilter && entity == buildingOwnerEntity && base.EntityManager.HasComponent<WorkplaceData>(selectedPrefab))
		{
			int upkeepOfEmployeeWage = CityServiceUpkeepSystem.GetUpkeepOfEmployeeWage(InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RW_BufferLookup, ref base.CheckedStateRef), buildingOwnerEntity, m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(), inactiveBuilding);
			if (!moneyUpkeep.TryGetValue(Resource.Money.ToString(), out var value3))
			{
				moneyUpkeep[Resource.Money.ToString()] = value3;
			}
			moneyUpkeep[Resource.Money.ToString()] += new UIUpkeepItem(upkeepOfEmployeeWage, upkeepOfEmployeeWage, Resource.Money, string.Empty);
		}
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_PrefabUISystem = base.World.GetOrCreateSystemManaged<PrefabUISystem>();
		m_BudgetDataQuery = GetEntityQuery(ComponentType.ReadOnly<ServiceBudgetData>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		resourceUpkeep = new Dictionary<Resource, UIUpkeepItem>(5);
		moneyUpkeep = new Dictionary<string, UIUpkeepItem>(5);
		upkeeps = new List<UIUpkeepItem>(10);
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

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		inactive = (base.EntityManager.TryGetComponent<Building>(selectedEntity, out var component) && BuildingUtils.CheckOption(component, BuildingOption.Inactive)) || (base.EntityManager.TryGetComponent<Extension>(selectedEntity, out var component2) && (component2.m_Flags & ExtensionFlags.Disabled) != 0);
		if (base.EntityManager.TryGetBuffer(selectedPrefab, isReadOnly: true, out DynamicBuffer<ServiceUpkeepData> buffer))
		{
			Entity owner = selectedEntity;
			bool inactiveBuilding = inactive;
			bool inactiveUpgrade = false;
			if (base.EntityManager.HasComponent<Game.Buildings.ServiceUpgrade>(selectedEntity) && base.EntityManager.TryGetComponent<Owner>(selectedEntity, out var component3) && base.EntityManager.TryGetComponent<Building>(component3.m_Owner, out component))
			{
				owner = component3.m_Owner;
				inactiveUpgrade = inactive;
				inactiveBuilding = BuildingUtils.CheckOption(component, BuildingOption.Inactive);
			}
			CalculateServiceUpkeepDatas(owner, selectedPrefab, owner, buffer, inactiveBuilding, inactiveUpgrade);
			if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<InstalledUpgrade> buffer2))
			{
				for (int i = 0; i < buffer2.Length; i++)
				{
					InstalledUpgrade installedUpgrade = buffer2[i];
					if (base.EntityManager.TryGetComponent<PrefabRef>(installedUpgrade.m_Upgrade, out var component4) && base.EntityManager.TryGetBuffer(component4.m_Prefab, isReadOnly: true, out DynamicBuffer<ServiceUpkeepData> buffer3))
					{
						CalculateServiceUpkeepDatas(installedUpgrade.m_Upgrade, component4.m_Prefab, owner, buffer3, inactiveBuilding, BuildingUtils.CheckOption(installedUpgrade, BuildingOption.Inactive));
					}
				}
			}
		}
		foreach (KeyValuePair<string, UIUpkeepItem> item in moneyUpkeep)
		{
			upkeeps.Add(item.Value);
			total += item.Value.price;
		}
		foreach (KeyValuePair<Resource, UIUpkeepItem> item2 in resourceUpkeep)
		{
			upkeeps.Add(item2.Value);
			total += item2.Value.price;
		}
		upkeeps.Sort();
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
		writer.PropertyName("upkeeps");
		writer.ArrayBegin(upkeeps.Count);
		for (int i = 0; i < upkeeps.Count; i++)
		{
			writer.Write(upkeeps[i]);
		}
		writer.ArrayEnd();
		writer.PropertyName("total");
		writer.Write(total);
		writer.PropertyName("inactive");
		writer.Write(inactive);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		moneyUpkeep.Clear();
		resourceUpkeep.Clear();
		upkeeps.Clear();
		total = 0;
		inactive = false;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (!base.EntityManager.HasComponent<ServiceUpkeepData>(selectedPrefab))
		{
			if (base.EntityManager.HasComponent<ServiceObjectData>(selectedPrefab))
			{
				return base.EntityManager.HasComponent<WorkplaceData>(selectedPrefab);
			}
			return false;
		}
		return true;
	}
```


## Nested types

- `Game.UI.InGame.UpkeepSection+UIUpkeepItem`  
- `Game.UI.InGame.UpkeepSection+TypeHandle`  

