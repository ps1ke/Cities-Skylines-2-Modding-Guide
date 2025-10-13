# Game.UI.InGame.PrivateVehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PrivateVehicleSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <keeperEntity>k__BackingField;
    private Game.UI.InGame.VehicleLocaleKey <vehicleKey>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity keeperEntity { private get; private set; }
    private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }

    public PrivateVehicleSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity <keeperEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <keeperEntity>k__BackingField;
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

- `private Unity.Entities.Entity keeperEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity keeperEntity { private get; private set; }
```

- `private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set }`  

```csharp
private Game.UI.InGame.VehicleLocaleKey vehicleKey { private get; private set; }
```


## Constructors

- `public PrivateVehicleSection()`  

```csharp
[Preserve]
	public PrivateVehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		base.stateKey = VehicleUIUtils.GetStateKey(selectedEntity, base.EntityManager);
		keeperEntity = Entity.Null;
		if (base.stateKey != VehicleStateLocaleKey.Parked)
		{
			keeperEntity = (base.EntityManager.TryGetComponent<PersonalCar>(selectedEntity, out var component) ? component.m_Keeper : Entity.Null);
		}
		vehicleKey = (base.EntityManager.HasComponent<Taxi>(selectedEntity) ? VehicleLocaleKey.Taxi : VehicleLocaleKey.HouseholdVehicle);
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
		writer.PropertyName("keeper");
		if (keeperEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, keeperEntity);
		}
		writer.PropertyName("keeperEntity");
		if (keeperEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(keeperEntity);
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
		keeperEntity = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.HasComponent<Vehicle>(selectedEntity) && base.EntityManager.HasComponent<Owner>(selectedEntity))
		{
			if (!base.EntityManager.HasComponent<PersonalCar>(selectedEntity))
			{
				return base.EntityManager.HasComponent<Taxi>(selectedEntity);
			}
			return true;
		}
		return false;
	}
```


