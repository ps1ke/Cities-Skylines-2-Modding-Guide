# Game.Objects.Attachment

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.IEmptySerializable`  

## Code

```csharp
public sealed struct Attachment : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Attached;

    public Attachment(Unity.Entities.Entity attached);

}
```


## Fields

- `public Unity.Entities.Entity m_Attached`  

```csharp
public Unity.Entities.Entity m_Attached;
```


## Constructors

- `public Attachment(Unity.Entities.Entity attached)`  

```csharp
public Attachment(Entity attached)
	{
		m_Attached = attached;
	}
```


