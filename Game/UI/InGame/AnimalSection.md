# Game.UI.InGame.AnimalSection

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoSectionBase`  
**Implements:** `Game.UI.InGame.ISectionSource`, `Colossal.UI.Binding.IJsonWritable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AnimalSection : Game.UI.InGame.InfoSectionBase, Game.UI.InGame.ISectionSource, Colossal.UI.Binding.IJsonWritable
{
    private Game.UI.InGame.AnimalSection+TypeKey <typeKey>k__BackingField;
    private Unity.Entities.Entity <ownerEntity>k__BackingField;
    private Unity.Entities.Entity <destinationEntity>k__BackingField;

    protected System.String group { protected get; }
    private Game.UI.InGame.AnimalSection+TypeKey typeKey { private get; private set; }
    private Unity.Entities.Entity ownerEntity { private get; private set; }
    private Unity.Entities.Entity destinationEntity { private get; private set; }

    public AnimalSection();

    private Unity.Entities.Entity GetDestination();
    private Game.UI.InGame.AnimalSection+TypeKey GetTypeKey();
    private System.String GetTypeKeyString(Game.UI.InGame.AnimalSection+TypeKey typeKey);
    protected virtual System.Void OnProcess();
    protected virtual System.Void OnUpdate();
    public virtual System.Void OnWriteProperties(Colossal.UI.Binding.IJsonWriter writer);
    protected virtual System.Void Reset();
    private System.Boolean Visible();
}
```


## Fields

- `private Game.UI.InGame.AnimalSection+TypeKey <typeKey>k__BackingField`  

```csharp
private Game.UI.InGame.AnimalSection+TypeKey <typeKey>k__BackingField;
```

- `private Unity.Entities.Entity <ownerEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <ownerEntity>k__BackingField;
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

- `private Game.UI.InGame.AnimalSection+TypeKey typeKey { private get; private set }`  

```csharp
private Game.UI.InGame.AnimalSection+TypeKey typeKey { private get; private set; }
```

- `private Unity.Entities.Entity ownerEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity ownerEntity { private get; private set; }
```

- `private Unity.Entities.Entity destinationEntity { private get; private set }`  

```csharp
private Unity.Entities.Entity destinationEntity { private get; private set; }
```


## Constructors

- `public AnimalSection()`  

```csharp
[Preserve]
	public AnimalSection()
	{
	}
```


## Methods

- `private GetDestination() : Unity.Entities.Entity`  

```csharp
private Entity GetDestination()
	{
		if (base.EntityManager.TryGetComponent<CurrentTransport>(selectedEntity, out var component))
		{
			Entity entity = Entity.Null;
			if (base.EntityManager.TryGetComponent<Target>(component.m_CurrentTransport, out var component2))
			{
				entity = component2.m_Target;
			}
			if (base.EntityManager.HasComponent<OutsideConnection>(entity))
			{
				return entity;
			}
			if (base.EntityManager.TryGetComponent<Owner>(entity, out var component3))
			{
				return component3.m_Owner;
			}
			if (base.EntityManager.Exists(entity))
			{
				return entity;
			}
		}
		return Entity.Null;
	}
```

- `private GetTypeKey() : Game.UI.InGame.AnimalSection+TypeKey`  

```csharp
private TypeKey GetTypeKey()
	{
		if (base.EntityManager.HasComponent<HouseholdPet>(selectedEntity))
		{
			return TypeKey.Pet;
		}
		if (base.EntityManager.HasComponent<Wildlife>(selectedEntity))
		{
			return TypeKey.Wildlife;
		}
		return TypeKey.Livestock;
	}
```

- `private GetTypeKeyString(Game.UI.InGame.AnimalSection+TypeKey typeKey) : System.String`  

```csharp
private string GetTypeKeyString(TypeKey typeKey)
	{
		return typeKey switch
		{
			TypeKey.Pet => "Pet", 
			TypeKey.Livestock => "Livestock", 
			_ => "Wildlife", 
		};
	}
```

- `protected virtual OnProcess() : System.Void`  

```csharp
protected override void OnProcess()
	{
		typeKey = GetTypeKey();
		ownerEntity = (base.EntityManager.TryGetComponent<HouseholdPet>(selectedEntity, out var component) ? component.m_Household : Entity.Null);
		destinationEntity = GetDestination();
		base.tooltipKeys.Add(GetTypeKeyString(typeKey));
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
		writer.PropertyName("typeKey");
		writer.Write(Enum.GetName(typeof(TypeKey), typeKey));
		writer.PropertyName("owner");
		if (ownerEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			m_NameSystem.BindName(writer, ownerEntity);
		}
		writer.PropertyName("ownerEntity");
		if (ownerEntity == Entity.Null)
		{
			writer.WriteNull();
		}
		else
		{
			writer.Write(ownerEntity);
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
		ownerEntity = Entity.Null;
		destinationEntity = Entity.Null;
	}
```

- `private Visible() : System.Boolean`  

```csharp
private bool Visible()
	{
		if (!base.EntityManager.HasComponent<HouseholdPet>(selectedEntity))
		{
			return base.EntityManager.HasComponent<Wildlife>(selectedEntity);
		}
		return true;
	}
```


## Nested types

- `Game.UI.InGame.AnimalSection+TypeKey`  

