# Game.UI.InGame.StorageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StorageSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity m_CompanyEntity;
    private System.Int32 <stored>k__BackingField;
    private System.Int32 <capacity>k__BackingField;
    private Game.UI.InGame.StorageSection+StorageStatus <status>k__BackingField;
    private Game.UI.InGame.UIResource+StorageType <storageType>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField;
    private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;

    protected System.String group { protected get; }
    private System.Int32 stored { private get; private set; }
    private System.Int32 capacity { private get; private set; }
    private Game.UI.InGame.StorageSection+StorageStatus status { private get; private set; }
    private Game.UI.InGame.UIResource+StorageType storageType { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set; }

    public StorageSection();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity m_CompanyEntity`  

```csharp
private Unity.Entities.Entity m_CompanyEntity;
```

- `private System.Int32 <stored>k__BackingField`  

```csharp
private System.Int32 <stored>k__BackingField;
```

- `private System.Int32 <capacity>k__BackingField`  

```csharp
private System.Int32 <capacity>k__BackingField;
```

- `private Game.UI.InGame.StorageSection+StorageStatus <status>k__BackingField`  

```csharp
private Game.UI.InGame.StorageSection+StorageStatus <status>k__BackingField;
```

- `private Game.UI.InGame.UIResource+StorageType <storageType>k__BackingField`  

```csharp
private Game.UI.InGame.UIResource+StorageType <storageType>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField;
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField;
```

- `private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs`  

```csharp
private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 stored { private get; private set }`  

```csharp
private System.Int32 stored { private get; private set; }
```

- `private System.Int32 capacity { private get; private set }`  

```csharp
private System.Int32 capacity { private get; private set; }
```

- `private Game.UI.InGame.StorageSection+StorageStatus status { private get; private set }`  

```csharp
private Game.UI.InGame.StorageSection+StorageStatus status { private get; private set; }
```

- `private Game.UI.InGame.UIResource+StorageType storageType { private get; private set }`  

```csharp
private Game.UI.InGame.UIResource+StorageType storageType { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set; }
```

- `private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set }`  

```csharp
private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set; }
```


## Constructors

- `public StorageSection()`  

```csharp
[Preserve]
	public StorageSection()
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
		rawMaterials = new NativeList<UIResource>(Allocator.Persistent);
		processedGoods = new NativeList<UIResource>(Allocator.Persistent);
		mail = new NativeList<UIResource>(Allocator.Persistent);
		m_ResourcePrefabs = base.World.GetOrCreateSystemManaged<ResourceSystem>().GetPrefabs();
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		rawMaterials.Dispose();
		processedGoods.Dispose();
		mail.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Resources> buffer) || base.EntityManager.TryGetBuffer(m_CompanyEntity, isReadOnly: true, out buffer))
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Resources resources = buffer[i];
				if (EconomyUtils.GetWeight(base.EntityManager, resources.m_Resource, m_ResourcePrefabs) != 0f)
				{
					UIResource.CategorizeResources(resources.m_Resource, resources.m_Amount, rawMaterials, processedGoods, mail, base.EntityManager, m_ResourcePrefabs, storageType);
					stored += buffer[i].m_Amount;
				}
			}
		}
		stored = math.min(math.max(stored, 0), capacity);
		status = ((stored == capacity) ? StorageStatus.Full : (((double)stored >= (double)capacity * 0.8) ? StorageStatus.NearlyFull : (((double)stored >= (double)capacity * 0.2) ? StorageStatus.Balanced : ((stored <= 0) ? StorageStatus.Empty : StorageStatus.NearlyEmpty))));
		if (TryGetComponentWithUpgrades<StorageCompanyData>(selectedEntity, selectedPrefab, out var data))
		{
			foreach (Resource value2 in Enum.GetValues(typeof(Resource)))
			{
				UIResource value = new UIResource(value2, 0, storageType, base.EntityManager, m_ResourcePrefabs);
				if ((data.m_StoredResources & value2) != Resource.NoResource && EconomyUtils.GetWeight(base.EntityManager, value2, m_ResourcePrefabs) != 0f && !rawMaterials.Contains(value) && !processedGoods.Contains(value) && !mail.Contains(value))
				{
					UIResource.CategorizeResources(value2, 0, rawMaterials, processedGoods, mail, base.EntityManager, m_ResourcePrefabs, storageType);
				}
			}
		}
		if (storageType != UIResource.StorageType.None)
		{
			base.tooltipKeys.Add(storageType.ToString());
		}
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
		writer.PropertyName("stored");
		writer.Write(stored);
		writer.PropertyName("capacity");
		writer.Write(capacity);
		writer.PropertyName("status");
		writer.Write(Enum.GetName(typeof(StorageStatus), status));
		writer.PropertyName("storageType");
		writer.Write(Enum.GetName(typeof(UIResource.StorageType), storageType));
		rawMaterials.Sort();
		writer.PropertyName("rawMaterials");
		writer.ArrayBegin(rawMaterials.Length);
		for (int i = 0; i < rawMaterials.Length; i++)
		{
			writer.Write(rawMaterials[i]);
		}
		writer.ArrayEnd();
		processedGoods.Sort();
		writer.PropertyName("processedGoods");
		writer.ArrayBegin(processedGoods.Length);
		for (int j = 0; j < processedGoods.Length; j++)
		{
			writer.Write(processedGoods[j]);
		}
		writer.ArrayEnd();
		mail.Sort();
		writer.PropertyName("mail");
		writer.ArrayBegin(mail.Length);
		for (int k = 0; k < mail.Length; k++)
		{
			writer.Write(mail[k]);
		}
		writer.ArrayEnd();
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		rawMaterials.Clear();
		processedGoods.Clear();
		mail.Clear();
		stored = 0;
		capacity = 0;
		m_CompanyEntity = Entity.Null;
		status = StorageStatus.None;
		storageType = UIResource.StorageType.Company;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<CargoTransportStationData>(selectedPrefab) && TryGetComponentWithUpgrades<StorageLimitData>(selectedEntity, selectedPrefab, out var data))
		{
			capacity = data.m_Limit;
			storageType = UIResource.StorageType.Cargo;
		}
		Entity entity = Entity.Null;
		if (CompanyUIUtils.HasCompany(base.EntityManager, selectedEntity, selectedPrefab, out m_CompanyEntity) && base.EntityManager.TryGetComponent<PrefabRef>(m_CompanyEntity, out var component) && base.EntityManager.TryGetComponent<StorageLimitData>(component.m_Prefab, out data))
		{
			entity = component.m_Prefab;
			bool flag = false;
			if (base.EntityManager.TryGetComponent<IndustrialProcessData>(component.m_Prefab, out var component2))
			{
				bool num = EconomyUtils.GetWeight(base.EntityManager, component2.m_Input1.m_Resource, m_ResourcePrefabs) > 0f;
				bool flag2 = EconomyUtils.GetWeight(base.EntityManager, component2.m_Input2.m_Resource, m_ResourcePrefabs) > 0f;
				bool flag3 = EconomyUtils.GetWeight(base.EntityManager, component2.m_Output.m_Resource, m_ResourcePrefabs) > 0f;
				flag = num || flag2 || flag3;
			}
			if (base.EntityManager.TryGetComponent<PropertyRenter>(selectedEntity, out var component3) && base.EntityManager.TryGetComponent<PrefabRef>(component3.m_Property, out var component4) && base.EntityManager.TryGetComponent<BuildingPropertyData>(component4.m_Prefab, out var component5) && base.EntityManager.TryGetComponent<SpawnableBuildingData>(component4.m_Prefab, out var component6) && base.EntityManager.TryGetComponent<BuildingData>(component4.m_Prefab, out var component7))
			{
				bool flag4 = component5.m_AllowedStored != Resource.NoResource;
				if (flag4)
				{
					storageType = UIResource.StorageType.Warehouse;
				}
				capacity = (flag ? (flag4 ? data.GetAdjustedLimitForWarehouse(component6, component7) : data.m_Limit) : 0);
			}
			else if (base.EntityManager.TryGetComponent<BuildingPropertyData>(selectedPrefab, out component5) && base.EntityManager.TryGetComponent<SpawnableBuildingData>(selectedPrefab, out component6) && base.EntityManager.TryGetComponent<BuildingData>(selectedPrefab, out component7))
			{
				bool flag5 = component5.m_AllowedStored != Resource.NoResource;
				if (flag5)
				{
					storageType = UIResource.StorageType.Warehouse;
				}
				capacity = (flag ? (flag5 ? data.GetAdjustedLimitForWarehouse(component6, component7) : data.m_Limit) : 0);
			}
			else
			{
				capacity = data.m_Limit;
			}
		}
		Entity entity2 = Entity.Null;
		PropertyRenter component9;
		if (base.EntityManager.TryGetComponent<Attached>(selectedEntity, out var component8) && base.EntityManager.HasBuffer<InstalledUpgrade>(component8.m_Parent))
		{
			entity2 = component8.m_Parent;
		}
		else if (base.EntityManager.TryGetComponent<PropertyRenter>(selectedEntity, out component9) && base.EntityManager.TryGetComponent<Attached>(component9.m_Property, out component8) && base.EntityManager.HasBuffer<InstalledUpgrade>(component8.m_Parent))
		{
			entity2 = component8.m_Parent;
		}
		if (entity2 != Entity.Null && entity == Entity.Null)
		{
			entity = selectedPrefab;
		}
		if (entity2 != Entity.Null && TryGetComponentWithUpgrades<StorageLimitData>(entity2, entity, out var data2))
		{
			capacity = data2.m_Limit;
		}
		return capacity > 0;
	}
```


## Nested types

- `Game.UI.InGame.StorageSection+StorageStatus`  

