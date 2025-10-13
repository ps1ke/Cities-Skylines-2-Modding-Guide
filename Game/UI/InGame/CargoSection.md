# Game.UI.InGame.CargoSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CargoSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <cargo>k__BackingField;
    private System.Int32 <capacity>k__BackingField;
    private Game.UI.InGame.CargoSection+CargoKey <cargoKey>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <rawMaterials>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <processedGoods>k__BackingField;
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> <mail>k__BackingField;
    private Game.Prefabs.ResourcePrefabs m_ResourcePrefabs;

    protected System.String group { protected get; }
    private System.Int32 cargo { private get; private set; }
    private System.Int32 capacity { private get; private set; }
    private Game.UI.InGame.CargoSection+CargoKey cargoKey { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> rawMaterials { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> processedGoods { private get; private set; }
    private Unity.Collections.NativeList<Game.UI.InGame.UIResource> mail { private get; private set; }
    protected Unity.Entities.Entity selectedEntity { protected get; }
    protected Unity.Entities.Entity selectedPrefab { protected get; }

    public CargoSection();

    private System.Void AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target);
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

- `private System.Int32 <cargo>k__BackingField`  

```csharp
private System.Int32 <cargo>k__BackingField;
```

- `private System.Int32 <capacity>k__BackingField`  

```csharp
private System.Int32 <capacity>k__BackingField;
```

- `private Game.UI.InGame.CargoSection+CargoKey <cargoKey>k__BackingField`  

```csharp
private Game.UI.InGame.CargoSection+CargoKey <cargoKey>k__BackingField;
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

- `private System.Int32 cargo { private get; private set }`  

```csharp
private System.Int32 cargo { private get; private set; }
```

- `private System.Int32 capacity { private get; private set }`  

```csharp
private System.Int32 capacity { private get; private set; }
```

- `private Game.UI.InGame.CargoSection+CargoKey cargoKey { private get; private set }`  

```csharp
private Game.UI.InGame.CargoSection+CargoKey cargoKey { private get; private set; }
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

- `protected Unity.Entities.Entity selectedEntity { protected get }`  

```csharp
protected Unity.Entities.Entity selectedEntity { protected get; }
```

- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

```csharp
protected Unity.Entities.Entity selectedPrefab { protected get; }
```


## Constructors

- `public CargoSection()`  

```csharp
[Preserve]
	public CargoSection()
	{
	}
```


## Methods

- `private AddResources(Unity.Entities.DynamicBuffer<Game.Economy.Resources> source, Unity.Collections.NativeList<Game.Economy.Resources> target) : System.Void`  

```csharp
private void AddResources(DynamicBuffer<Resources> source, NativeList<Resources> target)
	{
		for (int i = 0; i < source.Length; i++)
		{
			Resources value = source[i];
			if (value.m_Amount == 0)
			{
				continue;
			}
			int num = 0;
			while (true)
			{
				if (num < target.Length)
				{
					Resources value2 = target[num];
					if (value2.m_Resource == value.m_Resource)
					{
						value2.m_Amount += value.m_Amount;
						target[num] = value2;
						break;
					}
					num++;
					continue;
				}
				target.Add(in value);
				break;
			}
		}
	}
```

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
		cargoKey = CargoKey.Cargo;
		if (base.EntityManager.TryGetComponent<Game.Vehicles.DeliveryTruck>(selectedEntity, out var component))
		{
			Resource resource = Resource.NoResource;
			if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<LayoutElement> buffer) && buffer.Length != 0)
			{
				int num = 0;
				for (int i = 0; i < buffer.Length; i++)
				{
					Entity vehicle = buffer[i].m_Vehicle;
					if (base.EntityManager.TryGetComponent<Game.Vehicles.DeliveryTruck>(vehicle, out var component2))
					{
						resource |= component2.m_Resource;
						if ((component2.m_State & DeliveryTruckFlags.Loaded) != 0)
						{
							num += component2.m_Amount;
						}
					}
				}
				cargo = num;
			}
			else
			{
				resource = component.m_Resource;
				cargo = (((component.m_State & DeliveryTruckFlags.Loaded) != 0) ? component.m_Amount : 0);
			}
			UIResource.CategorizeResources(resource, cargo, rawMaterials, processedGoods, mail, base.EntityManager, m_ResourcePrefabs);
			return;
		}
		NativeList<Resources> target = new NativeList<Resources>(32, Allocator.Temp);
		DynamicBuffer<Resources> buffer4;
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<LayoutElement> buffer2))
		{
			for (int j = 0; j < buffer2.Length; j++)
			{
				Entity vehicle2 = buffer2[j].m_Vehicle;
				if (base.EntityManager.TryGetBuffer(vehicle2, isReadOnly: true, out DynamicBuffer<Resources> buffer3))
				{
					AddResources(buffer3, target);
				}
			}
		}
		else if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out buffer4))
		{
			AddResources(buffer4, target);
		}
		for (int k = 0; k < target.Length; k++)
		{
			Resources resources = target[k];
			UIResource.CategorizeResources(resources.m_Resource, resources.m_Amount, rawMaterials, processedGoods, mail, base.EntityManager, m_ResourcePrefabs);
			cargo += resources.m_Amount;
		}
		target.Dispose();
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
		writer.PropertyName("cargo");
		writer.Write(cargo);
		writer.PropertyName("capacity");
		writer.Write(capacity);
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
		writer.PropertyName("cargoKey");
		writer.Write(Enum.GetName(typeof(CargoKey), cargoKey));
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		rawMaterials.Clear();
		processedGoods.Clear();
		mail.Clear();
		cargo = 0;
		capacity = 0;
		cargoKey = CargoKey.Cargo;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (!base.EntityManager.HasComponent<Vehicle>(selectedEntity))
		{
			return false;
		}
		DeliveryTruckData component4;
		CargoTransportVehicleData component5;
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<LayoutElement> buffer) && buffer.Length != 0)
		{
			for (int i = 0; i < buffer.Length; i++)
			{
				Entity vehicle = buffer[i].m_Vehicle;
				if (base.EntityManager.TryGetComponent<PrefabRef>(vehicle, out var component))
				{
					CargoTransportVehicleData component3;
					if (base.EntityManager.TryGetComponent<DeliveryTruckData>(component.m_Prefab, out var component2))
					{
						capacity += component2.m_CargoCapacity;
					}
					else if (base.EntityManager.TryGetComponent<CargoTransportVehicleData>(component.m_Prefab, out component3))
					{
						capacity += component3.m_CargoCapacity;
					}
				}
			}
		}
		else if (base.EntityManager.TryGetComponent<DeliveryTruckData>(selectedPrefab, out component4))
		{
			capacity = component4.m_CargoCapacity;
		}
		else if (base.EntityManager.TryGetComponent<CargoTransportVehicleData>(selectedPrefab, out component5))
		{
			capacity = component5.m_CargoCapacity;
		}
		return capacity > 0;
	}
```


## Nested types

- `Game.UI.InGame.CargoSection+CargoKey`  

