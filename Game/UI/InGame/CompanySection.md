# Game.UI.InGame.CompanySection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanySection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity companyEntity;
    private Game.Economy.Resource <input1>k__BackingField;
    private Game.Economy.Resource <input2>k__BackingField;
    private Game.Economy.Resource <output>k__BackingField;
    private Game.Economy.Resource <sells>k__BackingField;
    private Game.Economy.Resource <stores>k__BackingField;
    private Unity.Mathematics.int2 <customers>k__BackingField;
    private System.Single <price>k__BackingField;
    private System.Boolean <isRentable>k__BackingField;

    protected System.String group { protected get; }
    private Game.Economy.Resource input1 { private get; private set; }
    private Game.Economy.Resource input2 { private get; private set; }
    private Game.Economy.Resource output { private get; private set; }
    private Game.Economy.Resource sells { private get; private set; }
    private Game.Economy.Resource stores { private get; private set; }
    private Unity.Mathematics.int2 customers { private get; private set; }
    private System.Single price { private get; private set; }
    private System.Boolean isRentable { private get; private set; }

    public CompanySection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity companyEntity`  

```csharp
private Unity.Entities.Entity companyEntity;
```

- `private Game.Economy.Resource <input1>k__BackingField`  

```csharp
private Game.Economy.Resource <input1>k__BackingField;
```

- `private Game.Economy.Resource <input2>k__BackingField`  

```csharp
private Game.Economy.Resource <input2>k__BackingField;
```

- `private Game.Economy.Resource <output>k__BackingField`  

```csharp
private Game.Economy.Resource <output>k__BackingField;
```

- `private Game.Economy.Resource <sells>k__BackingField`  

```csharp
private Game.Economy.Resource <sells>k__BackingField;
```

- `private Game.Economy.Resource <stores>k__BackingField`  

```csharp
private Game.Economy.Resource <stores>k__BackingField;
```

- `private Unity.Mathematics.int2 <customers>k__BackingField`  

```csharp
private Unity.Mathematics.int2 <customers>k__BackingField;
```

- `private System.Single <price>k__BackingField`  

```csharp
private System.Single <price>k__BackingField;
```

- `private System.Boolean <isRentable>k__BackingField`  

```csharp
private System.Boolean <isRentable>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.Economy.Resource input1 { private get; private set }`  

```csharp
private Game.Economy.Resource input1 { private get; private set; }
```

- `private Game.Economy.Resource input2 { private get; private set }`  

```csharp
private Game.Economy.Resource input2 { private get; private set; }
```

- `private Game.Economy.Resource output { private get; private set }`  

```csharp
private Game.Economy.Resource output { private get; private set; }
```

- `private Game.Economy.Resource sells { private get; private set }`  

```csharp
private Game.Economy.Resource sells { private get; private set; }
```

- `private Game.Economy.Resource stores { private get; private set }`  

```csharp
private Game.Economy.Resource stores { private get; private set; }
```

- `private Unity.Mathematics.int2 customers { private get; private set }`  

```csharp
private Unity.Mathematics.int2 customers { private get; private set; }
```

- `private System.Single price { private get; private set }`  

```csharp
private System.Single price { private get; private set; }
```

- `private System.Boolean isRentable { private get; private set }`  

```csharp
private System.Boolean isRentable { private get; private set; }
```


## Constructors

- `public CompanySection()`  

```csharp
[Preserve]
	public CompanySection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (companyEntity == Entity.Null)
		{
			if (base.EntityManager.TryGetComponent<SpawnableBuildingData>(selectedPrefab, out var component) && base.EntityManager.TryGetComponent<ZoneData>(component.m_ZonePrefab, out var component2))
			{
				switch (component2.m_AreaType)
				{
				case AreaType.Commercial:
					base.tooltipKeys.Add("VacantCommercial");
					break;
				case AreaType.Industrial:
					base.tooltipKeys.Add(component2.IsOffice() ? "VacantOffice" : "VacantIndustrial");
					break;
				}
			}
			if (base.EntityManager.HasComponent<PropertyOnMarket>(selectedEntity))
			{
				isRentable = true;
			}
		}
		if (base.EntityManager.TryGetBuffer(companyEntity, isReadOnly: true, out DynamicBuffer<Resources> _) && base.EntityManager.TryGetComponent<PrefabRef>(companyEntity, out var component3) && base.EntityManager.TryGetComponent<IndustrialProcessData>(component3.m_Prefab, out var component4))
		{
			if (base.EntityManager.HasComponent<ServiceAvailable>(companyEntity))
			{
				Resource resource = component4.m_Input1.m_Resource;
				Resource resource2 = component4.m_Input2.m_Resource;
				Resource resource3 = component4.m_Output.m_Resource;
				if (resource != Resource.NoResource && resource != resource3)
				{
					input1 = resource;
				}
				if (resource2 != Resource.NoResource && resource2 != resource3 && resource2 != resource)
				{
					input2 = resource2;
					base.tooltipKeys.Add("Requires");
				}
				sells = resource3;
				base.tooltipKeys.Add("Sells");
			}
			else if (base.EntityManager.HasComponent<Game.Companies.ProcessingCompany>(companyEntity))
			{
				input1 = component4.m_Input1.m_Resource;
				input2 = component4.m_Input2.m_Resource;
				output = component4.m_Output.m_Resource;
				base.tooltipKeys.Add("Requires");
				base.tooltipKeys.Add("Produces");
			}
			else if (base.EntityManager.HasComponent<Game.Companies.ExtractorCompany>(companyEntity))
			{
				output = component4.m_Output.m_Resource;
				base.tooltipKeys.Add("Produces");
			}
			else if (base.EntityManager.HasComponent<Game.Companies.StorageCompany>(companyEntity))
			{
				stores = base.EntityManager.GetComponentData<StorageCompanyData>(component3.m_Prefab).m_StoredResources;
				base.tooltipKeys.Add("Stores");
			}
		}
		if (base.EntityManager.TryGetComponent<LodgingProvider>(companyEntity, out var component5) && base.EntityManager.TryGetBuffer(companyEntity, isReadOnly: true, out DynamicBuffer<Renter> buffer2))
		{
			customers = new int2(buffer2.Length, buffer2.Length + component5.m_FreeRooms);
			price = component5.m_Price;
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
		writer.PropertyName("companyName");
		if (companyEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, companyEntity);
		}
		writer.PropertyName("isRentable");
		writer.Write(isRentable);
		writer.PropertyName("input1");
		if (input1 == Resource.NoResource)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(Enum.GetName(typeof(Resource), input1));
		}
		writer.PropertyName("input2");
		if (input2 == Resource.NoResource)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(Enum.GetName(typeof(Resource), input2));
		}
		writer.PropertyName("output");
		if (output == Resource.NoResource)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(Enum.GetName(typeof(Resource), output));
		}
		writer.PropertyName("sells");
		if (sells == Resource.NoResource)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(Enum.GetName(typeof(Resource), sells));
		}
		writer.PropertyName("stores");
		if (stores == Resource.NoResource)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(Enum.GetName(typeof(Resource), stores));
		}
		writer.PropertyName("customers");
		if (customers.y == 0)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(customers);
		}
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		companyEntity = Entity.Null;
		input1 = Resource.NoResource;
		input2 = Resource.NoResource;
		output = Resource.NoResource;
		sells = Resource.NoResource;
		stores = Resource.NoResource;
		customers = int2.zero;
		isRentable = false;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return CompanyUIUtils.HasCompany(base.EntityManager, selectedEntity, selectedPrefab, out companyEntity);
	}
```


## Nested types

- `Game.UI.InGame.CompanySection+ExtractedKey`  

