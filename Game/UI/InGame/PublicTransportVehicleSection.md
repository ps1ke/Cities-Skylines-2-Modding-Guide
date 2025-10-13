# Game.UI.InGame.PublicTransportVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleWithLineSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PublicTransportVehicleSection : Game.UI.InGame.VehicleWithLineSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public PublicTransportVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
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

- `public PublicTransportVehicleSection()`  

```csharp
[Preserve]
	public PublicTransportVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Vehicles.PublicTransport componentData = base.EntityManager.GetComponentData<Game.Vehicles.PublicTransport>(selectedEntity);
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, componentData, base.EntityManager);
		PublicTransportVehicleData componentData2 = base.EntityManager.GetComponentData<PublicTransportVehicleData>(selectedPrefab);
		vehicleKey = (((componentData2.m_PurposeMask & PublicTransportPurpose.PrisonerTransport) != 0) ? VehicleLocaleKey.PrisonVan : (((componentData2.m_PurposeMask & PublicTransportPurpose.Evacuation) != 0 && (componentData.m_State & PublicTransportFlags.Evacuating) != 0) ? VehicleLocaleKey.EvacuationBus : VehicleLocaleKey.PublicTransportVehicle));
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
		writer.PropertyName("vehicleKey");
		writer.Write(Enum.GetName(typeof(VehicleLocaleKey), vehicleKey));
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<Owner>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Game.Vehicles.PublicTransport>(selectedEntity);
		}
		return false;
	}
```


