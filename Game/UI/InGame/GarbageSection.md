# Game.UI.InGame.GarbageSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private System.Int32 <garbage>k__BackingField;
    private System.Int32 <garbageCapacity>k__BackingField;
    private System.Int32 <processingSpeed>k__BackingField;
    private System.Int32 <processingCapacity>k__BackingField;
    private Game.UI.InGame.GarbageSection+LoadKey <loadKey>k__BackingField;

    protected System.String group { protected get; }
    private System.Int32 garbage { private get; private set; }
    private System.Int32 garbageCapacity { private get; private set; }
    private System.Int32 processingSpeed { private get; private set; }
    private System.Int32 processingCapacity { private get; private set; }
    private Game.UI.InGame.GarbageSection+LoadKey loadKey { private get; private set; }

    public GarbageSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private System.Int32 <garbage>k__BackingField`  

```csharp
private System.Int32 <garbage>k__BackingField;
```

- `private System.Int32 <garbageCapacity>k__BackingField`  

```csharp
private System.Int32 <garbageCapacity>k__BackingField;
```

- `private System.Int32 <processingSpeed>k__BackingField`  

```csharp
private System.Int32 <processingSpeed>k__BackingField;
```

- `private System.Int32 <processingCapacity>k__BackingField`  

```csharp
private System.Int32 <processingCapacity>k__BackingField;
```

- `private Game.UI.InGame.GarbageSection+LoadKey <loadKey>k__BackingField`  

```csharp
private Game.UI.InGame.GarbageSection+LoadKey <loadKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private System.Int32 garbage { private get; private set }`  

```csharp
private System.Int32 garbage { private get; private set; }
```

- `private System.Int32 garbageCapacity { private get; private set }`  

```csharp
private System.Int32 garbageCapacity { private get; private set; }
```

- `private System.Int32 processingSpeed { private get; private set }`  

```csharp
private System.Int32 processingSpeed { private get; private set; }
```

- `private System.Int32 processingCapacity { private get; private set }`  

```csharp
private System.Int32 processingCapacity { private get; private set; }
```

- `private Game.UI.InGame.GarbageSection+LoadKey loadKey { private get; private set }`  

```csharp
private Game.UI.InGame.GarbageSection+LoadKey loadKey { private get; private set; }
```


## Constructors

- `public GarbageSection()`  

```csharp
[Preserve]
	public GarbageSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.TryGetComponent<Game.Buildings.GarbageFacility>(selectedEntity, out var component))
		{
			if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Resources> buffer))
			{
				garbage = EconomyUtils.GetResources(Resource.Garbage, buffer);
			}
			if (TryGetComponentWithUpgrades<GarbageFacilityData>(selectedEntity, selectedPrefab, out var data))
			{
				garbageCapacity = data.m_GarbageCapacity;
				processingSpeed = component.m_ProcessingRate;
				processingCapacity = data.m_ProcessingSpeed;
				if (data.m_LongTermStorage)
				{
					base.tooltipKeys.Add("Landfill");
				}
				if (base.EntityManager.HasComponent<Game.Buildings.ResourceProducer>(selectedEntity))
				{
					base.tooltipKeys.Add("RecyclingCenter");
				}
				if (base.EntityManager.HasComponent<ElectricityProducer>(selectedEntity))
				{
					base.tooltipKeys.Add("Incinerator");
				}
				if (data.m_IndustrialWasteOnly)
				{
					base.tooltipKeys.Add("HazardousWaste");
					loadKey = LoadKey.IndustrialWaste;
				}
			}
		}
		if (!base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Game.Areas.SubArea> buffer2))
		{
			return;
		}
		for (int i = 0; i < buffer2.Length; i++)
		{
			Entity area = buffer2[i].m_Area;
			if (base.EntityManager.TryGetComponent<Storage>(area, out var component2))
			{
				PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(area);
				Geometry componentData2 = base.EntityManager.GetComponentData<Geometry>(area);
				if (base.EntityManager.TryGetComponent<StorageAreaData>(componentData.m_Prefab, out var component3))
				{
					garbageCapacity += AreaUtils.CalculateStorageCapacity(componentData2, component3);
					garbage += component2.m_Amount;
				}
			}
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
		writer.PropertyName("garbage");
		writer.Write(garbage);
		writer.PropertyName("garbageCapacity");
		writer.Write(garbageCapacity);
		writer.PropertyName("processingSpeed");
		writer.Write(processingSpeed);
		writer.PropertyName("processingCapacity");
		writer.Write(processingCapacity);
		writer.PropertyName("loadKey");
		writer.Write(Enum.GetName(typeof(LoadKey), loadKey));
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		garbage = 0;
		garbageCapacity = 0;
		processingSpeed = 0;
		processingCapacity = 0;
		loadKey = LoadKey.Garbage;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		return base.EntityManager.HasComponent<Game.Buildings.GarbageFacility>(selectedEntity);
	}
```


## Nested types

- `Game.UI.InGame.GarbageSection+LoadKey`  

