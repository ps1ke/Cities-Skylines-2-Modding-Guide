# Game.UI.InGame.ExtractorVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ExtractorVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public ExtractorVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```


## Constructors

- `public ExtractorVehicleSection()`  

```csharp
[Preserve]
	public ExtractorVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		base.OnProcess();
		PrefabRef component3;
		if (base.EntityManager.TryGetComponent<Owner>(base.owner.entity, out var component) && (base.EntityManager.TryGetComponent<Attachment>(component.m_Owner, out var component2) || (base.EntityManager.TryGetComponent<Owner>(component.m_Owner, out component) && base.EntityManager.TryGetComponent<Attachment>(component.m_Owner, out component2))) && base.EntityManager.TryGetBuffer(component2.m_Attached, isReadOnly: true, out DynamicBuffer<Renter> buffer) && buffer.Length > 0)
		{
			Entity renter = buffer[0].m_Renter;
			Entity entity = base.EntityManager.GetComponentData<PrefabRef>(renter);
			switch (base.EntityManager.GetComponentData<IndustrialProcessData>(entity).m_Output.m_Resource)
			{
			case Resource.Grain:
			case Resource.Vegetables:
			case Resource.Livestock:
			case Resource.Cotton:
				base.stateKey = VehicleStateLocaleKey.Farming;
				vehicleKey = VehicleLocaleKey.FarmVehicle;
				break;
			case Resource.Wood:
				base.stateKey = VehicleStateLocaleKey.Harvesting;
				vehicleKey = VehicleLocaleKey.ForestryVehicle;
				break;
			case Resource.Oil:
				base.stateKey = VehicleStateLocaleKey.Drilling;
				vehicleKey = VehicleLocaleKey.DrillingVehicle;
				break;
			case Resource.Ore:
			case Resource.Coal:
			case Resource.Stone:
				base.stateKey = VehicleStateLocaleKey.Mining;
				vehicleKey = VehicleLocaleKey.MiningVehicle;
				break;
			case Resource.Fish:
				base.stateKey = VehicleStateLocaleKey.Fishing;
				vehicleKey = VehicleLocaleKey.FishingVehicle;
				break;
			default:
				base.stateKey = VehicleStateLocaleKey.Extracting;
				vehicleKey = VehicleLocaleKey.ExtractingVehicle;
				break;
			}
			base.owner = new VehicleUIUtils.EntityWrapper(component2.m_Attached);
		}
		else if (base.EntityManager.TryGetComponent<Owner>(base.owner.entity, out component) && base.EntityManager.TryGetComponent<PrefabRef>(component.m_Owner, out component3) && base.EntityManager.HasComponent<ServiceObjectData>(component3.m_Prefab))
		{
			base.owner = new VehicleUIUtils.EntityWrapper(component.m_Owner);
		}
		else
		{
			base.owner = new VehicleUIUtils.EntityWrapper(Entity.Null);
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
		base.OnWriteProperties(writer);
		writer.PropertyName("vehicleKey");
		writer.Write(Enum.GetName(typeof(VehicleLocaleKey), vehicleKey));
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		base.Reset();
		vehicleKey = VehicleLocaleKey.Vehicle;
		base.stateKey = VehicleStateLocaleKey.Working;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Game.Vehicles.WorkVehicle>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Owner>(selectedEntity);
		}
		return false;
	}
```


