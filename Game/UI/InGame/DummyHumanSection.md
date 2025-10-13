# Game.UI.InGame.DummyHumanSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public class DummyHumanSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <originEntity>k__BackingField;
    private Unity.Entities.Entity <destinationEntity>k__BackingField;

    protected System.String group { protected get; }
    private Unity.Entities.Entity originEntity { private get; private set; }
    private Unity.Entities.Entity destinationEntity { private get; private set; }

    public DummyHumanSection();

    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Unity.Entities.Entity <originEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <originEntity>k__BackingField;
```

- `private Unity.Entities.Entity <destinationEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <destinationEntity>k__BackingField;
```


## Properties

- `protected System.String group { protected get }`  

```csharp
protected System.String group { protected get; }
```

- `private Unity.Entities.Entity originEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity originEntity { private get; private set; }
```

- `private Unity.Entities.Entity destinationEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity destinationEntity { private get; private set; }
```


## Constructors

- `public DummyHumanSection()`  

```csharp
[Preserve]
	public DummyHumanSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		if (base.EntityManager.TryGetComponent<CurrentVehicle>(selectedEntity, out var component))
		{
			originEntity = base.EntityManager.GetComponentData<Owner>(component.m_Vehicle).m_Owner;
			destinationEntity = VehicleUIUtils.GetDestination(base.EntityManager, component.m_Vehicle);
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
		writer.PropertyName("origin");
		if (originEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, originEntity);
		}
		writer.PropertyName("originEntity");
		if (originEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(originEntity);
		}
		writer.PropertyName("destination");
		if (destinationEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, destinationEntity);
		}
		writer.PropertyName("destinationEntity");
		if (destinationEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(destinationEntity);
		}
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		originEntity = Entity.Null;
		destinationEntity = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (base.EntityManager.TryGetComponent<Resident>(selectedEntity, out var component))
		{
			return component.m_Citizen == Entity.Null;
		}
		return false;
	}
```


