# Game.UI.InGame.FireVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class FireVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public FireVehicleSection();

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

- `public FireVehicleSection()`  

```csharp
[Preserve]
	public FireVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Game.Vehicles.FireEngine componentData = base.EntityManager.GetComponentData<Game.Vehicles.FireEngine>(selectedEntity);
		base.EntityManager.TryGetBuffer(selectedEntity, isReadOnly: true, out DynamicBuffer<ServiceDispatch> buffer);
		vehicleKey = (base.EntityManager.HasComponent<HelicopterData>(selectedPrefab) ? VehicleLocaleKey.FireHelicopter : VehicleLocaleKey.FireEngine);
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, componentData, buffer, base.EntityManager);
		if (base.stateKey == VehicleStateLocaleKey.Dispatched)
		{
			if (!buffer.IsCreated || buffer.Length == 0)
			{
				return;
			}
			ServiceDispatch serviceDispatch = buffer[0];
			if (!base.EntityManager.TryGetComponent<FireRescueRequest>(serviceDispatch.m_Request, out var component))
			{
				return;
			}
			Destroyed component3;
			if (base.EntityManager.TryGetComponent<OnFire>(component.m_Target, out var component2) && component2.m_Event != Entity.Null)
			{
				base.nextStop = new VehicleUIUtils.EntityWrapper(component2.m_Event);
			}
			else if (base.EntityManager.TryGetComponent<Destroyed>(component.m_Target, out component3) && component3.m_Event != Entity.Null)
			{
				base.nextStop = new VehicleUIUtils.EntityWrapper(component3.m_Event);
			}
			else if (component.m_Target != Entity.Null)
			{
				base.nextStop = new VehicleUIUtils.EntityWrapper(component.m_Target);
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
		writer.PropertyName("vehicleKey");
		writer.Write(Enum.GetName(typeof(VehicleLocaleKey), vehicleKey));
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<Game.Vehicles.FireEngine>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Owner>(selectedEntity);
		}
		return false;
	}
```


