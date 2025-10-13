# Game.UI.InGame.EntityGamePanel

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `Game.UI.InGame.GamePanel`  
**Implements:** `Colossal.UI.Binding.IJsonWritable`, `System.IEquatable<Game.UI.InGame.EntityGamePanel>`  

## Code

```csharp
public abstract class EntityGamePanel : Game.UI.InGame.GamePanel, Colossal.UI.Binding.IJsonWritable, System.IEquatable<Game.UI.InGame.EntityGamePanel>
{
    private Unity.Entities.Entity <selectedEntity>k__BackingField;

    public Unity.Entities.Entity selectedEntity { get; set; }

    protected EntityGamePanel();

    protected virtual System.Void BindProperties(Colossal.UI.Binding.IJsonWriter writer);
    public System.Boolean Equals(Game.UI.InGame.EntityGamePanel other);
}
```


## Fields

- `private Unity.Entities.Entity <selectedEntity>k__BackingField`  

```csharp
private Unity.Entities.Entity <selectedEntity>k__BackingField;
```


## Properties

- `public Unity.Entities.Entity selectedEntity { get; set }`  

```csharp
public Unity.Entities.Entity selectedEntity { get; set; }
```


## Constructors

- `protected EntityGamePanel()`  

```csharp
protected EntityGamePanel();
```


## Methods

- `protected virtual BindProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

```csharp
protected override void BindProperties(IJsonWriter writer)
	{
		base.BindProperties(writer);
		writer.PropertyName("selectedEntity");
		writer.Write(selectedEntity);
	}
```

- `public Equals(Game.UI.InGame.EntityGamePanel other) : System.Boolean`  

```csharp
public bool Equals(EntityGamePanel other)
	{
		if (other == null)
		{
			return false;
		}
		if (this != other)
		{
			return selectedEntity.Equals(other.selectedEntity);
		}
		return true;
	}
```


