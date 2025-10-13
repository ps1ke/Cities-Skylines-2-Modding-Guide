# Game.UI.InGame.DeliveryVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeliveryVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.Economy.Resource <resource>k__BackingField;
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Game.Economy.Resource resource { private get; private set; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public DeliveryVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.Economy.Resource <resource>k__BackingField`  

```csharp
private Game.Economy.Resource <resource>k__BackingField;
```

- `private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.Economy.Resource resource { private get; private set }`  

```csharp
private Game.Economy.Resource resource { private get; private set; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```


## Constructors

- `public DeliveryVehicleSection()`  

```csharp
[Preserve]
	public DeliveryVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		DeliveryTruck componentData = base.EntityManager.GetComponentData<DeliveryTruck>(selectedEntity);
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<LayoutElement> buffer) && buffer.Length != 0)
		{
			Resource resource = Resource.NoResource;
			for (int i = 0; i < buffer.Length; i++)
			{
				if (base.EntityManager.TryGetComponent<DeliveryTruck>(buffer[i].m_Vehicle, out var component))
				{
					resource |= component.m_Resource;
				}
			}
			this.resource = resource;
		}
		else
		{
			this.resource = componentData.m_Resource;
		}
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, componentData, base.EntityManager);
		vehicleKey = (((this.resource & (Resource)28672uL) != Resource.NoResource) ? VehicleLocaleKey.PostTruck : VehicleLocaleKey.DeliveryTruck);
		base.tooltipKeys.Add(vehicleKey.ToString());
		base.OnProcess();
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
		base.OnWriteProperties(writer);
		writer.PropertyName("resourceKey");
		writer.Write(Enum.GetName(typeof(Resource), resource));
		writer.PropertyName("vehicleKey");
		writer.Write(Enum.GetName(typeof(VehicleLocaleKey), vehicleKey));
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		base.Reset();
		resource = Resource.NoResource;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<DeliveryTruck>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Owner>(selectedEntity);
		}
		return false;
	}
```


