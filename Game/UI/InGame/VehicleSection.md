# Game.UI.InGame.VehicleSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public abstract class VehicleSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.VehicleStateLocaleKey <stateKey>k__BackingField;
    private Game.UI.InGame.VehicleUIUtils+EntityWrapper <owner>k__BackingField;
    private System.Boolean <fromOutside>k__BackingField;
    private Game.UI.InGame.VehicleUIUtils+EntityWrapper <nextStop>k__BackingField;

    protected Game.UI.InGame.VehicleStateLocaleKey stateKey { protected get; protected set; }
    protected Game.UI.InGame.VehicleUIUtils+EntityWrapper owner { protected get; protected set; }
    protected System.Boolean fromOutside { protected get; protected set; }
    protected Game.UI.InGame.VehicleUIUtils+EntityWrapper nextStop { protected get; protected set; }
    protected Unity.Entities.Entity selectedEntity { protected get; }
    protected Unity.Entities.Entity selectedPrefab { protected get; }

    protected VehicleSection();

    protected virtual System.Void OnProcess();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Game.UI.InGame.VehicleStateLocaleKey <stateKey>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleStateLocaleKey <stateKey>k__BackingField;
```

- `private Game.UI.InGame.VehicleUIUtils+EntityWrapper <owner>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleUIUtils+EntityWrapper <owner>k__BackingField;
```

- `private System.Boolean <fromOutside>k__BackingField`  

```csharp
private System.Boolean <fromOutside>k__BackingField;
```

- `private Game.UI.InGame.VehicleUIUtils+EntityWrapper <nextStop>k__BackingField`  

```csharp
private Game.UI.InGame.VehicleUIUtils+EntityWrapper <nextStop>k__BackingField;
```


## Properties

- `protected Game.UI.InGame.VehicleStateLocaleKey stateKey { protected get; protected set }`  

```csharp
protected Game.UI.InGame.VehicleStateLocaleKey stateKey { protected get; protected set; }
```

- `protected Game.UI.InGame.VehicleUIUtils+EntityWrapper owner { protected get; protected set }`  

```csharp
protected Game.UI.InGame.VehicleUIUtils+EntityWrapper owner { protected get; protected set; }
```

- `protected System.Boolean fromOutside { protected get; protected set }`  

```csharp
protected System.Boolean fromOutside { protected get; protected set; }
```

- `protected Game.UI.InGame.VehicleUIUtils+EntityWrapper nextStop { protected get; protected set }`  

```csharp
protected Game.UI.InGame.VehicleUIUtils+EntityWrapper nextStop { protected get; protected set; }
```

- `protected Unity.Entities.Entity selectedEntity { protected get }`  

```csharp
protected Unity.Entities.Entity selectedEntity { protected get; }
```

- `protected Unity.Entities.Entity selectedPrefab { protected get }`  

```csharp
protected Unity.Entities.Entity selectedPrefab { protected get; }
```


## Constructors

- `protected VehicleSection()`  

```csharp
[Preserve]
	protected VehicleSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		Entity entity = base.EntityManager.GetComponentData<Owner>(selectedEntity).m_Owner;
		owner = new VehicleUIUtils.EntityWrapper(entity);
		fromOutside = base.EntityManager.HasComponent<Game.Objects.OutsideConnection>(entity);
		VehicleStateLocaleKey vehicleStateLocaleKey = stateKey;
		if (vehicleStateLocaleKey != VehicleStateLocaleKey.Returning && vehicleStateLocaleKey != VehicleStateLocaleKey.Patrolling && vehicleStateLocaleKey != VehicleStateLocaleKey.Collecting && vehicleStateLocaleKey != VehicleStateLocaleKey.Working)
		{
			nextStop = new VehicleUIUtils.EntityWrapper(VehicleUIUtils.GetDestination(base.EntityManager, selectedEntity));
		}
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		writer.PropertyName("stateKey");
		writer.Write(Enum.GetName(typeof(VehicleStateLocaleKey), stateKey));
		writer.PropertyName("owner");
		owner.Write(writer, m_NameSystem);
		writer.PropertyName("fromOutside");
		writer.Write(fromOutside);
		writer.PropertyName("nextStop");
		nextStop.Write(writer, m_NameSystem);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		stateKey = VehicleStateLocaleKey.Unknown;
		owner = new VehicleUIUtils.EntityWrapper(Entity.Null);
		fromOutside = false;
		nextStop = new VehicleUIUtils.EntityWrapper(Entity.Null);
	}
```


