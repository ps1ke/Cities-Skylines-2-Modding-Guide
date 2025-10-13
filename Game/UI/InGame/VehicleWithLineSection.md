# Game.UI.InGame.VehicleWithLineSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.InGame.VehicleSection`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

## Code

```csharp
public abstract class VehicleWithLineSection : Game.UI.InGame.VehicleSection, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Unity.Entities.Entity <lineEntity>k__BackingField;

    protected Unity.Entities.Entity lineEntity { protected get; protected set; }

    protected VehicleWithLineSection();

    protected virtual System.Void OnProcess();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
}
```


## Fields

- `private Unity.Entities.Entity <lineEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <lineEntity>k__BackingField;
```


## Properties

- `protected Unity.Entities.Entity lineEntity { protected get; protected set }`  

```csharp
protected Unity.Entities.Entity lineEntity { protected get; protected set; }
```


## Constructors

- `protected VehicleWithLineSection()`  

```csharp
[Preserve]
	protected VehicleWithLineSection()
	{
	}
```


## Methods

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		lineEntity = (base.EntityManager.TryGetComponent<CurrentRoute>(selectedEntity, out var component) ? component.m_Route : Entity.Null);
		base.OnProcess();
	}
```

- `public virtual OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
public override void OnWriteProperties(IJsonWriter writer)
	{
		base.OnWriteProperties(writer);
		writer.PropertyName("line");
		if (lineEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, lineEntity);
		}
		writer.PropertyName("lineEntity");
		writer.Write(lineEntity);
	}
```

- `protected virtual Reset() : System.Void`  

```csharp
protected override void Reset()
	{
		base.Reset();
		lineEntity = Entity.Null;
	}
```


