# Game.UI.InGame.HealthcareVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthcareVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <patientEntity>k__BackingField;
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity patientEntity { private get; private set; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public HealthcareVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity <patientEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <patientEntity>k__BackingField;
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

- `private Unity.Entities.Entity patientEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity patientEntity { private get; private set; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```


## Constructors

- `public HealthcareVehicleSection()`  

```csharp
[Preserve]
	public HealthcareVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Vehicles.Ambulance componentData = base.EntityManager.GetComponentData<Game.Vehicles.Ambulance>(selectedEntity);
		patientEntity = componentData.m_TargetPatient;
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, componentData, base.EntityManager);
		vehicleKey = (base.EntityManager.HasComponent<HelicopterData>(selectedPrefab) ? VehicleLocaleKey.MedicalHelicopter : VehicleLocaleKey.Ambulance);
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
		writer.PropertyName("patient");
		if (patientEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, patientEntity);
		}
		writer.PropertyName("patientEntity");
		if (patientEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(patientEntity);
		}
		writer.PropertyName("vehicleKey");
		writer.Write(Enum.GetName(typeof(VehicleLocaleKey), vehicleKey));
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		base.Reset();
		patientEntity = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<Game.Vehicles.Ambulance>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Owner>(selectedEntity);
		}
		return false;
	}
```


