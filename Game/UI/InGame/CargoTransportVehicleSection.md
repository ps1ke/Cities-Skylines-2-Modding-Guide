# Game.UI.InGame.CargoTransportVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleWithLineSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CargoTransportVehicleSection : Game.UI.InGame.VehicleWithLineSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    protected System.String group { protected get; }

    public CargoTransportVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    private System.Boolean Visible();
}
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```


## Constructors

- `public CargoTransportVehicleSection()`  

```csharp
[Preserve]
	public CargoTransportVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		CargoTransport componentData = base.EntityManager.GetComponentData<CargoTransport>(selectedEntity);
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, componentData, base.EntityManager);
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

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<CargoTransport>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Owner>(selectedEntity);
		}
		return false;
	}
```


