# Game.UI.InGame.PoliceVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PoliceVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <criminalEntity>k__BackingField;
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity criminalEntity { private get; private set; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public PoliceVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity <criminalEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <criminalEntity>k__BackingField;
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

- `private Unity.Entities.Entity criminalEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity criminalEntity { private get; private set; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```


## Constructors

- `public PoliceVehicleSection()`  

```csharp
[Preserve]
	public PoliceVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Vehicles.PoliceCar componentData = base.EntityManager.GetComponentData<Game.Vehicles.PoliceCar>(selectedEntity);
		PoliceCarData componentData2 = base.EntityManager.GetComponentData<PoliceCarData>(selectedPrefab);
		base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<ServiceDispatch> buffer);
		if (base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<Passenger> buffer2))
		{
			for (int i = 0; i < buffer2.Length; i++)
			{
				Entity entity = buffer2[i].m_Passenger;
				if (base.EntityManager.TryGetComponent<Game.Creatures.Resident>(entity, out var component))
				{
					entity = component.m_Citizen;
				}
				if (base.EntityManager.HasComponent<Citizen>(entity))
				{
					criminalEntity = entity;
				}
			}
		}
		vehicleKey = (base.EntityManager.HasComponent<HelicopterData>(selectedPrefab) ? VehicleLocaleKey.PoliceHelicopter : VehicleUIUtils.GetPoliceVehicleLocaleKey(componentData2.m_PurposeMask));
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, componentData, buffer, base.EntityManager);
		if ((componentData.m_State & PoliceCarFlags.AccidentTarget) != 0 && (componentData.m_State & PoliceCarFlags.AtTarget) == 0)
		{
			if (componentData.m_RequestCount <= 0 || !buffer.IsCreated || buffer.Length <= 0)
			{
				return;
			}
			ServiceDispatch serviceDispatch = buffer[0];
			if (!base.EntityManager.TryGetComponent<PoliceEmergencyRequest>(serviceDispatch.m_Request, out var component2))
			{
				return;
			}
			if (base.EntityManager.TryGetComponent<AccidentSite>(component2.m_Site, out var component3) && component3.m_Event != Entity.Null)
			{
				base.nextStop = new VehicleUIUtils.EntityWrapper(component3.m_Event);
			}
			else
			{
				base.nextStop = new VehicleUIUtils.EntityWrapper(component2.m_Target);
			}
		}
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
		writer.PropertyName("criminal");
		if (criminalEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, criminalEntity);
		}
		writer.PropertyName("criminalEntity");
		if (criminalEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(criminalEntity);
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
		criminalEntity = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<Game.Vehicles.PoliceCar>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Owner>(selectedEntity);
		}
		return false;
	}
```


